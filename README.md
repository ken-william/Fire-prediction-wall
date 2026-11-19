# Feux de Forêt — Seine-et-Marne (Saison Feux 2027)

> **Projet de Modélisation et Pipeline de Données — Stratégie Business Data-Driven**  
> **Master MD5 (2026 / 2027) — Hétic**  
> **Commanditaire** : Direction du SDIS 77 (Service Départemental d'Incendie et de Secours de Seine-et-Marne)  
> **Région étudiée** : Île-de-France (Focus départemental : Seine-et-Marne - 77)  
> **Date cible de rendu** : 11 décembre 2026  

---

## Présentation du Projet

À la suite des saisons feux intenses et des épisodes de sécheresse estivale récents en Île-de-France, la Direction du **SDIS 77** prépare la saison estivale 2027 en sollicitant une analyse data-driven approfondie pour répondre à deux arbitrages stratégiques majeurs :

1. **Optimisation spatiale des moyens** : *Où concentrer les moyens humains et financiers pour lutter au mieux contre les départs de feux ?* (massif forestier de Fontainebleau, forêts de Crécy et de Villefermoy, zones agricoles céréalières de la Brie exposées aux feux de chaumes, interfaces habitat-forêt périurbaines franciliennes).
2. **Calibrage du seuil de déclenchement** : *À partir de quel niveau de la Météo des forêts déclencher le dispositif renforcé (patrouilles préventives, guet, pré-positionnement) ?*
   - Résoudre le paradoxe du seuil actuel : remédier aux **faux positifs** coûteux (sur-mobilisation sans départ de feu) et aux **faux négatifs** dangereux (feux réels déclenchés par indice bas).
   - Comparer le comportement de l'indice en Seine-et-Marne avec les départements voisins d'Île-de-France (Essonne, Yvelines, Val-d'Oise, etc.) et le reste du territoire national.

---

## Gouvernance & Répartition des Rôles (Groupe 8)

Conformément à la gouvernance d'équipe validée par l'encadrement pédagogique, les responsabilités sont attribuées selon les domaines d'expertise :

| Responsable | Rôle Officiel | Missions Clés | Livrables Engagés |
| :--- | :--- | :--- | :--- |
| **Théo**<br>*(Théophane KENGNI)*<br>`t_kengni@hetic.eu` | **Chef de projet** | Pilote le projet et veille au respect des échéances. Crée et organise le dépôt GitHub, attribue les tickets, gère les branches et PRs, organise les checkpoints et tient le journal des décisions. Coordonne la préparation de la restitution devant la direction du SDIS 77. | `README.md`, tableau des rôles, backlog GitHub, planning, journal des décisions (`docs/decisions/`), consolidation de la présentation finale. |
| **Linda**<br>*(Linda MAKAMTA)*<br>`l_makamtanjossu@hetic.eu` | **Responsable Data Analytics, KPIs & BI** | Définit les questions auxquelles les données doivent répondre et construit l'arbre de KPIs. Analyse les incendies par année, commune et niveau de danger météo, puis réalise les analyses comparatives Seine-et-Marne / Île-de-France / France. Conçoit le dashboard Power BI et traduit les résultats en recommandations opérationnelles. | Catalogue de KPIs, fiches indicateurs, calculs analytiques, maquettes puis rapport Power BI (`.pbix`), synthèse des recommandations. |
| **Mike**<br>*(Mikael NDEDI)* | **Responsable Data Engineering & Modélisation** | Développe le pipeline reproductible qui alimente les analyses. Charge et harmonise les données, construit les règles de jointure, modélise les tables de faits et dimensions, et produit un diagramme du modèle cible. Documente les transformations réalisées pour chaque champ. | Scripts Python/SQL, pipeline ETL médaillon, schéma UML ou équivalent, tables consolidées Parquet, dictionnaire technique et tableau de data lineage. |
| **Harald**<br>*(Harald MAFORIKAN)*<br>`h_maforikan@hetic.eu` | **Responsable Data Sources, Qualité & Conformité** | Identifie et documente les jeux de données nécessaires, établit la matrice questions × sources et vérifie la fiabilité des données. Définit les contrôles de qualité, examine les problèmes d'alignement entre sources et documente le choix des données lorsqu'il existe des doublons ou valeurs contradictoires. Traite les enjeux de conformité. | Fiches sources, glossaire, matrice questions × sources, rapport qualité, règles de validation, annexes des sources. |

---

## Architecture Cible du Dépôt

Le dépôt est structuré pour organiser l'ensemble des livrables de l'équipe (alimenté par les branches thématiques dédiées) :

```text
.
├── README.md                           # Présentation du projet, cadrage et gouvernance d'équipe
├── .gitignore                          # Règles d'exclusion des données volumineuses et secrets
├── docs/                               # Livrables et documentation d'équipe (fusionnés via PR)
│   ├── analyse/                        # [PR #3] Analyse de la commande, questions de cadrage et livrable Atelier 1
│   ├── sources/                        # [PR #4] Fiches descriptives des sources et matrice Questions × Sources (77)
│   ├── modelisation/                   # Diagramme UML StarUML, spécification données cibles et annexes
│   ├── dataviz/                        # [Nouveau] Maquettes UX, spécifications DAX et rapports Power BI
│   ├── glossaire/                      # Glossaire partagé des termes métiers et techniques
│   └── decisions/                      # Journal de bord des choix d'architecture et de gouvernance
└── data/                               # Jeux de données bruts et nettoyés (non versionnés sur git)
```
