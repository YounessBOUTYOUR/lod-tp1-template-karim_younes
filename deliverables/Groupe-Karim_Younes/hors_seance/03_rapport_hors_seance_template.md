# Rapport hors séance - TP1

## Page de garde

- **Module** : Linked Open Data  
- **TP** : TP1 - Introduction aux données ouvertes liées  
- **Groupe** : Karim_Younes  
- **Étudiants** : Karim Ait Salim, Younes …  
- **Date** : 18/04/2026  

## Consigne

Ce rapport est à remettre **avant la prochaine séance**. Il constitue une **étude distincte** du travail réalisé pendant le TP1 en classe et prépare directement le TP2.

## 1. Introduction

Ce travail s’inscrit dans le cadre du module Linked Open Data et vise à préparer un jeu de données réel à une future transformation en données liées.  
Le dataset étudié provient du portail Open Data du Maroc et décrit les établissements publics de l’enseignement supérieur pour l’année 2024-2025.  

L’objectif est d’identifier les entités principales, d’étudier les possibilités d’appariement avec des référentiels externes, et de proposer une stratégie de normalisation et d’identification.
Le principal problème étudié est l’absence d’identifiants stables et de normalisation, ce qui rend difficile l’interconnexion des données.


## 2. Types d'entités étudiés

Les entités retenues sont :

    - Établissement
    - Université
    - Ville

- les raisons de ce choix : 
    - L’établissement est l’entité centrale du dataset  
    - L’université structure les établissements  
    - La ville permet la localisation et le lien avec des référentiels géographiques  

- les champs ou indices disponibles pour les apparier à des référentiels externes
    - nom de l’établissement  
    - nom de l’université  
    - ville  
    - site web  



## 3. Benchmark des référentiels externes

Les référentiels étudiés sont :
    - Wikidata
    - DBpedia
    - GeoNames

Comparaison :

    - Couverture : Wikidata couvre mieux les institutions, GeoNames les villes  
    - Précision : Wikidata est plus fiable pour les entités académiques  
    - Identifiants : Wikidata fournit des identifiants stables  
    - Richesse : Wikidata contient plus d’informations que DBpedia  
    - Facilité d’usage : GeoNames est simple pour les villes  

Conclusion :  
    Wikidata est le plus pertinent pour les établissements et universités,  
GeoNames pour les villes. De plus, Wikidata est privilégié car il offre des identifiants uniques et une meilleure interopérabilité.


## 4. Cas d'appariement manuel

Quelques cas étudiés :

- ENSIAS → Wikidata  
  - indices : nom + ville  
  - confiance : élevée  
  - décision : validé  

- EMI → Wikidata  
  - indices : nom + sigle  
  - confiance : moyenne (sigle ambigu)  
  - décision : validé  

- Université Mohammed V → Wikidata  
  - indices : nom + ville  
  - confiance : élevée  
  - décision : validé  

- Rabat → GeoNames  
  - indices : nom + pays  
  - confiance : élevée  
  - décision : validé  

- Casablanca → GeoNames  
  - indices : nom + pays  
  - confiance : élevée  
  - décision : validé  

- UCA → DBpedia  
  - indices : nom + ville  
  - confiance : moyenne  
  - décision : validé 


## 5. Plan de normalisation et d'identification

Avant de transformer les données en Linked Data, il faut d’abord les nettoyer et les organiser. Par exemple, les noms des établissements peuvent être écrits de différentes façons, donc il faut les uniformiser. C’est pareil pour les types d’institution et les domaines, il faut les standardiser pour éviter les incohérences.

Pour les identifiants, il n’y a pas d’identifiant officiel dans le dataset, donc on peut utiliser une combinaison comme le nom de l’établissement avec la ville. On peut aussi utiliser des référentiels externes comme Wikidata ou GeoNames pour avoir des identifiants plus fiables.

L’objectif est de rendre les données plus propres et plus faciles à utiliser pour la suite.

## 6. Analyse des risques

Il y a plusieurs risques dans ce travail. Le plus important est le faux appariement, par exemple quand deux établissements ont des noms proches ou le même sigle. Il y a aussi des problèmes avec la langue, car certains noms sont en français et d’autres en anglais.

Les villes peuvent aussi poser problème si elles ont des noms similaires. En plus, le dataset manque d’informations importantes comme des identifiants officiels ou des coordonnées, ce qui rend l’appariement plus difficile.

## 7. Difficultés rencontrées

On a rencontré plusieurs difficultés pendant ce travail. D’abord, il n’y a pas d’identifiants stables, donc il faut se baser sur les noms, ce qui n’est pas toujours fiable. Ensuite, les noms ne sont pas toujours écrits de la même façon, ce qui complique les choses.

Certains référentiels ne contiennent pas toutes les informations ou ne couvrent pas tous les établissements. Enfin, il est parfois difficile de savoir si deux noms correspondent vraiment à la même entité.

## 8. Conclusion

Ce travail nous a permis de comprendre que même si le dataset est bien structuré, il n’est pas encore prêt pour être utilisé en Linked Data. Il faut d’abord nettoyer les données, normaliser les valeurs et créer des identifiants fiables.

Les référentiels comme Wikidata et GeoNames sont très utiles pour améliorer la qualité des données. Ce travail est important car il prépare le passage au TP2 où on va utiliser ces données pour créer un modèle plus avancé.
