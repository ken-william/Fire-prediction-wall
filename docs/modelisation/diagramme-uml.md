# 1. Diagramme UML de Classes — Modèle Conceptuel et Logique de Données

Ce document formalise la modélisation conceptuelle et logique des données de la plateforme d'aide à la décision feux de forêt pour la Seine-et-Marne (SDIS 77). Le modèle est conçu pour être exportable ou modélisable sous **StarUML** et visualisable directement via le diagramme Mermaid ci-dessous.

---

## 1.1 Diagramme de Classes UML (Rendu Mermaid)

```mermaid
classDiagram
    direction TB

    class Commune {
        +String code_insee PK
        +String nom_commune
        +String code_postal
        +Float superficie_totale_ha
        +Float surface_boisee_ha
        +Float taux_boisement
        +Float zone_interface_wui_ha
        +Integer population_insee
        +Polygon geom
    }

    class MassifForestier {
        +String id_massif PK
        +String nom_massif
        +Float surface_totale_ha
        +String type_peuplement_dominant
        +String vulnerabilite_sol
        +String statut_protection
    }

    class CentreIncendieSecours {
        +String code_cis PK
        +String nom_cis
        +String groupement_territorial
        +Integer effectif_garde_spp
        +Integer effectif_garde_spv
        +Integer dotation_ccf
        +Float coord_x
        +Float coord_y
    }

    class Incendie {
        +String id_incendie PK
        +String code_insee FK
        +Date date_premiere_alerte
        +Time heure_premiere_alerte
        +Date date_extinction
        +Float surface_parcourue_totale_ha
        +Float surface_foret_ha
        +Float surface_agricole_chaume_ha
        +String type_vegetation
        +String nature_cause
        +Float coord_lat
        +Float coord_lon
        +String source_signalement
    }

    class MeteoDepartementaleJour {
        +Date date_observation PK
        +String code_departement PK
        +String niveau_meteo_forets
        +Float temperature_max_c
        +Float humidite_min_pourcent
        +Float vitesse_vent_rafale_kmh
        +String direction_vent_dominante
        +Float cumul_precipitations_mm
        +Float indice_fwi_moyen
    }

    class DispositifOperationnel {
        +String id_dispositif PK
        +Date date_dispositif FK
        +String code_cis FK
        +String regle_declenchement
        +String niveau_alerte_active
        +Integer nb_patrouilles_giff_postees
        +Integer nb_engins_ccf_mobilises
        +Boolean guet_arme_active
        +Boolean feu_survenu_sur_secteur
        +Float cout_mobilisation_eur
    }

    class KpiConsolideAnnuel {
        +String id_kpi PK
        +Integer annee
        +String maille_analyse
        +String identifiant_entite
        +Integer nb_feux_total
        +Float surface_brulee_totale_ha
        +Float surface_brulee_p1000ha_boises
        +Float taux_couverture_seuil_jaune
        +Float taux_couverture_seuil_orange
        +Float part_feux_inf_1ha
        +Integer nb_journees_mobilisees_a_vide
    }

    Commune "1..*" --> "1" MassifForestier : est rattachée à
    Commune "1" --> "0..*" Incendie : localise
    CentreIncendieSecours "1" --> "1..*" Commune : couvre le premier appel de
    MeteoDepartementaleJour "1" --> "0..*" DispositifOperationnel : déclenche
    DispositifOperationnel "0..*" --> "1" CentreIncendieSecours : armé par
    Incendie "0..*" --> "0..1" DispositifOperationnel : couvert par
    Commune "1" --> "0..*" KpiConsolideAnnuel : consolidée dans
    MassifForestier "1" --> "0..*" KpiConsolideAnnuel : agrégé dans
```

---

## 1.2 Dictionnaire des Entités Métier

### 1. Entité `Commune` (Référentiel Spatial & Administratif)
- **Rôle** : Maille territoriale atomique permettant de réconcilier les données cadastrales, les massifs forestiers et les sinistres.
- **Attributs clés** :
  - `code_insee` (PK) : Code officiel géographique INSEE sur 5 caractères (ex. `77186` pour Fontainebleau).
  - `surface_boisee_ha` : Superficie forestière réelle issue de la BD Forêt IGN (> 140 000 ha au total sur la Seine-et-Marne).
  - `taux_boisement` : Ratio `surface_boisee_ha / superficie_totale_ha` (24 % en moyenne départementale, jusqu'à 85 % à Fontainebleau).
  - `zone_interface_wui_ha` : Surface de la zone d'interface habitat-forêt (bande des 50 mètres soumise aux Obligations Légales de Débroussaillement - OLD).

### 2. Entité `MassifForestier` (Périmètre Écologique & Géographique)
- **Rôle** : Regroupement cohérent des espaces boisés majeurs du département.
- **Attributs clés** :
  - `id_massif` (PK) : Identifiant unique normalisé (ex. `MASSIF_FONTAINEBLEAU`, `MASSIF_CRECY`, `MASSIF_VILLEFERMOY`).
  - `vulnerabilite_sol` : Caractéristique édaphique (ex. *Sables stampiens ultra-drainants* à Fontainebleau vs *Argiles à meulières* en Brie).
  - `statut_protection` : Régime juridique (Forêt de protection, Réserve biologique, Parc naturel régional du Gâtinais français).

### 3. Entité `CentreIncendieSecours` (Moyens du SDIS 77)
- **Rôle** : Caserne ou centre de secours armant les personnels et les véhicules de lutte.
- **Attributs clés** :
  - `code_cis` (PK) : Identifiant interne du centre de secours.
  - `groupement_territorial` : Secteur d'affectation (Nord, Sud, Centre, Est).
  - `dotation_ccf` : Nombre de Camions Citernes Feux de Forêts opérationnels.

### 4. Entité `Incendie` (Événements de Sinistres)
- **Rôle** : Enregistrement individuel d'un feu de forêt ou de végétation issu de la BDIFF.
- **Attributs clés** :
  - `id_incendie` (PK) : Numéro national unique BDIFF.
  - `surface_parcourue_totale_ha` : Surface brute incendiée en hectares.
  - `surface_foret_ha` : Part de surface boisée détruite (filtrage des feux agricoles de Brie).
  - `source_signalement` : Origine de l'alerte (Appel public 18/112, patrouille GIFF, détection satellite).

### 5. Entité `MeteoDepartementaleJour` (Conditions Exogènes)
- **Rôle** : Climatologie quotidienne et qualification du risque météo.
- **Attributs clés** :
  - `date_observation` + `code_departement` (PK composite) : Clé unique par jour et département (77).
  - `niveau_meteo_forets` : Indice public Météo-France (Vert=1, Jaune=2, Orange=3, Rouge=4).
  - `indice_fwi_moyen` : Valeur numérique continue de l'Indice Forêt Météo (IFM/FWI).

### 6. Entité `DispositifOperationnel` (Décision SDIS 77)
- **Rôle** : Trace quotidienne de la posture de mobilisation des pompiers.
- **Attributs clés** :
  - `regle_declenchement` : Option d'arbitrage appliquée (Option A = Orange, Option B = Jaune, Option C = Gradué territorialisé).
  - `nb_patrouilles_giff_postees` : Nombre de Groupes d'Intervention Feux de Forêts pré-positionnés en forêt.
  - `feu_survenu_sur_secteur` : Booléen qualifiant si la journée a enregistré un feu (Vrai Positif) ou aucun départ (Faux Positif / mobilisation à vide).

### 7. Entité `KpiConsolideAnnuel` (Couche Gold — Perspective Utilisateur)
- **Rôle** : Table de restitution analytique pour l'État-Major du SDIS 77 et le CASDIS.
- **Attributs clés** :
  - `surface_brulee_p1000ha_boises` : KPI de décision normalisé (0,45 ha / 1 000 ha en moyenne quinquennale).
  - `taux_couverture_seuil_jaune` : Pourcentage des journées avec feu couvertes en niveau Jaune (~82 %).
  - `part_feux_inf_1ha` : Efficacité de l'attaque initiale (~88 % des feux contenus).

---

## 1.3 Compatibilité StarUML & PlantUML

Le fichier source [`diagramme-uml.puml`](file:///home/antigravity/ken-william/Fire-prediction-wall/docs/modelisation/diagramme-uml.puml) est mis à disposition dans le dépôt. Il peut être :
1. Directement ouvert ou rendu via le plugin PlantUML sous VS Code / IntelliJ / JetSki.
2. Importé ou retranscrit dans **StarUML** via le menu *File > Import > XMI/Class Structure* ou modélisé selon l'arbre de packages ci-dessus.
