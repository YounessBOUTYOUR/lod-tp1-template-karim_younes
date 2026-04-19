# Carte des entités et des liens potentiels

## 1. Inventaire des entités

| Entité ou type d'entité | Exemple local | Pourquoi s'agit-il d'une entité ? | Attributs associés | Identifiant local potentiel |
| --- | --- | --- | --- | --- |
| Institution | ENSIAS | organisation réelle | nom, site web, année | website |
| Ville | Rabat | lieu réel | nom ville | city |
| Pays | Morocco | entité géographique | nom pays | country |
| Type d’institution | university | catégorie métier | type | valeur normalisée |
| Domaine | engineering | domaine académique | discipline | valeur normalisée |
| Site web | https://www.emi.ac.ma | ressource associée | URL | website |
| Portail Open Data | data.gov.ma | source de données | nom portail | portal_hint |

## 2. Relations conceptuelles observées

| Source | Relation conceptuelle | Cible | Cardinalité | Commentaire |
| --- | --- | --- | --- | --- |
| Institution | est située dans | Ville | N:1 | plusieurs institutions par ville |
| Ville | appartient à | Pays | N:1 | une ville → un pays |
| Institution | a pour type | Type d’institution | N:1 | chaque institution a un type |
| Institution | a pour domaine | Domaine | N:1 | domaine principal |
| Institution | possède | Site web | 1:1 | un site par institution |
| Institution | référencée par | Portail | N:1 | source du dataset |

## 3. Liens externes proposés

| Entité locale | Ressource externe candidate | Type de lien envisagé | Critères d'appariement | Justification | Bénéfice attendu | Niveau de confiance | Risque |
| --- | --- | --- | --- | --- | --- | --- | --- |
| ENSIAS | Wikidata | équivalence | nom + ville + site web | institution connue | identifiant stable | élevé | faible |
| EMI | Wikidata | équivalence | nom + sigle + ville | établissement reconnu | enrichissement | élevé | moyen |
| Rabat | GeoNames | correspondance | nom + pays | ville identifiable | coordonnées GPS | élevé | faible |
| Casablanca | GeoNames | correspondance | nom + pays | ville connue | normalisation | élevé | faible |
| Morocco | Wikidata | équivalence | nom pays | unique | identifiant stable | très élevé | faible |
| Morocco | DBpedia | équivalence | nom pays | ressource connue | enrichissement | très élevé | faible |

## 4. Schéma conceptuel




## 5. Analyse critique

- Quels liens vous paraissent les plus fiables ?
Les liens les plus fiables sont ceux vers les pays et les grandes villes. Les liens vers les institutions sont fiables mais nécessitent plusieurs critères (nom + ville + site).

- Quels liens restent incertains ?
Les liens les plus incertains concernent les sigles et les noms ambigus.

- Quelles informations supplémentaires faudrait-il pour automatiser les correspondances ?
Il faudrait des identifiants officiels et des coordonnées GPS pour automatiser les correspondances.

- Quelles entités devraient recevoir un identifiant stable en priorité ?
Les institutions doivent recevoir un identifiant stable en priorité.

- Quels risques de faux positifs ou de collisions d'identifiants avez-vous identifiés ?
Le principal risque est le faux appariement à cause des variantes de noms.