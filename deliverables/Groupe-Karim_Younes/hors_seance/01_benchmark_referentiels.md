# Benchmark des référentiels externes

## Identification

- **Groupe** : Karim_Younes
- **Jeu de données étudié** : Etablissements de l'enseignement supérieur universitaire public 2024-2025
- **Types d'entités retenus** : Établissement, Université, Ville

## 1. Référentiels comparés

| Référentiel | URL | Types d'entités couverts | Intérêt potentiel | Limites observées |
| --- | --- | --- | --- | --- |
| Wikidata | https://www.wikidata.org | institutions, universités, pays | identifiants stables, riche | parfois complexe |
| DBpedia | https://dbpedia.org | institutions, universités | lié à Wikipédia | couverture incomplète |
| GeoNames | https://www.geonames.org | villes, pays | données géographiques précises | pas d’infos académiques |


## 2. Critères de comparaison

Expliquez les critères utilisés pour comparer les référentiels :

- couverture : nombre d’entités disponibles 
- qualité des identifiants : présence d’identifiants stables 
- précision sémantique : clarté des concepts
- facilité d'appariement : facilité à trouver une correspondance 
- richesse des informations disponibles : quantité d’informations disponibles

## 3. Cas d'appariement manuel

Documentez au moins `6` cas.

| Entité locale | Type | Référentiel cible | Correspondance candidate | Indices utilisés | Niveau de confiance | Décision |
| --- | --- | --- | --- | --- | --- | --- |
| ENSIAS | Établissement | Wikidata | ENSIAS | nom + ville + site web | élevé | validé |
| EMI | Établissement | Wikidata | EMI | nom + sigle + ville | moyen | validé |
| Université Mohammed V | Université | Wikidata | UM5 | nom + ville | élevé | validé |
| Rabat | Ville | GeoNames | Rabat | nom + pays | élevé | validé |
| Casablanca | Ville | GeoNames | Casablanca | nom + pays | élevé | validé |
| UCA | Université | DBpedia | Cadi Ayyad University | nom + ville | moyen | validé |


## 4. Synthèse

- Quel référentiel paraît le plus utile pour chaque type d'entité ?
    - Wikidata est le meilleur pour les institutions et universités. 
    - GeoNames est le plus adapté pour les villes.
    - DBpedia est utile mais moins complet.

- Quels cas restent ambigus ?
    - sigles (EMI, UCA)
    - noms différents selon la langue

- Quels champs du dataset aident le plus à l'appariement ?
    - institution_name
    - city
    - website
    - short_name