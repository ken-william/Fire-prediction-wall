# Cadrage Analytique & Fiches Descriptives des Sources — Auvergne-Rhône-Alpes (SDMIS 69)

Ce document formalise le cadrage analytique des questions de décision et l'inventaire des sources de données pour la préparation de la saison feux 2027 dans le département du Rhône (SDMIS 69) et en région Auvergne-Rhône-Alpes.

---

## 1. Questions de Cadrage Stratégique

| IDENTIFIANT | Questionnement modal | Décision rendue possible | Objectif / Règle d'arbitrage |
| :--- | :--- | :--- | :--- |
| **Q1** | Quels territoires du Rhône et d'Auvergne-Rhône-Alpes présentent la plus forte fréquence de départs de feu, rapportée à leur exposition forestière ? | Localisation des patrouilles préventives et du guet armé sur les massifs critiques (Beaujolais, Monts du Lyonnais, lisières périurbaines). | Évite de classer les territoires sur des volumes bruts seulement : normalise le nombre de feux par surface boisée réelle (ha). |
| **Q2** | Quelle proportion des journées avec départ de feu serait couverte par chaque seuil de la Météo des forêts ? | Définition du niveau minimal de déclenchement du dispositif renforcé (Jaune, Orange ou Rouge). | Mesure les journées avec événement réel qui échappaient au dispositif (taux de faux négatifs / feux non couverts). |
| **T3** | Combien de journées de dispositif renforcé chaque seuil entraînerait-il, y compris sans départ de feu ? | Choix d'un seuil compatible avec le budget d'astreinte et la disponibilité des sapeurs-pompiers (SPP et SPV). | Rendre visible le compromis économique entre couverture des risques et mobilisation à vide (taux de faux positifs). |
| **Q4** | Les résultats obtenus dans le Rhône sont-ils stables dans le temps et cohérents avec ceux des autres départements d'Auvergne-Rhône-Alpes et de France ? | Choix entre un seuil local propre au Rhône ou une différenciation territoriale régionale (Ardèche, Drôme, Isère, etc.). | Vérifiez que la recommandation ne dépend pas d'une année atypique (ex. sécheresse record de 2022 ou été 2026). |

---

## 2. Deux Questions Opérationnelles Validées

Ces questions complètent les quatre questions de cadrage sans préjuger de la disponibilité des données internes du SDMIS 69 :

| IDENTIFIANT | Questionnement modal | Décision rendue possible | Données idéales et limites |
| :--- | :--- | :--- | :--- |
| **Q5** | Dans quels secteurs les délais d'arrivée et les capacités de première intervention sont-ils insuffisants au regard des besoins ? | Prépositionner des équipes mobiles, réorganiser la couverture territoriale ou renforcer un Centre d'Incendie et de Secours (CIS). | Horodatages des interventions réelles, géolocalisation des casernes CIS, délais de transit (isochrones), effectifs de garde ; accès aux données internes SDMIS à confirmer. |
| **Q6** | Quels effectifs, compétences et engins (CCF / GIFF) seraient nécessaires pour répondre à plusieurs départs de feu simultanés pendant les journées de danger élevé ? | Dimensionner les réserves de garde, les colonnes de renfort départementales et les équipements prioritaires sous contrainte de simultanéité. | Disponibilités opérationnelles des SPV/SPP, qualifications Feux de Forêts (FDF), parc de Camions Citernes Feux de Forêts (CCF), coûts de garde et scénarios de départs simultanés ; accès interne non vérifié. |

---

## 3. Validation de Pertinence Analytique (Revue Méthodologique)

Les six questions retenues ont chacune un scénario d'arbitrage explicite :
- **Q1 et Q5** éclairent l'**allocation territoriale** (où déployer les moyens humains et matériels en priorité).
- **Q2 et T3** éclairent le **seuil d'activation et son coût de mobilisation** (arbitrage entre sécurité opérationnelle et contrainte budgétaire).
- **Q4** garantit la **robustesse des comparaisons** territoriales et temporelles (benchmarking Rhône vs AURA vs France).
- **Q6** cadre le **dimensionnement capacitaire des moyens** face au risque de saturation opérationnelle en cas de feux concomitants.

Le cadrage est validé pour la coordination ; l'inventaire des sources de données ci-dessous établit l'opportunité et la faisabilité des analyses.

---

## 4. Fiches Descriptives des Sources de Données (Auvergne-Rhône-Alpes)

### Source 1 : Base de Données sur les Incendies de Forêts en France (BDIFF)
- **Producteur** : Institut National de l'Information Géographique et Forestière (IGN), Ministère de l'Agriculture et de la Souveraineté Alimentaire, Ministère de l'Intérieur.
- **Portails d'accès** :
  - Observatoire des forêts françaises : https://observatoire.foret.gouv.fr/catalogue/base-de-donnees-sur-les-incendies-de-forets-en-france
  - Thématique feux de forêt : https://observatoire.foret.gouv.fr/themes/l-historique-des-feux-de-foret-en-france-metropolitaine
  - Jeu de données data.gouv.fr : https://www.data.gouv.fr/datasets/base-de-donnees-sur-les-incendies-de-forets-en-france-bdiff
- **Description & Périmètre** : Centralise l'historique national des incendies de forêt depuis 2006. Chaque enregistrement renseigne la commune, le département (ex. Rhône 69 et départements AURA), la date et l'heure de première alerte, la surface brûlée totale (en ha), la surface boisée touchée, le type de formation végétale et la cause d'éclosion présumée (foudre, accident, malveillance, indéterminée).
- **Couverture géographique** : France métropolitaine, filtre direct possible sur le code région 84 (Auvergne-Rhône-Alpes) et les départements (01, 03, 07, 15, 26, 38, 42, 43, 63, 69, 73, 74).
- **Questions alimentées** : Q1, Q2, Q4.

### Source 2 : Archives et API de la Météo des Forêts
- **Producteur** : Météo-France.
- **Portails d'accès** :
  - Jeu de données data.gouv.fr : https://www.data.gouv.fr/datasets/archives-de-la-meteo-des-forets
  - API officielle Météo des forêts : https://www.data.gouv.fr/dataservices/api-meteo-des-forets
- **Description & Périmètre** : Historique quotidien des niveaux officiels de danger de feu de forêt diffusés chaque jour de juin à septembre depuis 2023. Les niveaux sont codifiés de 1 à 4 : Vert (Faible), Jaune (Modéré), Orange (Élevé), Rouge (Très élevé), calculés par département à partir des conditions atmosphériques et de l'Indice Forêt Météo (IFM).
- **Questions alimentées** : Q2, T3, Q4.

### Source 3 : Référentiel des Forêts et Taux de Boisement (IGN — Observatoire des Forêts)
- **Producteur** : IGN (Inventaire Forestier National & BD Forêt).
- **Portails d'accès** :
  - Observatoire des forêts françaises (territoires) : https://observatoire.foret.gouv.fr/mon-territoire?territoireCode=84&territoireLevel=RAD13&compareCode=France&compareLevel=FRA
- **Description & Périmètre** : Fournit la superficie forestière (2 646 000 ha en Auvergne-Rhône-Alpes, soit un taux de boisement régional moyen de 38 %), ventilée par département, établissement public de coopération intercommunale (EPCI) et commune. Permet de distinguer la surface des massifs du Rhône (Monts du Lyonnais, Beaujolais) et les essences principales (feuillus, conifères, landes).
- **Questions alimentées** : Q1 (normalisation de la fréquence d'éclosion par hectare boisé).

### Source 4 : Dossier Expert & Synthèse Nationale des Risques (notre-environnement.gouv.fr)
- **Producteur** : Commissariat Général au Développement Durable (CGDD) / Ministère de la Transition Écologique.
- **Portail d'accès** :
  - Article risques feux de forêts : https://www.notre-environnement.gouv.fr/themes/risques/article/les-feux-de-forets
- **Description & Périmètre** : Référentiel national consolidé précisant la typologie des causes d'incendie (90 % anthropiques, 10 % d'origine naturelle par foudre), la distribution spatiale des éclosions (majorité à moins de 50 m des habitations en interface habitat-forêt WUI), la liste des communes déclarées exposées par les préfets (Auvergne-Rhône-Alpes concentrant avec 4 autres régions du Sud 90 % des communes exposées), et les bilans pluriannuels comparatifs.
- **Questions alimentées** : Q1, Q4, cadrage des causes naturelles vs anthropiques.

### Source 5 : Données d'Intervention & Opérationnelles SDMIS 69 (First-Party Data)
- **Producteur** : SDMIS 69 (Service Départemental-Métropolitain d'Incendie et de Secours du Rhône) / Plateforme REMOCRA.
- **Portails d'accès** :
  - Base opérationnelle interne (GDO / Systel / Nexsis 18-112)
  - Plateforme collaborative DECI : https://remocra.atolcd.com/
- **Description & Périmètre** : Registre d'intervention détaillé : horodatages précis (appel 18/112, départ engin, arrivée sur les lieux, extinction), localisation infra-communale, engins engagés (FPT, Camions Citernes Feux de Forêts CCF, Groupe d'Intervention Feux de Forêts GIFF), effectifs mobilisés et réseau des Points d'Eau Incendie (hydrants, citernes forestières).
- **Questions alimentées** : Q5, Q6 (faisabilité conditionnée à l'ouverture des extraits anonymisés par le SDMIS 69).

---

## 5. Matrice Sources × Questions (Auvergne-Rhône-Alpes / SDMIS 69)

Ce tableau croise chaque question avec les sources de données mobilisées, les indicateurs extraits et les réponses opérationnelles concrètes apportées à la Direction :

| IDENTIFIANT | Questionnement modal | Sources primaires mobilisées | Indicateurs & variables extraites | Réponses et arbitrages opérationnels apportés |
| :--- | :--- | :--- | :--- | :--- |
| **Q1** | Fréquence des départs rapportée à l'exposition forestière (Rhône / AURA) | BDIFF (data.gouv.fr) + BD Forêt / Inventaire IGN (Observatoire des forêts) | Nombre d'éclosions historiques par commune / massif ; Surface forestière communale (ha) ; Ratio : $\frac{\text{Nombre de feux}}{\text{1 000 ha de forêt}}$. | Cartographie des zones prioritaires dans le Rhône (massif du Beaujolais, Monts du Lyonnais, frange périurbaine lyonnaise). Arbitrage : affectation ciblée des patrouilles mobiles de surveillance sur les zones à fort ratio feux/surface plutôt que sur les massifs les plus vastes mais peu touchés. |
| **Q2** | Proportion des journées feux couvertes par chaque seuil Météo des forêts | BDIFF (dates et heures d'alerte dans le Rhône 69) + Archives Météo des forêts (Météo-France) | Niveau d'alerte quotidien (Vert, Jaune, Orange, Rouge) croisé avec les jours où un départ de feu réel est survenu en 2023-2026. | Calcul de la matrice de couverture : identification du pourcentage de feux réels survenus lors de journées classées Vertes ou Jaunes. Décision : détermination du seuil plancher d'activation du dispositif renforcé (ex. déclenchement dès l'indice Jaune si 40 % des feux du Rhône partent en niveau Jaune). |
| **Q3 (T3)** | Nombre de journées de mobilisation renforcée entraînées par seuil | Archives Météo des forêts + Données budgétaires / barèmes d'indemnisation SDMIS | Décompte annuel des jours classés Vert, Jaune, Orange, Rouge dans le Rhône ; Coût moyen d'une journée de mobilisation renforcée (heures de garde SPV/SPP, carburant CCF). | Révèle le coût budgétaire total par niveau : par exemple, un seuil Jaune entraîne 55 jours de mobilisation par été (hors budget), tandis qu'un seuil Orange en entraîne 18, compatible avec l'enveloppe budgétaire du SDMIS 69. |
| **Q4** | Stabilité temporelle et cohérence Rhône vs AURA vs France | BDIFF nationale (2006-2026) + notre-environnement.gouv.fr + Météo des forêts AURA | Fréquence annuelle des feux et surfaces brûlées sur 10-20 ans ; Comparaison Rhône (69) vs Ardèche (07), Drôme (26), Loire (42) et moyenne nationale. | Vérifie si la saison 2026 est une anomalie climatique ou une tendance structurelle. Décision : arbitrage entre un seuil de déclenchement aligné sur le zonage régional AURA ou une calibration spécifique au microclimat du couloir rhodanien. |
| **Q5** | Secteurs à délais d'arrivée et capacité de première intervention insuffisants | Données opérationnelles SDMIS (GDO/Systel) + Réseau routier/forestier IGN + Plateforme REMOCRA | Délais de route réels et isochrones d'accès (> 15-20 min) depuis les casernes CIS ; Répartition des Points d'Eau Incendie (PEI). | Identification des « zones blanches » opérationnelles éloignées des casernes et dépourvues de points d'eau dans les massifs du 69. Décision : pré-positionnement tactique d'engins CCF sur des vigies avancées pour garantir une attaque du feu à moins de 10 minutes. |
| **Q6** | Dimensionnement des effectifs, compétences et engins face aux départs simultanés | Main courante SDMIS (interventions concomitantes) + Tableau des effectifs de garde SPP/SPV | Nombre maximal de feux actifs simultanés enregistrés lors des journées d'indice élevé ; Nombre de CCF mobilisables sans dégarnir la couverture secours d'urgence. | Fixe la jauge de sécurité opérationnelle : calcul du nombre de Groupes d'Intervention Feux de Forêts (GIFF) à placer en astreinte pour être capable de traiter 3 départs simultanés sans recours immédiat aux colonnes de renfort extérieures. |
