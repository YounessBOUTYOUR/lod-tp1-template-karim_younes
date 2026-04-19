# Plan de normalisation et d'identification

## 1. Entités prioritaires

| Type d'entité | Pourquoi est-il prioritaire ? | Identifiant actuel | Stratégie proposée |
| --- | --- | --- | --- |
| Établissement | entité centrale du dataset | record_id | créer un URI unique basé sur nom + ville |
| Université | structure principale regroupant les établissements | record_id | utiliser nom officiel + ville |
| Ville | utilisée pour la localisation | city | relier à GeoNames |

## 2. Champs à normaliser

| Champ | Problème observé | Règle de normalisation proposée | Impact attendu |
| --- | --- | --- | --- |
| Nom établissement | variations d’écriture | uniformiser les noms | éviter ambiguïtés |
| Université | noms différents | normaliser noms officiels | cohérence |
| Ville | variantes possibles | aligner avec GeoNames | fiabilité géographique |
| Type établissement | valeurs non standard | créer liste contrôlée | cohérence |

## 3. Stratégie d'identifiants

| Entité cible | Base de construction envisagée | Risque | Recommandation |
| --- | --- | --- | --- |
| Établissement | nom établissement + ville | variations d’écriture | créer un identifiant unique (URI) |
| Université | nom officiel | noms différents selon langue | normaliser avant utilisation |
| Ville | référentiel externe (GeoNames) | homonymie possible | utiliser identifiant GeoNames |

## 4. Risques et limites

- Quels champs sont trop faibles pour servir d'identifiant ?
Les noms des établissements peuvent varier (langue, accents).

- Quelles collisions ou ambiguïtés sont possibles ?
    - Les sigles peuvent être ambigus (ex : EMI, UCA).
    - Risque de confusion entre établissements et universités.
    - Les noms de villes peuvent avoir plusieurs variantes.

- Quelles informations supplémentaires seraient nécessaires ?
Il manque des identifiants officiels uniques
