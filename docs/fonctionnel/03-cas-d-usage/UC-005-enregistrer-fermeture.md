# UC-005 – Enregistrer une fermeture

**Acteur** : Aurélie

**Préconditions** : Aurélie est connectée.

## Scénario nominal

1. Aurélie indique la période de fermeture et sa raison (vacances, maladie…).
2. Les cours de la période deviennent indisponibles.

## Variantes et erreurs

- Pour corriger, Aurélie supprime la fermeture (RG-019).

## Règles liées

RG-013, RG-019

## Critères d'acceptation

- Étant donné un cours avec des élèves inscrits, quand Aurélie enregistre une fermeture couvrant ce cours, alors le cours devient indisponible et la raison est conservée.
- Étant donné la même fermeture, quand elle est enregistrée, alors le carnet de chaque élève n'est pas utilisé et un cours est ajouté à la fin de sa série.
- Étant donné une fermeture enregistrée par erreur, quand Aurélie la supprime, alors les cours redeviennent disponibles et les séries sont rétablies.
