# UC-011 – Enregistrer une absence

**Acteur** : Aurélie

**Préconditions** : L'élève est inscrit à ce cours.

## Scénario nominal

1. Aurélie marque l'élève absent à un seul cours, avec ou sans justification valide.
2. Si la justification est valide, Aurélie la valide.

## Variantes et erreurs

- Si l'absence est justifiée et validée, un rattrapage est possible sur un autre jour de la même semaine (UC-010).
- Pour corriger, Aurélie retire l'absence (RG-019).

## Règles liées

RG-010, RG-011, RG-016, RG-019

## Critères d'acceptation

- Étant donné une absence sans justification valide, quand Aurélie l'enregistre, alors le carnet est utilisé et ses autres cours sont inchangés.
- Étant donné une absence justifiée et validée par Aurélie, quand elle l'enregistre, alors le carnet n'est pas utilisé et un rattrapage est possible sur un autre jour de la même semaine.
- Étant donné un cours à 6 élèves, quand Aurélie marque l'un d'eux absent, alors une place se libère dans le cours.
- Étant donné une absence marquée par erreur, quand Aurélie la retire, alors la situation est rétablie.
