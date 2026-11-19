# Spécifications des Formules DAX — Modèle Power BI (SDIS 77)

**Auteure :** Linda MAKAMTA (Responsable Data Analytics, KPIs & BI)  
**Modèle relationnel sous-jacent :** Étoile (Star Schema) alimentée par la couche Gold Parquet de Mike (`fact_incendie`, `fact_meteo`, `dim_commune`, `dim_massif`, `dim_date`).

---

## 1. Mesures Volumétriques de Base

### 1.1 Nombre Total de Feux
```dax
Total_Feux = 
COUNTROWS( fact_incendie )
```

### 1.2 Surface Brûlée Totale (en Hectares)
```dax
Surface_Brulee_Totale_ha = 
SUM( fact_incendie[surface_parcourue_ha] )
```

### 1.3 Surface Boisée du Territoire (en Milliers d'Hectares)
```dax
Surface_Boisee_IGN_1000ha = 
SUM( dim_commune[surface_boisee_ha] ) / 1000
```

---

## 2. Indicateurs Clés de Performance (KPIs)

### 2.1 KPI de Décision — Surface Brûlée pour 1 000 ha Boisés
```dax
KPI_Surface_Brulee_p1000ha = 
DIVIDE(
    [Surface_Brulee_Totale_ha],
    [Surface_Boisee_IGN_1000ha],
    BLANK()
)
```

### 2.2 Médiane Quinquennale du KPI (Estimateur Robuste hors Aléa Extrême)
```dax
Mediane_KPI_Quinquennale = 
MEDIANX(
    VALUES( dim_date[annee] ),
    [KPI_Surface_Brulee_p1000ha]
)
```

### 2.3 Part des Feux Contenus sous 1 Hectare (Proxy Efficacité Attaque Initiale)
```dax
Part_Feux_Inf_1ha = 
VAR Nb_Feux_Petits = 
    CALCULATE(
        [Total_Feux],
        fact_incendie[surface_parcourue_ha] < 1.0
    )
RETURN
DIVIDE(
    Nb_Feux_Petits,
    [Total_Feux],
    0
)
```

---

## 3. Mesures d'Arbitrage des Seuils de Vigilance (Météo des Forêts)

### 3.1 Taux de Couverture au Seuil Jaune (Niveau >= 2)
```dax
Taux_Couverture_Seuil_Jaune = 
VAR Jours_Feu_Couverts = 
    CALCULATE(
        DISTINCTCOUNT( fact_incendie[date_alerte] ),
        fact_meteo[niveau_danger_num] >= 2
    )
VAR Total_Jours_Feu = 
    DISTINCTCOUNT( fact_incendie[date_alerte] )
RETURN
DIVIDE( Jours_Feu_Couverts, Total_Jours_Feu, 0 )
```

### 3.2 Taux de Couverture au Seuil Orange (Niveau >= 3)
```dax
Taux_Couverture_Seuil_Orange = 
VAR Jours_Feu_Couverts = 
    CALCULATE(
        DISTINCTCOUNT( fact_incendie[date_alerte] ),
        fact_meteo[niveau_danger_num] >= 3
    )
VAR Total_Jours_Feu = 
    DISTINCTCOUNT( fact_incendie[date_alerte] )
RETURN
DIVIDE( Jours_Feu_Couverts, Total_Jours_Feu, 0 )
```

### 3.3 Nombre de Journées de Mobilisation sans Feu (Faux Positifs / Coût à Vide)
```dax
Jours_Mobilises_Sans_Feu = 
VAR Seuil_Selectionne = SELECTEDVALUE( Param_Seuil[Valeur], 2 ) -- 2 = Jaune par défaut
RETURN
CALCULATE(
    DISTINCTCOUNT( fact_meteo[date] ),
    fact_meteo[niveau_danger_num] >= Seuil_Selectionne,
    ISBLANK( RELATED( fact_incendie[id_incendie] ) )
)
```

### 3.4 Simulation du Coût Budgétaire d'Astreinte (en k€)
```dax
Cout_Simulation_Astreinte_kEUR = 
VAR Cout_Moyen_Journee_GIFF = 4.5 -- 4 500 € par journée de garde postée GIFF + patrouille
RETURN
[Jours_Mobilises_Sans_Feu] * Cout_Moyen_Journee_GIFF
```
