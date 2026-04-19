# Fiche d'analyse du jeu de données

## Identification

- **Groupe** : Karim_Younes 
- **Date** : 18/04/2026
- **Nom du jeu de données** : higher_education_sample.csv
- **Source / producteur** : Ministère de l’Enseignement Supérieur, de la Recherche Scientifique et de l’Innovation (MESRSI)
- **URL de la source** : https://data.gov.ma/data/fr/dataset/etablissements-de-l-enseignement-superieur-universitaire-public-ouverts/resource/fb9c2300-77f7-461c-86a5-9184b00e57d9
- **Domaine métier** : Enseignement supérieur

## Description générale

- **Objectif du jeu de données** :Présenter la liste des établissements de l’enseignement supérieur universitaire public ouverts au Maroc pour l’année 2024-2025
- **Format(s) disponible(s)** : XLSX
- **Langue(s)** : Français
- **Licence** : Open Data Commons Open Database License (ODbL)
- **Fréquence de mise à jour** : annuelle
- **Unité d'observation** : université public
- **Granularité des enregistrements** :  Niveau institutionnel (université, école, faculté…)

## Structure du jeu de données

| Champ / colonne | Signification | Exemple de valeur | Observation |
| --- | --- | --- | --- |
| record_id | identifiant local | 1 | unique mais non stable |
| institution_name | nom complet | ENSIAS | principal champ descriptif |
| short_name | sigle | EMI | peut être ambigu |
| city | ville | Rabat | utile pour liaison externe |
| country | pays | Morocco | homogène |
| website | site web | https://www.emi.ac.ma | bon identifiant potentiel |
| institution_type | type | university | non normalisé |
| main_field | domaine | engineering | non normalisé |

## Évaluation "Open Data"

| Critère | Observation | Score / 5 |
| --- | --- | --- |
| Accessibilité | données faciles à accéder (CSV/XLSX) | 4/5 |
| Réutilisabilité | structure simple et exploitable | 4/5 |
| Documentation | peu d’informations disponibles | 2/5 |
| Format exploitable | format ouvert (CSV) | 5/5 |
| Présence d'une licence | licence disponible (ODbL) | 4/5 |

## Évaluation "Linked Data readiness"

| Point observé | Oui / Non / Partiel | Commentaire |
| --- | --- | --- |
| Identifiants stables pour les enregistrements | Partiel | record_id local uniquement |
| Entités clairement distinguables | Oui | institutions, villes, pays |
| Valeurs normalisées | Partiel | types et domaines non standardisés |
| Informations géographiques exploitables | Oui | city + country |
| Possibilité de lien vers des référentiels externes | Oui | noms + villes + site web |
| Présence de clés candidates plausibles | Oui | website, nom + ville |
| Présence de codes ou nomenclatures réutilisables | Non | aucun code officiel |

## Maturité "5 étoiles"

| Niveau | Atteint ? | Justification |
| --- | --- | --- |
| 1 étoile | Oui | données disponibles en ligne |
| 2 étoiles | Oui | données structurées |
| 3 étoiles | Oui | format CSV non propriétaire |
| 4 étoiles | Non | pas d’identifiants URI |
| 5 étoiles | Non | pas de liens externes |

## Clés candidates et identifiants

| Objet ou entité cible | Champ(s) candidat(s) | Fiabilité | Limites | Recommandation |
| --- | --- | --- | --- | --- |
| Institution | website | élevée | peut changer | bon identifiant temporaire |
| Institution | institution_name | moyenne | variations possibles | utiliser avec city |
| Institution | name + city | assez élevée | textuel | meilleure combinaison |

## Normalisation préalable nécessaire

| Champ | Problème observé | Impact pour le LOD | Action recommandée |
| --- | --- | --- | --- |
| institution_type | valeurs différentes | incohérence | standardiser |
| main_field | non structuré | difficile à relier | normaliser |
| city | variantes possibles | erreurs de lien | utiliser GeoNames |
| institution_name | variations | ambiguïté | harmoniser |

## Qualité des données

- **Forces observées** : structure simple, données claires, site web présent  
- **Faiblesses observées** : pas d’identifiant stable, normalisation faible  
- **Ambiguïtés ou doublons potentiels** : sigles ambigus, noms similaires  es GPS  
- **Champs manquants pour une meilleure interconnexion** : identifiant officiel, région
- **Risque principal pour une future mise en relation** : erreurs d’appariement

## Conclusion courte

Ce dataset est une bonne base car il est structuré et contient des entités réelles comme les institutions et les villes. Il peut être facilement exploité mais n’est pas encore prêt pour le Linked Open Data. Les principaux problèmes sont l’absence d’identifiants stables et le manque de normalisation. Pour améliorer, il faut créer des identifiants uniques, normaliser les catégories et relier les données à des référentiels externes comme Wikidata et GeoNames.
