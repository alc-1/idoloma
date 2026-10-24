# UC-009 – Retirer un élève d'un cours

**Acteur** : Aurélie

**Préconditions** : L'élève est inscrit à ce cours.

## Scénario nominal

1. Aurélie retire l'élève d'un seul cours.
2. Le carnet est utilisé par défaut.

## Variantes et erreurs

- Si l'absence est justifiée et validée par Aurélie, le carnet n'est pas utilisé et un rattrapage est possible sur un autre jour de la même semaine (UC-010).
- Pour corriger, Aurélie inscrit de nouveau l'élève à ce cours (RG-019).

## Règles liées

RG-010, RG-011, RG-019

## Critères d'acceptation

- Étant donné un élève inscrit à un cours, quand Aurélie le retire de ce cours sans justification, alors il n'apparaît plus sur ce cours, ses autres cours sont inchangés et le carnet est utilisé.
- Étant donné un retrait pour absence justifiée et validée, quand Aurélie le valide, alors le carnet n'est pas utilisé et un rattrapage est possible sur un autre jour de la même semaine.
