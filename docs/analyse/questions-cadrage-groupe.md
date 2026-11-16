# Référentiel Complet de Questions Maturées (Cadrage Professeur, Commanditaire SDMIS 69 & Brainstorming Équipe)

> [!IMPORTANT]
> Ce document conserve **100 % des questions précédentes mot pour mot** et **élargit le spectre d'investigation à 7 grands axes** pour couvrir l'ensemble de l'écosystème :
> 1. **Périmètre Métier, Causes Naturelles vs Humaines & Typologie des Sinistres**
> 2. **Déconstruction Scientifique de l'Indice « Météo des Forêts » (IFM) & Granularité**
> 3. **Nature, Écologie Forestière, Biodiversité & Bilan Carbone**
> 4. **Modèle Économique, Financier, Contrainte Humaine (SPP/SPV) & « Dispositif Renforcé »**
> 5. **Gouvernance des Données (0-Party, 1st-Party, 2nd-Party, 3rd-Party) & Sources Scientifiques**
> 6. **Systèmes d'Information Existants du SDMIS, Contraintes Administratives & Légales (SDACR, OLD, DFCI)**
> 7. **Projection vers la Solution Finale (Architecture Cible, Aide à la Décision & Adoption Terrain)**

---

## Axe 1 — Périmètre Métier, Typologie des Sinistres & Causes Naturelles vs Humaines

1. **Périmètre des feux couverts (Forêt stricte vs Espaces naturels & Périurbains)** :
   *Le SDMIS 69 couvre un territoire très contrasté (Métropole de Lyon périurbaine, zones agricoles de moissons, massifs des Monts du Lyonnais et du Beaujolais). Le SDMIS 69 couvre-t-il uniquement les feux de forêts au sens strict (massifs boisés / BDIFF), ou également les feux d'espaces naturels, périurbains et agricoles (friches, chaumes, broussailles) qui sont fréquents dans la périphérie lyonnaise, mobilisent les mêmes moyens et menacent directement les interfaces habitat-forêt ?*

2. **Définition d'un « feu significatif » pour le SDMIS** :
   *Quand les chefs de centre parlent de « feux partis des jours où l'indice était au plus bas », s'agit-il de tout départ de feu (même maîtrisé à moins de $100\text{ m}^2$) ou uniquement des feux ayant dépassé un certain seuil de surface parcourue ou de moyens engagés ? Quel est le critère de gravité prioritaire pour la Direction : le **nombre d'éclosions** ou la **surface/menace sur le bâti** ?*

3. **Mesure des feux d'origine naturelle et facteurs biophysiques d'éclosion** :
   *Selon Géorisques et le CGDD, 1 feu sur 10 au niveau national est d'origine naturelle (foudre), mais de nombreux départs et embrasements éclairent aussi des mécanismes biophysiques critiques indépendamment d'une action humaine directe (impacts de foudre sèche lors d'orages d'été, dessèchement extrême de la litière végétale, stress hydrique cumulé des sols, topographie et exposition solaire Sud/Sud-Ouest, couloirs de vent du Rhône). Comment isoler ces feux naturels dans les données historiques, et quels paramètres biophysiques locaux devons-nous prioriser pour capter ces éclosions que l'indice météo global ne voit pas ?*

4. **Qualification de la zone des « 50 mètres » et interfaces Habitat-Forêt (WUI)** :
   *Les études nationales (Géorisques) montrent que la majorité des feux se déclenchent à moins de 50 mètres des habitations ou le long des axes (routes, voies ferrées, lignes électriques). Le SDMIS 69 dispose-t-il d'une qualification précise des causes d'éclosion dans ses rapports d'intervention pour séparer l'aléa naturel pur de l'aléa d'interface anthropique ?*

---

## Axe 2 — Déconstruction Scientifique de l'Indice « Météo des Forêts » & Granularité

5. **Nature et granularité de l'indicateur utilisé actuellement** :
   *La Direction se réfère-t-elle à l'indicateur grand public de Météo-France (carte publique « Météo des forêts » diffusée de juin à septembre, échelle agrégée de 1 à 4 / vert, jaune, orange, rouge au niveau départemental) ou aux sous-indices techniques de l'**IFM (Indice Forêt Météo / Fire Weather Index - FWI)** calculés par Météo-France par zone météo ou massif ? Avons-nous la liberté de reconstruire ou d'hybrider cet indice avec des données à maille fine (ex. humidité des sols SIM2 à 8 km, vitesse du vent local, indice de sécheresse) ?*

6. **Distinction scientifique entre « Inflammabilité » (Éclosion) et « Combustibilité » (Propagation)** :
   *Les travaux de l'INRAE distinguent l'**inflammabilité** (capacité de la litière fine à s'enflammer à la moindre étincelle, régie par le code d'humidité des combustibles fins **FFMC**) et la **combustibilité** (capacité de la biomasse lourde à propager un grand feu, régie par la sécheresse profonde **DC/DMC** et le vent **ISI**). L'erreur actuelle du seuil SDMIS ne vient-elle pas du fait qu'on utilise un indice de propagation globale (IFM) pour prédire des éclosions rapides d'herbes sèches (FFMC) ?*

7. **Échelle géographique d'arbitrage des moyens** :
   *Pour la question « où concentrer nos moyens », quelle est la maille opérationnelle de décision du SDMIS 69 : le **Groupement territorial**, le **secteur de premier appel d'un Centre d'Incendie et de Secours (CIS)**, la **commune**, ou le **massif forestier / Zonage Météo-France (ZMF)** ?*

8. **Cinétique temporelle, effet mémoire et allongement de la saison feux** :
   *Les chefs de centre constatent des feux les jours où l'indice est au plus bas. Est-ce lié à un décalage temporel de l'indice (ex. une pluie fine en surface fait chuter l'indice du jour, alors que la biomasse profonde ou les herbes fines restent prêtes à s'enflammer avec le vent) ? De plus, avec le dérèglement climatique (saison qui déborde au printemps et à l'automne hors de la période juin-septembre de la Météo des forêts), faut-il étendre le suivi de mars à novembre sur une fenêtre glissante (J-7, J-15) ?*

---

## Axe 3 — Nature, Écologie Forestière, Biodiversité & Vulnérabilité Environnementale

9. **Typologie du combustible végétal et mortalité forestière (Dépérissement climatique)** :
   *Dans le Rhône et en AURA, les sécheresses successives (depuis 2022-2026) ont provoqué un dépérissement massif de certaines essences (bois mort sur pied, scolytes sur les résineux, landes ligneuses, friches). Comment intégrer l'état sanitaire réel de la végétation (via la **BD Forêt IGN**, l'ONF ou l'indice satellitaire de verdissement **NDVI Copernicus**) pour identifier les massifs devenus de véritables « poudrières » écologiques ?*

10. **Priorisation écologique et sanctuarisation de la biodiversité** :
    *Au-delà de la protection des vies humaines et du bâti, un incendie détruit des écosystèmes rares (zones Natura 2000, ZNIEFF, forêts anciennes qui mettent 50 ans à se régénérer), pollue les captages d'eau potable par les cendres et relâche massivement du $\text{CO}_2$. Le SDMIS 69 intègre-t-il une « valeur écologique et environnementale » des massifs dans sa matrice de priorisation des moyens ?*

11. **Continuité écologique des massifs vs coupures de combustible** :
    *Les études montrent que la continuité des formations végétales inflammables favorise les grands incendies (> 20 ha), tandis que la mosaïque agricole ou les coupures DFCI les ralentissent. Disposons-nous de la cartographie des aménagements préventifs (bandes débroussaillées, pistes forestières, coupures vertes) et du taux d'application des **OLD (Obligations Légales de Débroussaillement à 200 m)** dans le Rhône ?*

---

## Axe 4 — Modèle Économique, Financier, Contrainte Humaine & « Dispositif Renforcé »

12. **Moyens d'action et fonction de coût (Faux-Positif vs Faux-Négatif)** :
    *On ne peut pas mobiliser des pompiers et des moyens humains partout et en permanence pour chaque alerte. Quels sont les coûts ou contraintes associés au déclenchement d'un dispositif renforcé (astreintes, patrouilles préventives mobiles, guet, surveillance à distance par vigie/caméras/drones) afin d'évaluer la fonction de coût d'un **faux-positif** (mobilisation coûteuse à vide, fatigue opérationnelle des effectifs) vs un **faux-négatif** (départ de feu sans pré-positionnement) ?*

13. **Structure des effectifs (SPP vs SPV) et coût marginal d'une garde postée** :
    *Le SDMIS 69 repose sur un équilibre entre Sapeurs-Pompiers Professionnels (SPP) et Volontaires (SPV, dont la disponibilité dépend de leurs employeurs respectifs en semaine et des vacations horaires indemnisées). Quel est le coût financier et humain réel d'une journée de dispositif renforcé (indemnités de garde SPV, heures supplémentaires SPP, carburant des CCF - Camions Citernes Feux de Forêts) et quelle est la limite capacitaire de mobilisation simultanée ?*

14. **Gradation et plafond budgétaire du dispositif renforcé** :
    *Le déclenchement du dispositif renforcé est-il binaire (Activé / Non activé sur tout le département) ou gradué (ex. Niveau 1 : veille technologique / caméras / satellites ; Niveau 2 : guet aérien ou patrouilles ciblées SPV/ONF ; Niveau 3 : gardes postées GIFF en caserne et pré-positionnement sur le terrain) ? Disposons-nous d'un ordre de grandeur du budget annuel ou du nombre maximum de « journées-dispositif » que le SDMIS 69 peut financer sur l'été 2027 ?*

15. **Coût économique et financier évité (ROI de la prévention)** :
    *Pour justifier les arbitrages financiers auprès du Conseil d'Administration du SDMIS (Métropole de Lyon et Département du Rhône), pouvons-nous modéliser le **coût d'un grand feu non maîtrisé à l'éclosion** (coût d'engagement d'une colonne de renfort, largages aériens Dash/Canadair de la Sécurité Civile, pertes sylvicoles/agricoles/immobilières) par rapport au coût préventif d'un pré-positionnement ciblé ?*

16. **Effet d'atténuation du dispositif (Biais d'observation / Paradoxe de la prévention)** :
    *Lorsque l'indice est très élevé et qu'aucun feu majeur ne se déclare, est-il possible que ce soit justement **grâce** au dispositif préventif déployé (dissuasion par les patrouilles, arrêtés préfectoraux d'interdiction d'accès aux massifs, extinction immédiate des départs naissants) ? Avons-nous l'historique des jours où le dispositif renforcé a été activé en 2025/2026 pour corriger ce biais statistique ?*

---

## Axe 5 — Gouvernance des Données (0P, 1st, 2nd, 3rd Party), Qualité & Benchmarking

17. **Cartographie des sources par typologie (Zero, First, Second, Third-Party Data)** :
    *Pour structurer notre catalogue de données et notre matrice « Questions $\times$ Sources », quelle est l'accessibilité réelle des différentes strates de données pour le projet :*
    * **First-Party Data (1P — Interne SDMIS 69)** : Historique fin des interventions (SGA/Systel), géolocalisation exacte des départs, moyens engagés, localisation des casernes (CIS) et des Points d'Eau Incendie (PEI / base REMOCRA).
    * **Second-Party Data (2P — Partenaires institutionnels directs)** : Données fines **Météo-France** par massif (IFM expert, humidité des sols SIM2), données **ONF / DRAAF** (vigies, DFCI), Préfecture (arrêtés).
    * **Third-Party Data (3P — Open Data, Satellites & Recherche)** : **BDIFF / Prométhée**, **IGN** (BD Forêt, BD TOPO, RGE ALTI), **NASA FIRMS / VIIRS & Copernicus EFFIS** (points chauds satellites temps réel comme dans l'application open-source *FEUX FRANCE*), **INSEE** (densité population exposée), **Météorage** (impacts de foudre).
    * **Zero-Party Data (0P — Signalements citoyens & Terrain)** : Remontées directes des chefs de centre, appels 18/112 géolocalisés, signalements citoyens ou forestiers.

18. **Croisement avec des sources exogènes et validation scientifique** :
    *Confirmez-vous que cette approche hybride (croisant BDIFF/Météo avec les modèles scientifiques INRAE sur le stress hydrique, la topographie IGN et la télédétection satellitaire) est bien celle attendue pour construire notre inventaire, notre graphe de concepts et notre entrepôt de données ?*

19. **Périmètre du Benchmark Régional (AURA) et National** :
    *Pour situer le Rhône (69) par rapport aux autres départements d'Auvergne-Rhône-Alpes (notamment l'Ardèche 07 et la Drôme 26 historiquement méditerranéens, l'Isère 38 ou l'Allier 03) et au territoire national (90 départements touchés dès 2022), préconisez-vous une analyse exhaustive des 96 départements métropolitains ou une comparaison par **clusters bioclimatiques** (départements continentaux/périurbains en transition climatique vs départements historiques du Sud-Est/Sud-Ouest) ?*

20. **Profondeur historique vs Rupture climatique (2022-2026)** :
    *Sur quelle période temporelle devons-nous entraîner et valider nos analyses ? Un historique long (15-20 ans) offre du volume statistique mais sous-estime le nouveau régime climatique observé depuis le choc de 2022 et l'été 2026 dans le Rhône.*

---

## Axe 6 — Systèmes Existants de l'Administration, Contraintes Légales & Opérationnelles

21. **Intégration dans l'écosystème logiciel existant du SDMIS 69** :
    *Quels sont les outils métiers actuellement utilisés par la chaîne de commandement (CODIS / État-Major) du SDMIS 69 : système de gestion opérationnelle (**Systel / Artémis** ou migration vers **Nexsis 18-112**), SIG départemental (ArcGIS / QGIS), plateforme de gestion des points d'eau (**REMOCRA**) ? Sous quel format notre solution devra-t-elle s'interfacer pour ne pas créer un outil en silo de plus ?*

22. **Cadre réglementaire et administratif (SDACR, Ordre d'Opération Feux de Forêts, PFCI)** :
    *Les décisions du SDMIS s'inscrivent dans des documents cadres stricts : le **SDACR** (Schéma Départemental d'Analyse et de Couverture des Risques), le **PPFCI** (Plan de Protection des Forêts Contre les Incendies) et l'**Ordre Départemental d'Opération Feux de Forêts** arrêté chaque printemps avec le Préfet. À quel moment du cycle décisionnel administratif nos recommandations doivent-elles s'insérer (révision annuelle des seuils au printemps pour l'Ordre d'Opération, ET aide au déclenchement quotidien à J-1 / J-2 à 17h lors du briefing météo de l'État-Major) ?*

23. **Contraintes de conformité, souveraineté et RGPD** :
    *Quelles sont les règles de confidentialité et de conformité attendues par l'administration (anonymisation des adresses précises d'intervention ou des propriétaires de parcelles, hébergement souverain SecNumCloud / Open Source, explicabilité des algorithmes pour qu'un officier supérieur puisse justifier légalement sa décision devant le Préfet) ?*

---

## Axe 7 — Projection vers la Solution Finale (Vers quoi on se projette le 11 décembre et au-delà)

24. **Nature du livrable décisionnel attendu par la Direction du SDMIS** :
    *Pour répondre pleinement au besoin d'arbitrage de la Direction, quelle est la forme idéale de la solution cible vers laquelle nous devons nous projeter :*
    * **Un modèle de nouveau seuil composite (« Indice Risque Opérationnel SDMIS 69 »)** qui corrige la Météo des forêts en intégrant la sécheresse locale, la végétation, la pente et le délai d'intervention des casernes ?
    * **Une matrice d'allocation spatiale et budgétaire** identifiant les secteurs prioritaires où pré-positionner les moyens humains/financiers et ceux où privilégier la détection automatisée (caméras/satellites/drones) ?
    * **Un simulateur / tableau de bord d'aide à la décision (OAD)** permettant à l'État-Major de tester différents seuils de déclenchement et de visualiser en direct l'impact sur le budget consommé vs le taux de couverture des feux réels ?

25. **Explicabilité (« White-Box ») et adoption par les chefs de centre** :
    *La commande souligne une défiance des chefs de centre envers l'indice actuel. Pour que notre futur modèle soit accepté sur le terrain, ne doit-il pas être totalement transparent et explicable (ex. afficher clairement pourquoi tel secteur passe en alerte : « Indice météo modéré MAIS herbes sèches + vent du Sud 50 km/h + temps d'accès caserne > 18 min ») plutôt qu'une boîte noire statistique ?*
