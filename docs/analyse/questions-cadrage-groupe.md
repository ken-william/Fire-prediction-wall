# Référentiel Complet de Questions Maturées (Cadrage Professeur, Commanditaire SDIS 77 & Brainstorming Équipe)

## Sommaire des Axes d'Analyse

1. **Périmètre Métier, Causes Naturelles vs Humaines & Typologie des Sinistres**
2. **Déconstruction Scientifique de l'Indice « Météo des Forêts » (IFM) & Granularité**
3. **Nature, Écologie Forestière, Biodiversité & Bilan Carbone**
4. **Modèle Économique, Financier, Contrainte Humaine (SPP/SPV) & « Dispositif Renforcé »**
5. **Gouvernance des Données (0-Party, 1st-Party, 2nd-Party, 3rd-Party) & Sources Scientifiques**
6. **Systèmes d'Information Existants du SDIS 77, Contraintes Administratives & Légales (SDACR, OLD, DFCI)**
7. **Projection vers la Solution Finale (Architecture Cible, Aide à la Décision & Adoption Terrain)**

---

## Axe 1 — Périmètre Métier, Typologie des Sinistres & Causes Naturelles vs Humaines

1. **Périmètre des feux couverts (Forêt stricte vs Espaces naturels, Chaumes & Périurbains)** :
   *La Seine-et-Marne (77) présente un paysage dual très contrasté : de grands massifs forestiers emblématiques (Fontainebleau, Crécy, Villefermoy, Armainvilliers) et d'immenses plaines céréalières en Brie. Le SDIS 77 couvre-t-il uniquement les feux de forêts au sens strict (BDIFF), ou également les feux d'espaces naturels, périurbains et agricoles (feux de récoltes, chaumes, friches, talus autoroutiers A4/A5/A6 et ferroviaires) qui mobilisent massivement les engins en juillet-août et menacent directement les lisières boisées ?*

2. **Définition d'un « feu significatif » pour le SDIS 77** :
   *Quand les chefs de centre de secours parlent de « feux partis des jours où l'indice était au plus bas », s'agit-il de tout départ de feu naissant (même maîtrisé à moins de $100\text{ m}^2$) ou uniquement des feux ayant dépassé un certain seuil de surface parcourue ou d'engins engagés ? Quel est le critère de gravité prioritaire pour la Direction : le **nombre d'éclosions** à étouffer immédiatement ou la **surface/menace sur les massifs sensibles et le bâti** ?*

3. **Mesure des feux d'origine naturelle et facteurs biophysiques d'éclosion** :
   *Si l'humain est le principal déclencheur en Île-de-France (mégots, barbecues sauvages, chantiers, travaux agricoles), des facteurs biophysiques et naturels déclenchent ou accélèrent brutalement les feux (orages avec foudre sèche en été, substrat sableux ultra-drainant et sec du massif de Fontainebleau, dessèchement critique de la lande à bruyères et des litières de résineux, vents de secteur Est/Nord-Est asséchants). Comment isoler ces causes naturelles dans les données historiques du 77 et quels paramètres biophysiques locaux prioriser pour capter les éclosions que l'indice départemental ne voit pas ?*

4. **Qualification de la zone des « 50 mètres » et interfaces Habitat-Forêt (WUI)** :
   *En Île-de-France, la pression urbaine crée un linéaire d'interface habitat-forêt très dense en lisière de massif. Les statistiques nationales (Géorisques) indiquent que la majorité des feux naissent à moins de 50 m du bâti ou des infrastructures. Le SDIS 77 dispose-t-il d'une qualification précise des causes et lieux d'éclosion dans ses rapports opérationnels pour séparer l'aléa de lisière périurbaine de l'aléa de cœur de massif forestier ?*

---

## Axe 2 — Déconstruction Scientifique de l'Indice « Météo des Forêts » & Granularité

5. **Nature et granularité de l'indicateur utilisé actuellement** :
   *La Direction se réfère-t-elle à l'indicateur grand public de Météo-France (carte « Météo des forêts », échelle départementale agrégée de 1 à 4 : Vert, Jaune, Orange, Rouge) ou aux sous-indices techniques de l'**IFM (Indice Forêt Météo / Fire Weather Index - FWI)** calculés par zone météo ? Avons-nous la liberté d'hybrider cet indice avec des données à maille fine (ex. humidité des sols superficiels et profonds SIM2 à 8 km, vent local, humidité relative horaire) ?*

6. **Distinction scientifique entre « Inflammabilité » (Éclosion) et « Combustibilité » (Propagation)** :
   *Les travaux de recherche (INRAE) distinguent l'**inflammabilité** (capacité des combustibles fins comme la bruyère, la paille ou les aiguilles de pin à s'enflammer à l'étincelle — code **FFMC**) et la **combustibilité** (capacité des strates organiques et du bois lourd à propager un grand feu — sécheresse profonde **DC/DMC** et vent **ISI**). L'inadéquation constatée du seuil actuel en Seine-et-Marne ne vient-elle pas de l'usage d'un indice de propagation lourde (IFM) pour surveiller des feux d'herbes et de récoltes ultra-rapides ?*

7. **Échelle géographique d'arbitrage des moyens** :
   *Pour la question « où concentrer nos moyens », quelle est la maille opérationnelle de décision du SDIS 77 : le **Groupement territorial** (Nord, Sud, Centre, Est), le **secteur de premier appel d'un Centre d'Incendie et de Secours (CIS)**, la **commune**, ou le **massif forestier** (ex. massif de Fontainebleau, forêt de Crécy) ?*

8. **Cinétique temporelle, effet mémoire et allongement de la saison feux** :
   *Les chefs de centre constatent des feux les jours où l'indice est bas. Est-ce dû à une pluie superficielle d'été qui fait chuter l'indice journalier alors que le sol profond et le sous-bois restent arides ? De plus, en Seine-et-Marne, avec des printemps chauds et des automnes secs, faut-il étendre le suivi sur une fenêtre glissante (J-7 / J-15) débordant de la période estivale classique de la Météo des forêts (juin-septembre) ?*

---

## Axe 3 — Nature, Écologie Forestière, Biodiversité & Vulnérabilité Environnementale

9. **Typologie du combustible végétal et vulnérabilité du massif de Fontainebleau** :
   *Le massif de Fontainebleau présente un sol siliceux/sableux exceptionnellement drainant, avec une végétation à haute combustibilité (pins sylvestres, landes à callune et fougère aigle) combinée à des feuillus (chênaies, hêtraies). Comment intégrer la composition fine des essences (via la **BD Forêt v2 IGN**) et l'indice de dessèchement foliaire par satellite (**NDVI / Sentinel-2**) pour repérer les zones de poudrière végétale ?*

10. **Sanctuarisation écologique et sites classés d'exception** :
    *La forêt de Fontainebleau est Réserve de Biosphère UNESCO, Forêt d'Exception, classée Natura 2000 et ZNIEFF, accueillant plus de 15 millions de visites annuelles. Les feux de forêt y causent une perte irréparable de biodiversité et détruisent des paysages patrimoniaux séculaires. Le SDIS 77 pondère-t-il la vulnérabilité environnementale et touristique dans sa priorisation des moyens ?*

11. **Continuité des massifs vs coupures agricoles et Obligations Légales de Débroussaillement (OLD)** :
    *Les coupures de combustible (routes, clairières, parcelles cultivées) et les pistes DFCI jouent un rôle décisif pour freiner la course d'un front de flammes. Dispose-t-on de la cartographie des aménagements DFCI et du taux de respect des **OLD (rayon de 50 m autour du bâti et 200 m des forêts)** en Seine-et-Marne ?*

---

## Axe 4 — Modèle Économique, Financier, Contrainte Humaine & « Dispositif Renforcé »

12. **Fonction de coût d'arbitrage (Faux-Positif vs Faux-Négatif)** :
    *On ne peut pas mobiliser des pompiers et des engins partout et en permanence sur un département de 5 915 km². Quels sont les coûts réels d'une journée de dispositif renforcé (indemnités de garde SPV, heures supplémentaires SPP, usure et carburant des Camions Citernes Feux de Forêts CCF) pour chiffrer précisément le compromis entre une **sur-mobilisation à vide** (coût budgétaire certain) et un **défaut d'anticipation** (sinistre majeur incontrôlé) ?*

13. **Structure des effectifs et disponibilité opérationnelle (SPP vs SPV en milieu francilien)** :
    *Le SDIS 77 repose sur une complémentarité entre sapeurs-pompiers professionnels (SPP) et volontaires (SPV). En journée de semaine, la disponibilité des SPV est contrainte par leurs obligations professionnelles en région francilienne. Quelle est la capacité maximale d'astreinte simultanée sans compromettre les secours d'urgence aux personnes (SUAP) ?*

14. **Gradation et enveloppe budgétaire du dispositif renforcé** :
    *Le déclenchement du dispositif renforcé peut-il être modulé par paliers (Niveau 1 : surveillance des massifs par caméras/drones/vigies ONF ; Niveau 2 : patrouilles de surveillance mobiles ciblées ; Niveau 3 : gardes postées prêtes au départ immédiat en caserne) ? Quel est le nombre maximum de « journées-dispositif » finançables sur l'été 2027 ?*

15. **Retour sur investissement (ROI) de la prévention face aux méga-feux** :
    *Pour justifier les arbitrages budgétaires devant le Conseil d'Administration du SDIS 77 et le Conseil Départemental, pouvons-nous modéliser le coût évité d'un grand incendie (mise en danger du public à Fontainebleau, coupure d'axes stratégiques A6/TGV, moyens aériens de la Sécurité Civile) par rapport à l'investissement préventif ?*

16. **Biais du paradoxe de la prévention** :
    *Lors des journées classées rouges sans sinistre constaté, comment prouver la part attribuable à l'efficacité dissuasive des patrouilles du SDIS 77 et de l'ONF (sensibilisation, interdictions d'accès, extinction des feux de camp naissants) par rapport à une surestimation météorologique ?*

---

## Axe 5 — Gouvernance des Données (0P, 1st, 2nd, 3rd Party), Qualité & Benchmarking

17. **Cartographie des sources par typologie (0P / 1P / 2P / 3P)** :
    *Pour alimenter notre catalogue de données et notre matrice Questions $\times$ Sources, quel est le niveau d'accès effectif aux différentes strates :*
    * **First-Party Data (1P — Interne SDIS 77)** : Main courante opérationnelle des interventions feux de végétation, délais de route réels, casernes CIS, réseau des Points d'Eau Incendie (hydrants/citernes).
    * **Second-Party Data (2P — Partenaires Institutionnels)** : Données **Météo-France** (IFM, modèle SIM2), données de gestion forestière **ONF Île-de-France** (massif de Fontainebleau), arrêtés préfectoraux de Seine-et-Marne.
    * **Third-Party Data (3P — Open Data, Satellites & Recherche)** : **BDIFF** nationale, **IGN** (BD Forêt, BD TOPO, RGE ALTI), détections thermiques satellites **NASA FIRMS / VIIRS & Copernicus EFFIS** (plateforme *FEUX FRANCE* sur data.gouv.fr), données météo foudre **Météorage**.
    * **Zero-Party Data (0P — Terrain & Citoyens)** : Retours d'expérience (RETEX) des chefs de centre de Seine-et-Marne, appels 18/112 géolocalisés, signalements des forestiers et usagers.

18. **Croisement multi-sources et validation scientifique** :
    *Confirmez-vous que l'enrichissement de la base historique des feux (BDIFF) par les caractéristiques de végétation (IGN), la topographie (pentes des platières gréseuses), l'humidité des sols (SIM2) et les interfaces périurbaines est la méthode attendue pour construire l'entrepôt de données ?*

19. **Périmètre du Benchmark Francilien et National** :
    *Pour situer la Seine-et-Marne par rapport aux départements voisins d'Île-de-France (Essonne 91, Yvelines 78, Val-d'Oise 95) et au reste du territoire national, préconisez-vous une analyse comparative avec les massifs sableux et résineux comparables (Landes, Gironde) et les zones céréalières du Centre-Val de Loire (Eure-et-Loir, Loiret) ?*

20. **Profondeur historique et rupture climatique** :
    *Sur quelle profondeur temporelle devons-nous entraîner nos modèles ? Un historique sur 15-20 ans offre du volume statistique mais risque de lisser l'intensification récente des canicules et sécheresses observées depuis 2022 en Seine-et-Marne.*

---

## Axe 6 — Systèmes Existants du SDIS 77, Contraintes Légales & Opérationnelles

21. **Intégration dans les outils opérationnels du SDIS 77** :
    *Quels sont les outils logiciels utilisés par le Centre de Traitement de l'Alerte et le CODIS du SDIS 77 (logiciel de gestion opérationnelle **Systel / Artémis** ou déploiement **Nexsis 18-112**, SIG départemental) ? Sous quel format de sortie (couche SIG GeoJSON, API, tableau de bord web) nos recommandations doivent-elles être livrées pour être directement exploitables par la chaîne de commandement ?*

22. **Insertion dans les documents réglementaires (SDACR, Ordre Départemental Feux de Forêts)** :
    *Les arbitrages du SDIS 77 s'articulent avec le **SDACR** (Schéma Départemental d'Analyse et de Couverture des Risques) et l'**Ordre Départemental d'Opérations Feux de Forêts**. Comment nos recommandations peuvent-elles s'insérer à la fois dans la planification pluriannuelle et dans la décision tactique quotidienne (briefing météo d'état-major la veille à 17h) ?*

23. **Conformité, RGPD et explicabilité légale** :
    *Quelles sont les exigences de conformité attendues par le SDIS 77 (anonymisation des adresses des appelants 18/112, hébergement sécurisé, explicabilité totale des algorithmes pour justifier juridiquement les arrêtés de mobilisation ou d'interdiction d'accès aux massifs devant le Préfet) ?*

---

## Axe 7 — Projection vers la Solution Finale (Le 11 Décembre)

24. **Nature du livrable d'aide à la décision pour le SDIS 77** :
    *Pour répondre au besoin d'arbitrage de la Direction, quelle est la cible opérationnelle idéale :*
    * **Un nouvel indice composite (« Indice Risque Opérationnel SDIS 77 »)** qui combine l'indice météo avec la vulnérabilité du combustible végétal (sables/bruyères de Fontainebleau, chaumes de la Brie) et les délais de route des secours ?
    * **Une matrice d'allocation spatiale et budgétaire** ciblant les centres de secours et secteurs où pré-positionner les engins CCF vs ceux où déployer une veille par caméras/satellites ?
    * **Un simulateur d'aide à la décision (OAD)** permettant à l'État-Major de tester différents seuils de déclenchement et de visualiser le taux de couverture des feux vs le budget d'astreinte consommé ?

25. **Explicabilité (« White-Box ») et adhésion des chefs de centre** :
    *Face aux réticences des chefs de centre sur la pertinence de la Météo des forêts, notre modèle doit-il expliciter clairement les facteurs déclencheurs de chaque alerte (ex. « Alerte déclenchée : indice météo modéré MAIS massif sur sables drainants + vent de Nord-Est 45 km/h + forte affluence dominicale à Fontainebleau ») pour garantir la confiance opérationnelle du terrain ?*
