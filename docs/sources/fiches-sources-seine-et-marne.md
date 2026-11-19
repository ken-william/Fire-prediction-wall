# Cadrage Analytique & Fiches Descriptives des Sources — Seine-et-Marne (SDIS 77)

Ce document formalise le cadrage analytique des questions de décision et l'inventaire des sources de données pour la préparation de la saison feux 2027 dans le département de Seine-et-Marne (SDIS 77) et en région Île-de-France.

---

## 1. Questions de Cadrage Stratégique

| IDENTIFIANT | Questionnement modal | Décision rendue possible | Objectif / Règle d'arbitrage |
| :--- | :--- | :--- | :--- |
| **Q1** | Quels territoires de Seine-et-Marne présentent la plus forte fréquence de départs de feu, rapportée à leur exposition forestière ? | Localisation des patrouilles préventives et du guet armé sur les massifs critiques (massif de Fontainebleau, forêts de Crécy, Villefermoy, lisières périurbaines et plaines de la Brie). | Évite de classer les territoires sur des volumes bruts seulement : normalise le nombre de feux par surface boisée réelle (ha). |
| **Q2** | Quelle proportion des journées avec départ de feu serait couverte par chaque seuil de la Météo des forêts ? | Définition du niveau minimal de déclenchement du dispositif renforcé (Jaune, Orange ou Rouge). | Mesure les journées avec événement réel qui échappaient au dispositif (taux de faux négatifs / feux non couverts). |
| **T3** | Combien de journées de dispositif renforcé chaque seuil entraînerait-il, y compris sans départ de feu ? | Choix d'un seuil compatible avec le budget d'astreinte et la disponibilité des sapeurs-pompiers (SPP et SPV). | Rendre visible le compromis économique entre couverture des risques et mobilisation à vide (taux de faux positifs). |
| **Q4** | Les résultats obtenus en Seine-et-Marne sont-ils stables dans le temps et cohérents avec ceux des autres départements d'Île-de-France et de France ? | Choix entre un seuil local propre à la Seine-et-Marne ou une différenciation territoriale régionale (Essonne, Yvelines, Val-d'Oise, etc.). | Vérifiez que la recommandation ne dépend pas d'une année atypique (ex. sécheresses records de 2022 ou été 2026). |

---

## 2. Deux Questions Opérationnelles Validées

Ces questions complètent les quatre questions de cadrage sans préjuger de la disponibilité des données internes du SDIS 77 :

| IDENTIFIANT | Questionnement modal | Décision rendue possible | Données idéales et limites |
| :--- | :--- | :--- | :--- |
| **Q5** | Dans quels secteurs les délais d'arrivée et les capacités de première intervention sont-ils insuffisants au regard des besoins ? | Prépositionner des équipes mobiles, réorganiser la couverture territoriale ou renforcer un Centre d'Incendie et de Secours (CIS). | Horodatages des interventions réelles, géolocalisation des casernes CIS du 77, délais de transit (isochrones), effectifs de garde ; accès aux données internes SDIS 77 à confirmer. |
| **Q6** | Quels effectifs, compétences et engins (CCF / GIFF) seraient nécessaires pour répondre à plusieurs départs de feu simultanés pendant les journées de danger élevé ? | Dimensionner les réserves de garde, les colonnes de renfort départementales et les équipements prioritaires sous contrainte de simultanéité. | Disponibilités opérationnelles des SPV/SPP en Île-de-France, qualifications Feux de Forêts (FDF), parc de Camions Citernes Feux de Forêts (CCF), coûts de garde et scénarios de départs simultanés ; accès interne non vérifié. |

---

## 3. Validation de Pertinence Analytique (Revue Méthodologique)

Les six questions retenues ont chacune un scénario d'arbitrage explicite :
- **Q1 et Q5** éclairent l'**allocation territoriale** (où déployer les moyens humains et matériels en priorité).
- **Q2 et T3** éclairent le **seuil d'activation et son coût de mobilisation** (arbitrage entre sécurité opérationnelle et contrainte budgétaire).
- **Q4** garantit la **robustesse des comparaisons** territoriales et temporelles (benchmarking Seine-et-Marne vs Île-de-France vs France).
- **Q6** cadre le **dimensionnement capacitaire des moyens** face au risque de saturation opérationnelle en cas de feux concomitants (feux de moissons en plaine + feu de massif à Fontainebleau).

Le cadrage est validé pour la coordination ; l'inventaire des sources de données ci-dessous établit l'opportunité et la faisabilité des analyses.

---

## 4. Fiches Descriptives des Sources de Données (Seine-et-Marne / 77)

### Source 1 : Base de Données sur les Incendies de Forêts en France (BDIFF)
- **Producteur** : Institut National de l'Information Géographique et Forestière (IGN), Ministère de l'Agriculture et de la Souveraineté Alimentaire, Ministère de l'Intérieur.
- **Portails d'accès** :
  - Observatoire des forêts françaises : https://observatoire.foret.gouv.fr/catalogue/base-de-donnees-sur-les-incendies-de-forets-en-france
  - Thématique feux de forêt : https://observatoire.foret.gouv.fr/themes/l-historique-des-feux-de-foret-en-france-metropolitaine
  - Jeu de données data.gouv.fr : https://www.data.gouv.fr/datasets/base-de-donnees-sur-les-incendies-de-forets-en-france-bdiff
- **Description & Périmètre** : Centralise l'historique national des incendies de forêt depuis 2006. Chaque enregistrement renseigne la commune, le département (code 77 pour la Seine-et-Marne), la date et l'heure de première alerte, la surface brûlée totale (en ha), la surface boisée touchée, le type de formation végétale et la cause d'éclosion présumée.
- **Couverture géographique** : France métropolitaine, filtre direct possible sur le département 77 (Seine-et-Marne) et la région 11 (Île-de-France).
- **Questions alimentées** : Q1, Q2, Q4.

### Source 2 : Archives et API de la Météo des Forêts
- **Producteur** : Météo-France.
- **Portails d'accès** :
  - Jeu de données data.gouv.fr : https://www.data.gouv.fr/datasets/archives-de-la-meteo-des-forets
  - API officielle Météo des forêts : https://www.data.gouv.fr/dataservices/api-meteo-des-forets
- **Description & Périmètre** : Historique quotidien des niveaux officiels de danger de feu de forêt diffusés chaque jour de juin à septembre depuis 2023. Les niveaux sont codifiés de 1 à 4 : Vert (Faible), Jaune (Modéré), Orange (Élevé), Rouge (Très élevé), calculés pour le département de Seine-et-Marne à partir des conditions atmosphériques et de l'Indice Forêt Météo (IFM).
- **Questions alimentées** : Q2, T3, Q4.

### Source 3 : Référentiel des Forêts et Taux de Boisement (IGN — Observatoire des Forêts)
- **Producteur** : IGN (Inventaire Forestier National & BD Forêt).
- **Portails d'accès** :
  - Observatoire des forêts françaises (territoires) : https://observatoire.foret.gouv.fr/mon-territoire
- **Description & Périmètre** : La Seine-et-Marne concentre plus de 140 000 ha d'espaces boisés, soit un taux de boisement de 24 % (représentant plus de 50 % de l'ensemble des forêts d'Île-de-France). Ce référentiel fournit la répartition fine par commune et massif forestier (massif de Fontainebleau avec 22 000 ha, forêts de Crécy, Villefermoy, Notre-Dame) et la part des essences (chênaies, pinèdes sur chaos gréseux, landes).
- **Questions alimentées** : Q1 (normalisation de la fréquence d'éclosion par hectare boisé).

### Source 4 : Dossier Expert & Synthèse Nationale des Risques (notre-environnement.gouv.fr)
- **Producteur** : Commissariat Général au Développement Durable (CGDD) / Ministère de la Transition Écologique.
- **Portail d'accès** :
  - Article risques feux de forêts : https://www.notre-environnement.gouv.fr/themes/risques/article/les-feux-de-forets
- **Description & Périmètre** : Référentiel national consolidé précisant la typologie des causes d'incendie (90 % anthropiques, 10 % d'origine naturelle par foudre), la distribution spatiale des éclosions (majorité à moins de 50 m des habitations en interface habitat-forêt WUI), la liste des communes déclarées exposées par les préfets et l'extension du risque d'incendie aux régions tempérées du nord de la France et d'Île-de-France sous l'effet du changement climatique.
- **Questions alimentées** : Q1, Q4, cadrage des causes naturelles vs anthropiques.

### Source 5 : Données d'Intervention & Opérationnelles SDIS 77 (First-Party Data)
- **Producteur** : SDIS 77 (Service Départemental d'Incendie et de Secours de Seine-et-Marne).
- **Portails d'accès** :
  - Base opérationnelle interne (GDO / Systel / Nexsis 18-112)
  - Cartographie départementale des Points d'Eau Incendie (DECI)
- **Description & Périmètre** : Registre d'intervention détaillé : horodatages précis (appel 18/112, départ engin, arrivée sur les lieux, extinction), localisation infra-communale, engins engagés (FPT, Camions Citernes Feux de Forêts CCF, Groupe d'Intervention Feux de Forêts GIFF), effectifs mobilisés et réseau des Points d'Eau Incendie (hydrants, mares, citernes forestières).
- **Questions alimentées** : Q5, Q6 (faisabilité conditionnée à l'ouverture des extraits anonymisés par le SDIS 77).

---

## 5. Matrice Sources × Questions (Seine-et-Marne / SDIS 77)

Ce tableau croise chaque question avec les sources de données mobilisées, les indicateurs extraits et les réponses opérationnelles concrètes apportées à la Direction du SDIS 77 :

| IDENTIFIANT | Questionnement modal | Sources primaires mobilisées | Indicateurs & variables extraites | Réponses et arbitrages opérationnels apportés |
| :--- | :--- | :--- | :--- | :--- |
| **Q1** | Fréquence des départs rapportée à l'exposition forestière (Seine-et-Marne) | BDIFF (data.gouv.fr) + BD Forêt / Inventaire IGN (Observatoire des forêts) | Nombre d'éclosions historiques par commune / massif ; Surface forestière communale (ha) ; Ratio : $\frac{\text{Nombre de feux}}{\text{1 000 ha de forêt}}$. | Cartographie des zones prioritaires dans le 77 (massif de Fontainebleau, lisières de Crécy/Villefermoy, interfaces périurbaines). Arbitrage : affectation ciblée des patrouilles de surveillance mobiles sur les massifs à fort ratio d'éclosion par hectare boisé. |
| **Q2** | Proportion des journées feux couvertes par chaque seuil Météo des forêts | BDIFF (dates et heures d'alerte en Seine-et-Marne) + Archives Météo des forêts (Météo-France) | Niveau d'alerte quotidien (Vert, Jaune, Orange, Rouge) croisé avec les jours où un départ de feu réel est survenu en 2023-2026. | Calcul de la matrice de couverture : identification du pourcentage de feux réels survenus lors de journées classées Vertes ou Jaunes. Décision : détermination du seuil plancher d'activation du dispositif renforcé pour éviter les feux non anticipés. |
| **Q3 (T3)** | Nombre de journées de mobilisation renforcée entraînées par seuil | Archives Météo des forêts + Données budgétaires / barèmes d'indemnisation SDIS 77 | Décompte annuel des jours classés Vert, Jaune, Orange, Rouge dans le 77 ; Coût moyen d'une journée de mobilisation renforcée (heures de garde SPV/SPP, carburant CCF). | Révèle le coût budgétaire total par niveau : par exemple, un seuil Jaune entraîne une sur-mobilisation hors budget, tandis qu'un seuil Orange permet d'optimiser l'enveloppe budgétaire du SDIS 77 sur les journées critiques d'été. |
| **Q4** | Stabilité temporelle et cohérence Seine-et-Marne vs Île-de-France vs France | BDIFF nationale (2006-2026) + notre-environnement.gouv.fr + Météo des forêts Île-de-France | Fréquence annuelle des feux et surfaces brûlées sur 10-20 ans ; Comparaison Seine-et-Marne (77) vs Essonne (91), Yvelines (78) et moyenne nationale. | Vérifie si les saisons intenses récentes sont des anomalies isolées ou une tendance structurelle de réchauffement en Île-de-France. Décision : arbitrage entre un seuil francilien global ou une règle spécifique au massif de Fontainebleau. |
| **Q5** | Secteurs à délais d'arrivée et capacité de première intervention insuffisants | Données opérationnelles SDIS 77 (GDO/Systel) + Réseau routier/forestier IGN + Référentiel DECI | Délais de route réels et isochrones d'accès (> 15-20 min) depuis les casernes CIS ; Répartition des Points d'Eau Incendie (PEI) et pistes forestières. | Identification des « zones blanches » opérationnelles éloignées des casernes et dépourvues de points d'eau dans les grands massifs du 77. Décision : pré-positionnement tactique d'engins CCF aux entrées de massif pour garantir une attaque du feu à moins de 10 minutes. |
| **Q6** | Dimensionnement des effectifs, compétences et engins face aux départs simultanés | Main courante SDIS 77 (interventions concomitantes) + Tableau des effectifs de garde SPP/SPV | Nombre maximal de feux actifs simultanés enregistrés lors des journées de moissons et de fortes chaleurs ; Nombre de CCF mobilisables sans fragiliser les secours d'urgence. | Fixe la jauge de sécurité opérationnelle : calcul du nombre de Groupes d'Intervention Feux de Forêts (GIFF) à maintenir disponibles pour être capable de traiter simultanément un feu de récolte en plaine et un départ de feu en cœur de forêt à Fontainebleau. |
