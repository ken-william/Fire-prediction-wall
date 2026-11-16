# Feux de Forêt — Auvergne-Rhône-Alpes (Saison Feux 2027)

> **Projet de Modélisation et Pipeline de Données — Stratégie Business Data-Driven**  
> **Master MD5 (2026 / 2027) — Hétic**  
> **Commanditaire** : Direction du SDMIS 69 (Service Départemental-Métropolitain d'Incendie et de Secours du Rhône)  
> **Région étudiée** : Auvergne-Rhône-Alpes (Focus départemental : Rhône - 69)  
> **Date cible de rendu** : 11 décembre 2026  

---

## 📌 Présentation du Projet

À la suite des saisons feux intenses et de la canicule de 2026, la Direction du **SDMIS 69** prépare la saison estivale 2027 en sollicitant une analyse data-driven approfondie pour répondre à deux arbitrages stratégiques majeurs :

1. **Optimisation spatiale des moyens** : *Où concentrer les moyens humains et financiers pour lutter au mieux contre les départs de feux ?* (zones périurbaines lyonnaises, massifs du Beaujolais et des Monts du Lyonnais, interfaces habitat-forêt).
2. **Calibrage du seuil de déclenchement** : *À partir de quel niveau de la Météo des forêts déclencher le dispositif renforcé (patrouilles préventives, guet, pré-positionnement) ?*
   - Résoudre le paradoxe du seuil actuel : remédier aux **faux positifs** coûteux (sur-mobilisation sans départ de feu) et aux **faux négatifs** dangereux (feux réels déclenchés par indice bas).
   - Comparer le comportement de l'indice dans le Rhône avec les départements voisins d'Auvergne-Rhône-Alpes (Ardèche, Drôme, Isère, etc.) et le reste du territoire national.

---

## 👥 Gouvernance & Répartition des Rôles

Conformément aux exigences méthodologiques du titre RNCP, la gouvernance de l'équipe est organisée autour de 4 domaines de responsabilité :

| Rôle | Responsable | Périmètre de Responsabilité |
| :--- | :--- | :--- |
| **Chef·fe de projet** | **Théophane KENGNI** (`ken-william`) | Administration du dépôt, gestion des tickets / issues, planification des checkpoints et tenue du journal des décisions. *(Assure également le rôle Responsable sources en configuration 3 personnes)*. |
| **Responsable sources** | *À compléter par le groupe* | Inventaire des données (1P, 2P, 3P), fiches d'identité des sources, construction de la matrice « Questions $\times$ Sources ». |
| **Responsable qualité & conformité** | *À compléter par le groupe* | Définition des règles de qualité des données, tests de non-régression, conformité légale et RGPD / données sensibles. |
| **Responsable pipeline & modèle** | *À compléter par le groupe* | Architecture d'ingestion (ETL/ELT), consolidation des données multi-sources, modélisation de l'entrepôt et algorithmes d'aide à la décision. |

> *Note : Tout changement de rôle en cours de projet sera consigné et justifié dans le dossier `docs/decisions/`.*

---

## 🗂️ Architecture du Dépôt

Le dépôt est structuré pour garantir la traçabilité des contributions individuelles et collectives :

```text
.
├── README.md                           # Présentation du projet, cadrage et gouvernance
├── .gitignore                          # Règles d'exclusion des données volumineuses et secrets
├── docs/
│   ├── analyse/
│   │   ├── commande-theophane-kengni.md# Analyse individuelle (Partie B) - Questions, Termes, Besoins, Données
│   │   └── questions-cadrage-groupe.md # Référentiel complet des questions de cadrage du groupe (7 axes)
│   ├── glossaire/                      # Glossaire partagé des termes métiers et techniques
│   └── decisions/                      # Journal de bord des choix d'architecture et de gouvernance
└── data/                               # Dossier des jeux de données (non versionné sur git - DVC/S3 si applicable)
```

---

## 🎯 Livrables & Jalons du Projet

* **Exercice 1 — De la commande aux données** (Novembre 2026) :
  - [x] **Partie A (Groupe)** : Création du dépôt, gouvernance d'équipe, convention de travail et cadrage stratégique.
  - [x] **Partie B (Individuel)** : Analyse de la commande, formalisation des questions décisionnelles, termes inconnus, besoins et données cibles ([docs/analyse/commande-theophane-kengni.md](docs/analyse/commande-theophane-kengni.md)).
* **Exercice 2 — Inventaire & Qualification des Sources** :
  - Collecte et qualification des bases d'incendies (BDIFF, Prométhée, NASA FIRMS), données météo (Météo-France, SIM2), végétation (IGN BD Forêt) et topographie (IGN RGE ALTI).
* **Exercice 3 — Pipeline & Consolidation (Entrepôt de Données)** :
  - Pipeline de transformation, nettoyage et stockage structuré.
* **Rendu Final & Soutenance — 11 Décembre 2026** :
  - Modèle d'optimisation des seuils, simulateur d'arbitrage budgétaire et recommandations stratégiques pour le SDMIS 69.

---

## 🛠️ Normes de Travail & Collaboration Git

- **Branches atomiques** : une branche par fonctionnalité ou exercice (`feature/analyse-commande-theophane`, `feature/sources-bdiff`, etc.).
- **Commits individuels et explicites** : respect des conventions de commit (ex. `feat: ajout analyse commande theophane`, `docs: mise à jour du glossaire`).
- **Revue de code & Pull Requests** : chaque livrable fait l'objet d'une PR validée par le ou la responsable du domaine concerné avant merge sur `main`.
