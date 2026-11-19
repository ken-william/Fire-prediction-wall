# Modélisation & Architecture DataOps — Feux de Forêt (Seine-et-Marne / SDIS 77)

Ce dossier rassemble les livrables d'ingénierie et de modélisation demandés pour la plateforme de données feux de forêt du département de Seine-et-Marne (SDIS 77) :

---

## Sommaire des Livrables

### 1. Diagramme UML (Modèle Conceptuel et Logique de Données)
- **Fichier source PlantUML / StarUML :** [`diagramme-uml.puml`](diagramme-uml.puml)
- **Documentation & Rendu Visuel Mermaid :** [`diagramme-uml.md`](diagramme-uml.md)
- **Contenu :** Classes métier (`Commune`, `MassifForestier`, `CentreIncendieSecours`, `Incendie`, `MeteoDepartementaleJour`, `DispositifOperationnel`, `KpiConsolideAnnuel`), cardinalités, clés primaires et étrangères, typage strict.

### 2. Spécification des Données Cibles (Sources -> Transformations -> Alignement)
- **Document de référence :** [`donnees-cibles.md`](donnees-cibles.md)
- **Contenu :** Matrice détaillée des champs entrants, règles de transformation (nettoyage, standardisation, normalisation), alignement sémantique et spatial (codes INSEE 5 car., EPSG:2154, ISO 8601), architecture médaillon (Bronze -> Silver -> Gold), et justification de la performance/robustesse du format **Apache Parquet**.

### 3. Annexes (Liste Exhaustive des Sources Utilisées)
- **Document de référence :** [`annexes-sources.md`](annexes-sources.md)
- **Contenu :** Inventaire qualifié des 10 sources mobilisées (BDIFF, Météo-France, IGN BD Forêt, INSEE, RGE ALTI, NASA FIRMS, Copernicus EFFIS, SDIS 77 First-Party, ONF DFCI) avec licences, producteurs, URLs officielles, granularité spatio-temporelle et limites identifiées.
