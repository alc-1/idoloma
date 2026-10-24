# UC-005 – Enregistrer une fermeture

**Acteur** : Aurélie

**Préconditions** : Aurélie est connectée.

## Scénario nominal

1. Aurélie indique la période de fermeture et sa raison (vacances, maladie…).
2. Les cours de la période deviennent indisponibles.
3. Pour chaque élève concerné, Aurélie choisit de décaler sa série ou de lui accorder un rattrapage.

## Variantes et erreurs

- Pour corriger, Aurélie supprime la fermeture (RG-019).

## Règles liées

RG-010, RG-013, RG-019

## Critères d'acceptation

- Étant donné un cours avec des élèves inscrits, quand Aurélie enregistre une fermeture couvrant ce cours, alors le cours devient indisponible et la raison est conservée.
- Étant donné la même fermeture, quand Aurélie choisit de décaler la série d'un élève, alors le carnet n'est pas utilisé et un cours est ajouté à la fin de sa série.
- Étant donné la même fermeture, quand Aurélie choisit un rattrapage pour un élève, alors il est reporté sur un autre jour de la même semaine.
- Étant donné une fermeture enregistrée par erreur, quand Aurélie la supprime, alors les cours redeviennent disponibles et les séries sont rétablies.
