# Analyse de la Commande — Théophane KENGNI

- **Auteur** : Théophane KENGNI (`ken-william`)
- **Projet** : Feux de forêt Auvergne-Rhône-Alpes — Saison feux 2027 (SDMIS 69)
- **Cadre** : Modélisation et Pipeline de données - EU01. Stratégie business data-driven (Hétic MD5 - 2026/2027)
- **Livrable** : Exercice 1 — Partie B (Analyse individuelle)

---

## 1. Les Questions Décisionnelles

Chaque question ci-dessous conditionne directement un arbitrage ou une action opérationnelle de la Direction du SDMIS 69 :

### Axe 1 — Périmètre Métier, Typologie des Sinistres & Causes Naturelles vs Humaines
1. **Périmètre des feux couverts (Forêt stricte vs Espaces naturels & Périurbains)** :
   *Le SDMIS 69 couvre un territoire très contrasté (Métropole de Lyon périurbaine, zones agricoles de moissons, massifs des Monts du Lyonnais et du Beaujolais). Le SDMIS 69 couvre-t-il uniquement les feux de forêts au sens strict (massifs boisés / BDIFF), ou également les feux d'espaces naturels, périurbains et agricoles (friches, chaumes, broussailles) qui sont fréquents dans la périphérie lyonnaise, mobilisent les mêmes moyens et menacent directement les interfaces habitat-forêt ?*
   * **Impact décisionnel** : Si la commande inclut les friches et chaumes, le SDMIS doit pré-positionner des moyens d'attaque rapide en périphérie lyonnaise dès juillet (moissons) au lieu de concentrer les patrouilles uniquement dans les grands massifs du Beaujolais.

2. **Définition d'un « feu significatif » pour le SDMIS** :
   *Quand les chefs de centre parlent de « feux partis des jours où l'indice était au plus bas », s'agit-il de tout départ de feu (même maîtrisé à moins de $100\text{ m}^2$) ou uniquement des feux ayant dépassé un certain seuil de surface parcourue ou de moyens engagés ? Quel est le critère de gravité prioritaire pour la Direction : le nombre d'éclosions ou la surface/menace sur le bâti ?*
   * **Impact décisionnel** : Calibre l'algorithme d'optimisation soit sur la réduction du taux de feux naissants (détection ultra-précoce), soit sur l'évitement des méga-feux (> 20 ha).

3. **Mesure des feux d'origine naturelle et facteurs biophysiques d'éclosion** :
   *Beaucoup de départs de feux surviennent ou s'embrasent par des mécanismes naturels ou biophysiques indépendamment d'une action humaine directe (impacts de foudre sèche lors d'orages d'été, dessèchement extrême de la litière végétale, stress hydrique cumulé des sols, topographie et exposition solaire Sud/Sud-Ouest, couloirs de vent du Rhône). Comment isoler ces feux naturels dans les données historiques, et quels paramètres biophysiques locaux devons-nous prioriser pour capter ces éclosions que l'indice météo global ne voit pas ?*
   * **Impact décisionnel** : Déclenche des patrouilles post-orages sur les couloirs de foudre même si l'indice météo général est bas/vert.

### Axe 2 — Déconstruction de l'Indice « Météo des Forêts » & Granularité
4. **Nature et granularité de l'indicateur utilisé actuellement** :
   *La Direction se réfère-t-elle à l'indicateur grand public de Météo-France (carte publique « Météo des forêts », échelle agrégée de 1 à 4 / vert à rouge au niveau départemental) ou aux sous-indices techniques de l'IFM (Indice Forêt Météo / Fire Weather Index - FWI) calculés par Météo-France par zone météo ou massif ? Avons-nous la liberté de reconstruire ou d'hybrider cet indice avec des données à maille fine (ex. humidité des sols SIM2 à 8 km, vitesse du vent local, indice de sécheresse) ?*
   * **Impact décisionnel** : Détermine si l'outil d'arbitrage doit corriger l'indice public existant ou recalculer un score de risque propriétaire à maille infra-départementale.

5. **Échelle géographique d'arbitrage des moyens** :
   *Pour la question « où concentrer nos moyens », quelle est la maille opérationnelle de décision du SDMIS 69 : le Groupement territorial, le secteur de premier appel d'un Centre d'Incendie et de Secours (CIS), la commune, ou le massif forestier ?*
   * **Impact décisionnel** : Fixe le niveau d'agrégation spatiale du modèle pour que les consignes soient directement exploitables par les chefs de groupement.

6. **Cinétique temporelle et effet mémoire (Inertie de la sécheresse)** :
   *Les chefs de centre constatent des feux les jours où l'indice est au plus bas. Est-ce lié à un décalage temporel de l'indice (ex. une pluie fine en surface fait chuter l'indice du jour, alors que la biomasse profonde ou les herbes fines restent prêtes à s'enflammer avec le vent) ? Devons-nous analyser l'indice sur une fenêtre glissante (J-7, J-15, cumul de sécheresse printanière) plutôt qu'à la journée J ?*
   * **Impact décisionnel** : Évite de lever le dispositif renforcé trop tôt après une pluie d'été trompeuse qui ne réhydrate pas le sol en profondeur.

### Axe 3 — Modèle Économique, Contrainte Humaine & « Dispositif Renforcé »
7. **Moyens d'action et fonction de coût (Faux-Positif vs Faux-Négatif)** :
   *On ne peut pas mobiliser des pompiers et des moyens humains partout et en permanence pour chaque alerte. Quels sont les coûts ou contraintes associés au déclenchement d'un dispositif renforcé (astreintes, patrouilles préventives mobiles, guet, surveillance à distance par vigie/caméras/drones) afin d'évaluer la fonction de coût d'un faux-positif (mobilisation coûteuse à vide, fatigue opérationnelle des effectifs) vs un faux-négatif (départ de feu sans pré-positionnement) ?*
   * **Impact décisionnel** : Permet de pondérer mathématiquement la matrice de confusion de notre modèle pour trouver le seuil à coût global minimal.

8. **Gradation et plafond budgétaire du dispositif renforcé** :
   *Le déclenchement du dispositif renforcé est-il binaire (Activé / Non activé sur tout le département) ou gradué (ex. Niveau 1 : guet fixe / télédétection ; Niveau 2 : patrouilles mobiles ciblées ; Niveau 3 : gardes postées en caserne) ? Disposons-nous d'un ordre de grandeur du budget annuel ou du nombre maximum de « journées-dispositif » que le SDMIS 69 peut financer sur l'été 2027 pour optimiser notre seuil sous contrainte budgétaire ?*
   * **Impact décisionnel** : Transforme un problème théorique en une allocation sous contrainte de budget fermé (ex. max 25 jours renforcés par été).

9. **Effet d'atténuation du dispositif (Biais d'observation / Paradoxe de la prévention)** :
   *Lorsque l'indice est très élevé et qu'aucun feu majeur ne se déclare, est-il possible que ce soit justement grâce au dispositif préventif déployé (dissuasion, interdiction d'accès aux massifs, extinction immédiate des départs naissants à la première fumée) ? Avons-nous moyen de distinguer l'absence de départ de feu de l'efficacité de la prévention ?*
   * **Impact décisionnel** : Empêche l'algorithme de considérer à tort les journées préventives réussies comme des « erreurs de prédiction ».

10. **Délai d'intervention et vulnérabilité opérationnelle (Isochrones casernes)** :
    *Un départ de feu situé à 5 minutes d'une caserne est vite maîtrisé, tandis qu'un départ à 25 minutes dans un massif escarpé sans point d'eau devient critique même par indice modéré. Pour répondre à « où concentrer nos moyens », devons-nous intégrer le temps d'accès théorique des secours (isochrones CIS) et le maillage des points d'eau incendie comme critère de priorisation géographique ?*
    * **Impact décisionnel** : Positionne les patrouilles préventives prioritairement dans les « zones blanches » opérationnelles éloignées des casernes.

### Axe 4 — Stratégie de Données, Sources Exogènes & Benchmarking
11. **Croisement avec des sources exogènes (Au-delà de BDIFF & Météo)** :
    *Nous envisageons de croiser la base historique des incendies (BDIFF / Prométhée) et les données météo avec des variables structurelles, biophysiques et territoriales en Open Data : typologie de végétation et biomasse (BD Forêt IGN), topographie/pente/exposition (RGE ALTI), humidité profonde des sols (Météo-France SIM2), impacts de foudre, et vulnérabilité des interfaces (BD TOPO). Confirmez-vous que cette approche multi-sources est pertinente pour construire notre inventaire, notre graphe de concepts et notre matrice « Questions × Sources » ?*
    * **Impact décisionnel** : Valide l'architecture d'ingestion et évite de restreindre l'entrepôt à deux tables insuffisantes.

12. **Périmètre du Benchmark Régional et National** :
    *Pour situer le Rhône (69) par rapport aux autres départements d'Auvergne-Rhône-Alpes (notamment l'Ardèche 07 ou la Drôme 26 très exposées, ou les départements alpins) et au territoire national, préconisez-vous une analyse exhaustive des 96 départements métropolitains ou une comparaison par clusters bioclimatiques (départements continentaux/périurbains vs départements méditerranéens/Sud-Est vs massifs montagneux) ?*
    * **Impact décisionnel** : Définit la volumétrie des pipelines de données à construire et le cadre d'analyse comparative.

13. **Période historique de référence (Rupture climatique)** :
    *La commande mentionne que l'été 2027 s'annonce aussi critique que 2026. Sur quelle profondeur historique devons-nous calibrer nos analyses (ex. 5 dernières années post-2022 marquées par les méga-sécheresses dans le Rhône, ou 15-20 ans d'historique BDIFF au risque de diluer le changement de régime climatique récent) ?*
    * **Impact décisionnel** : Détermine le fenêtrage temporel d'entraînement pour éviter d'apprendre sur un climat révolu.

---

## 2. Les Termes Inconnus (Alimentation du Glossaire d'Équipe)

Ces termes techniques et métiers ont été identifiés pour alimenter le glossaire commun du groupe :

1. **SDMIS 69** : *Service Départemental-Métropolitain d'Incendie et de Secours du Rhône*. Établissement public spécifique gérant à la fois le département du Rhône et la Métropole de Lyon.
2. **Météo des forêts** : Dispositif national d'information préventive lancé par Météo-France en 2023, diffusé de juin à septembre avec 4 niveaux de danger (Vert = faible, Jaune = modéré, Orange = élevé, Rouge = très élevé).
3. **IFM (Indice Forêt Météo) / FWI (Fire Weather Index)** : Modèle d'origine canadienne utilisé par Météo-France, combinant température, humidité relative, vent et précipitations pour évaluer le potentiel d'incendie.
4. **FFMC (Fine Fuel Moisture Code)** : Composante de l'IFM mesurant la teneur en eau des combustibles fins de surface (herbes sèches, aiguilles mortes). Réagit très rapidement (quelques heures).
5. **DMC / DC (Duff Moisture Code / Drought Code)** : Composantes de l'IFM mesurant la teneur en humidité des couches organiques moyennes et profondes du sol. Représente l'effet mémoire de la sécheresse.
6. **WUI (Wildland-Urban Interface) / Interface Habitat-Forêt** : Zone de contact direct entre des constructions humaines et des espaces naturels combustibles, où se concentrent 90 % des départs et 100 % des enjeux de protection des personnes et des biens.
7. **DECI & REMOCRA** : *Défense Extérieure Contre l'Incendie*. Plateforme collaborative utilisée par les pompiers pour inventorier et suivre la disponibilité des Points d'Eau Incendie (hydrants, citernes forestières).
8. **Dispositif Renforcé (DFCI)** : Mesure opérationnelle activée par le SDMIS lors des pics de risque (patrouilles mobiles de surveillance, guet armé en vigie, gardes postées en caserne pour départ immédiat à moins de 3 minutes).
9. **CIS (Centre d'Incendie et de Secours)** : Caserne de pompiers locale assurant le premier appel sur son secteur opérationnel.
10. **BDIFF / Prométhée** : *Base de Données sur les Incendies de Forêts en France* (couverture nationale) et *Prométhée* (base historique spécifique à la zone méditerranéenne depuis 1973).
11. **OLD (Obligations Légales de Débroussaillement)** : Obligation réglementaire de débroussailler dans un rayon de 50 m autour des habitations et 200 m des massifs boisés pour rompre la continuité du combustible.
12. **Foudre Sèche** : Orage estival générant des impacts au sol sans précipitations suffisantes pour éteindre les départs de feux, responsable d'environ 10 % des éclosions naturelles.

---

## 3. Les Besoins de la Direction du SDMIS 69

L'analyse de la commande met en évidence trois catégories de besoins interconnectés :

1. **Besoin d'aide à la décision spatiale (Où concentrer les moyens ?)** :
   - Cartographier les zones d'Auvergne-Rhône-Alpes et du Rhône à plus forte probabilité combinée d'éclosion et de gravité.
   - Identifier les secteurs où le risque d'incendie dépasse les capacités de réponse rapide des casernes existantes (zones à long délai d'accès).
   - Arbitrer entre surveillance active (patrouilles, vigies) et pré-positionnement d'engins feux de forêts (CCF).

2. **Besoin d'optimisation du seuil de déclenchement (Quand déclencher ?)** :
   - Remplacer ou corriger le seuil départemental binaire de la Météo des forêts par une règle d'activation graduée et territorialisée.
   - Minimiser le coût économique des fausses alertes (sur-mobilisation des effectifs) sans jamais rater les jours de départs réels (sous-mobilisation critique).
   - Intégrer les facteurs que la Météo des forêts ignore : l'état réel de la végétation, l'exposition des versants, la foudre sèche et la pression humaine.

3. **Besoin de justification budgétaire et de benchmarking** :
   - Démontrer au Conseil d'Administration du SDMIS que chaque euro mobilisé sur le dispositif renforcé protège des zones à haute valeur (humaine, écologique, économique).
   - Situer la vulnérabilité du Rhône par rapport aux autres départements d'Auvergne-Rhône-Alpes pour justifier d'éventuels renforts ou mutualisations régionales.

---

## 4. Spécification des Données Idéales

Pour chaque question décisionnelle clé, voici la définition de la « donnée idéale » nécessaire à l'arbitrage :

| Question Décisionnelle | Donnée Idéale Cible | Grain Spatial | Période Temporelle | Fraîcheur / Fréquence | Emprise Géographique |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Q1 & Q2 (Périmètre & Gravité des départs)** | Main courante des interventions feux réels (surface brûlée, type de végétation touchée, heure de départ, véhicules engagés). | Coordonnées GPS exactes (infra-communal) | 2017 – 2026 (10 ans) | Quotidien (mise à jour à J+1) | Département du Rhône (69) et bordures limitrophes |
| **Q3 (Feux naturels & Foudre)** | Impacts de foudre au sol géolocalisés croisés avec les précipitations associées (détection de foudre sèche). | Point kilométrique (< 500 m) | 2017 – 2026 | Horaire / Temps réel | Auvergne-Rhône-Alpes |
| **Q4 & Q5 (Indice Météo & Découpage)** | Indices IFM complets (FFMC, DMC, DC, ISI, BUI) et paramètres météo bruts (température, vent instantané/rafales, humidité relative). | Maille fine (Zonage Météo-France ou grille 8x8 km SAFRAN) | 2017 – 2026 | Prévision à J-1 et J-2 (mise à jour 2x/jour) | Région AURA + Référentiel France entière |
| **Q6 (Effet mémoire & Sécheresse des sols)** | Indice d'humidité du sol profond et évapotranspiration réelle (modèle SIM2 Météo-France). | Maille 8 km | 2015 – 2026 | Hebdomadaire glissante | Rhône et Auvergne-Rhône-Alpes |
| **Q7 & Q8 (Coûts & Capacité Dispositif Renforcé)** | Barème des indemnités horaires de garde SPV/SPP, coût kilométrique des CCF, historique des jours d'activation passés. | Par centre de secours (CIS) | 2024 – 2026 | Annuel / Post-campagne | SDMIS 69 |
| **Q10 (Délai d'accès & Vulnérabilité)** | Isochrones de temps de trajet des engins pompiers sur le réseau routier et forestier + géolocalisation des points d'eau DECI. | Tronçon de route / PEI | Référentiel 2026 | Mise à jour mensuelle | Département du Rhône (69) |
| **Q11 (Combustible & Pente)** | Types de peuplements forestiers (BD Forêt v2), parcelles agricoles (RPG), et modèle numérique de pente et d'exposition au soleil. | Parcelle / Pixel 5 m (RGE ALTI) | Dernière version disponible (IGN 2024-2026) | Statique (mise à jour pluriannuelle) | Massifs du Rhône et région AURA |
| **Q12 (Benchmark National)** | Nombre de feux et surfaces brûlées normalisés par hectare boisé et par habitant. | Départemental (96 départements) | 2010 – 2026 | Annuel | France métropolitaine |
