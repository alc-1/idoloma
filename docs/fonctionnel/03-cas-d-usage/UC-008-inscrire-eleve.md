# UC-008 – Inscrire un élève

**Acteur** : Aurélie

**Préconditions** : Aurélie est connectée ; l'élève existe.

## Scénario nominal

1. Aurélie choisit l'élève, la disponibilité, la date de la première occurrence et la taille du carnet (5, 15, 30 ou 60).
2. Tous les cours du carnet sont générés à l'avance et l'élève y est inscrit.

## Variantes et erreurs

- Si un seul cours de la série n'a pas de place libre, l'inscription est refusée.
- L'inscription est possible sans paiement préalable.

## Règles liées

RG-001, RG-006, RG-007, RG-015

## Critères d'acceptation

- Étant donné une place libre sur chacun des 15 cours de la série, quand Aurélie inscrit l'élève avec un carnet de 15, alors l'élève apparaît sur les 15 cours.
- Étant donné un cours de la série à 6 élèves, quand Aurélie tente l'inscription, alors elle est refusée.
- Étant donné un élève qui n'a pas payé, quand Aurélie l'inscrit, alors l'inscription est acceptée et le carnet est en dette.
