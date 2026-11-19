# 3. Annexes — Liste Exhaustive des Sources de Données Utilisées

Ce document recense et qualifie l'ensemble des sources de données mobilisées pour la modélisation prédictive, le calibrage des seuils de vigilance et l'aide à la décision du SDIS 77 (Seine-et-Marne).

---

## 3.1 Tableau Récapitulatif des Sources

| N° | Source de Données | Producteur Officiel | Type de Gouvernance | Licence | Format Technique | Granularité Spatiale & Temporelle | URL d'Accès Officielle |
| :---: | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **S1** | **BDIFF** (Base de Données sur les Incendies de Forêts en France) | IGN, Ministère de l'Agriculture, Ministère de l'Intérieur | 3rd-Party (Open Data) | Licence Ouverte 2.0 (Etalab) | CSV, API data.gouv | Commune, Événement horodaté (2006–2024) | [data.gouv.fr — BDIFF](https://www.data.gouv.fr/fr/datasets/base-de-donnees-sur-les-incendies-de-forets-en-france-bdiff/) |
| **S2** | **Météo des forêts** (Archives & Alertes Quotidiennes) | Météo-France | 3rd-Party (Open Data) | Licence Ouverte 2.0 (Etalab) | CSV, GeoJSON, API | Département (77), Quotidien estival (2023–2026) | [data.gouv.fr — Météo des forêts](https://meteofrance.com/meteo-des-forets) |
| **S3** | **Données Climatologiques de Base** (Stations Météo 77) | Météo-France | 3rd-Party (Open Data) | Licence Ouverte 2.0 (Etalab) | CSV (horaire / quotidien) | Station ponctuelle (Melun, Fontainebleau, etc.) | [meteo.data.gouv.fr](https://meteo.data.gouv.fr/) |
| **S4** | **BD Forêt v2 & Inventaire Forestier National (IFN)** | IGN (Institut National de l'Information Géographique et Forestière) | 3rd-Party (Open Data) | Licence Ouverte 2.0 (Etalab) | Shapefile, GeoPackage, WFS | Polygone de peuplement (>= 0,5 ha), Mise à jour pluriannuelle | [geoservices.ign.fr — BD Forêt](https://geoservices.ign.fr/bdforet) |
| **S5** | **Référentiel des Communes & Superficies (CODGEO)** | INSEE | 3rd-Party (Open Data) | Licence Ouverte 2.0 (Etalab) | CSV, DBF | Commune administrative (5 caractères), Annuel | [insee.fr — Code Officiel Géographique](https://www.insee.fr/fr/information/2560452) |
| **S6** | **RGE ALTI (Modèle Numérique de Terrain - MNT)** | IGN | 3rd-Party (Open Data) | Licence Ouverte 2.0 (Etalab) | Raster GeoTIFF / ASC | Grille altimétrique 1m à 5m (Pente, Exposition au vent) | [geoservices.ign.fr — RGE ALTI](https://geoservices.ign.fr/rgealti) |
| **S7** | **NASA FIRMS** (Fire Information for Resource Management System) | NASA / LANCE (Satellites MODIS & VIIRS) | 3rd-Party (Open Data International) | Données publiques NASA (libre) | CSV, GeoJSON, API WMS/WFS | Point chaud 375 m (VIIRS) à 1 km (MODIS), Quasi temps-réel | [firms.modaps.eosdis.nasa.gov](https://firms.modaps.eosdis.nasa.gov/) |
| **S8** | **Copernicus EFFIS** (European Forest Fire Information System) | Commission Européenne / JRC | 3rd-Party (Open Data International) | Copernicus Open Access | GeoTIFF, NetCDF, GeoJSON | Maille 8 km (Indice FWI), Quotidien | [effis.jrc.ec.europa.eu](https://effis.jrc.ec.europa.eu/) |
| **S9** | **Mains Courantes & Horodatages Systel / Nexsis** *(Cible)* | SDIS 77 (Service Départemental d'Incendie et de Secours) | 1st-Party (Données Internes) | Données internes confidentielles / Diffusion restreinte | Base relationnelle interne, CSV anonymisé | Coordonnées GPS précises, Seconde près | *Accès interne sécurisé État-Major SDIS 77* |
| **S10** | **Cartographie des Pistes & Défense des Forêts (DFCI)** | ONF (Office National des Forêts) / Direction Départementale des Territoires (DDT 77) | 2nd-Party (Partenaire Institutionnel) | Convention partenariale | Shapefile SIG | Points d'Eau Incendie (PEI), Pistes carrossables | [onf.fr — Massif de Fontainebleau](https://www.onf.fr/) |

---

## 3.2 Fiches Détaillées par Catégorie de Source

### A. Données Historiques de Sinistralité (S1 : BDIFF)
- **Description :** Recensement officiel de tous les feux de forêt ayant entraîné l'engagement des services d'incendie et de secours sur le territoire français.
- **Rôle dans le projet :** Source socle pour le calcul du KPI de décision (*Surface brûlée pour 1 000 ha boisés*), de la fréquence des éclosions et de la part des feux contenus sous 1 hectare.
- **Profondeur historique :** De 2006 à 2024 (série continue).
- **Points de vigilance & Limites :** Ne comptabilise pas les départs de feux strictement agricoles (feux de chaumes en Brie) lorsqu'ils ne menacent aucun massif boisé ; délais de consolidation administrative pouvant atteindre 6 à 12 mois pour l'année en cours.

### B. Données Météorologiques et d'Alerte (S2 & S3 : Météo-France)
- **Description :** Émission quotidienne d'un niveau de risque incendie (Vert, Jaune, Orange, Rouge) fondé sur l'Indice Forêt Météo (IFM / FWI) et intégrant la sécheresse des végétaux, la température, l'humidité de l'air et le vent.
- **Rôle dans le projet :** Évaluation du taux de couverture des départs de feux réels (Q2) et simulation du volume de journées mobilisées sans feu (T3).
- **Profondeur historique :** Déploiement grand public depuis l'été 2023. Les années antérieures font l'objet d'une rétro-simulation à partir des données climatiques des stations de Melun et Fontainebleau.
- **Points de vigilance & Limites :** Échelle départementale unique masquant le microclimat très sec des sables de Fontainebleau par rapport aux sols humides de l'Est francilien.

### C. Référentiels Spatiaux et Végétaux (S4 & S5 : IGN et INSEE)
- **Description :** Cartographie précise des essences d'arbres (pins sylvestres, chênes, taillis) et délimitation administrative des communes et massifs.
- **Rôle dans le projet :** Fournit la base de normalisation immuable du KPI (140 000 ha boisés en Seine-et-Marne) et permet d'éviter l'erreur d'une analyse basée sur les seuls chiffres bruts.
- **Précision :** Détection des peuplements à partir de 0,5 hectare ; contours cadastraux millimétriques.

### D. Télédétection et Données Spatiales (S7 & S8 : NASA FIRMS & Copernicus)
- **Description :** Détection thermique satellitaire infrarouge des anomalies de température au sol.
- **Rôle dans le projet :** Contrôle qualité indépendant pour contrer le biais de sous-déclaration de la loi de Goodhart (détection des petits départs de feu non répertoriés dans la BDIFF ou survenus en lisière agricole).
- **Résolution :** 375 mètres pour le capteur VIIRS (SNPP et NOAA-20) ; passage bi-quotidien au-dessus de l'Île-de-France.
