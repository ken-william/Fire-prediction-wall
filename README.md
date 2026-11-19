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

## Gouvernance & Répartition des Rôles

Conformément aux exigences méthodologiques du titre RNCP, la gouvernance de l'équipe est organisée autour de 4 domaines de responsabilité :

| Rôle | Responsable | Périmètre de Responsabilité |
| :--- | :--- | :--- |
| **Chef·fe de projet** | *À compléter par le groupe* | Administration du dépôt, gestion des tickets / issues, planification des checkpoints et tenue du journal des décisions. *(Assure également le rôle Responsable sources en configuration 3 personnes)*. |
| **Responsable sources** | *À compléter par le groupe* | Inventaire des données (1P, 2P, 3P), fiches d'identité des sources, construction de la matrice « Questions $\times$ Sources ». |
| **Responsable qualité & conformité** | *À compléter par le groupe* | Définition des règles de qualité des données, tests de non-régression, conformité légale et RGPD / données sensibles. |
| **Responsable pipeline & modèle** | *À compléter par le groupe* | Architecture d'ingestion (ETL/ELT), consolidation des données multi-sources, modélisation de l'entrepôt et algorithmes d'aide à la décision. |

> *Note : Tout changement de rôle en cours de projet sera consigné et justifié dans le dossier `docs/decisions/`.*

---

## Architecture du Dépôt

Le dépôt est structuré pour organiser les travaux collectifs de l'équipe :

```text
.
├── README.md                           # Présentation du projet, cadrage et gouvernance
├── .gitignore                          # Règles d'exclusion des données volumineuses et secrets
├── docs/                               # Livrables et documentation (développés dans les branches de travail)
│   ├── analyse/                        # Analyse de la commande et questions de cadrage
│   ├── sources/                        # Fiches descriptives des sources et matrice de décision
│   ├── glossaire/                      # Glossaire partagé des termes métiers et techniques
│   └── decisions/                      # Journal de bord des choix d'architecture et de gouvernance
└── data/                               # Jeux de données (non versionnés sur git)
```
