# Cahier des Charges Fonctionnel — Dashboard Power BI (SDIS 77)

**Auteure :** Linda MAKAMTA (Responsable Data Analytics, KPIs & BI)  
**Destinataires :** Direction Générale, État-Major Opérationnel et Chefs de Groupement du SDIS 77  

---

## 1. Contexte & Enjeux Décisionnels

L'application Power BI doit permettre de passer des calculs bruts issus du pipeline de données à un outil d'aide à la décision visuel, fluide et pédagogique. Elle est articulée autour de **trois écrans majeurs**, chacun répondant à un arbitrage précis.

---

## 2. Description Détaillée des Trois Écrans

### Écran 1 — Cartographie Stratégique & Diagnostic Territorial (Q1 & Q5)
*Objectif : Identifier les secteurs prioritaires pour le pré-positionnement des moyens et du guet.*

- **Composants visuels :**
  - **Carte choroplèthe dynamique :** Communes de Seine-et-Marne colorées selon le KPI normalisé (`ha brûlés / 1 000 ha boisés`), avec superposition des polygones des massifs forestiers (Fontainebleau, Crécy, Villefermoy).
  - **Cartes KPI (Tuiles en haut d'écran) :**
    - Nombre total de départs de feux sur la sélection.
    - Surface totale parcourue (ha).
    - KPI normalisé départemental (`ha / 1 000 ha de forêt IGN`).
    - Part des feux contenus sous 1 ha (Proxy attaque rapide).
  - **Filtres interactifs (Slicers) :**
    - Sélecteur d'année (2019 à 2023, avec option « Quinquennat consolidé »).
    - Filtre par Groupement Territorial (Nord, Sud, Centre, Est).
    - Filtre par Massif Forestier (Fontainebleau, Crécy, Villefermoy, plaines de Brie).
  - **Graphique à barres horizontales :** Top 10 des communes les plus exposées rapportées à leur couvert végétal.

---

### Écran 2 — Simulateur d'Arbitrage des Seuils de Vigilance (Q2, T3 & Choix Option A/B/C)
*Objectif : Arbitrer le niveau de déclenchement du dispositif renforcé en visualisant le compromis sécurité / coût.*

- **Composants visuels :**
  - **Matrice de Confusion 2x2 interactive :**
    - Vrais Positifs (VP) : Journées avec feu où le dispositif renforcé était activé.
    - Faux Positifs (FP) : Journées mobilisées sans aucun départ de feu (mobilisation à vide / surcoût).
    - Faux Négatifs (FN) : Journées avec départ de feu survenues sous le seuil d'alerte (danger opérationnel).
    - Vrais Négatifs (VN) : Journées calmes sans mobilisation inutile.
  - **Sélecteur de Scénario d'Arbitrage (Boutons radio) :**
    - *Option A :* Seuil Orange uniforme départemental.
    - *Option B :* Seuil Jaune uniforme départemental.
    - *Option C :* Dispositif gradué et territorialisé (Jaune sur massifs sensibles, Orange/Rouge ailleurs).
  - **Indicateurs d'impact simulés :**
    - Taux de couverture des départs de feux réels (%).
    - Nombre de journées de mobilisation à vide induites par saison.
    - Coût d'astreinte estimé (en k€ pour le budget du CASDIS).

---

### Écran 3 — Robustesse Temporelle & Benchmark Régional (Q4)
*Objectif : Prouver que la stratégie 2027 ne dépend pas d'une année climatique atypique.*

- **Composants visuels :**
  - **Courbe chronologique 2019–2023 :** Évolution annuelle des surfaces brûlées brutes opposée à la médiane 5 ans (mise en évidence de l'anomalie caniculaire de 2022 représentant 69,2 % des dégâts).
  - **Benchmark Île-de-France :** Comparatif de la Seine-et-Marne avec les départements franciliens voisins (Essonne 91, Yvelines 78, Val-d'Oise 95).
  - **Graphique de sensibilité :** Comparaison visuelle du classement des massifs selon la base de normalisation choisie (Surface totale communale INSEE vs Surface boisée réelle IGN).
