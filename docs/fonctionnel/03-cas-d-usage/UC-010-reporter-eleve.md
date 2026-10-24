# UC-010 – Reporter un élève (rattrapage)

**Acteur** : Aurélie

**Préconditions** : L'élève est inscrit à un cours de groupe de la semaine.

## Scénario nominal

1. Aurélie fait glisser l'élève vers un autre cours de groupe de la même semaine.
2. Le cours de destination est un rattrapage.
3. Le cours d'origine est conservé et barré.

## Variantes et erreurs

- Un cours d'une autre semaine est refusé.
- Un cours complet est accepté.
- Pour corriger, Aurélie reporte l'élève dans l'autre sens (RG-019).

## Règles liées

RG-010, RG-011, RG-019

## Critères d'acceptation

- Étant donné un élève inscrit le mardi et un cours complet le jeudi de la même semaine, quand Aurélie le reporte au jeudi, alors le report est accepté, le jeudi est un rattrapage, le cours du mardi est conservé et barré, et le décompte est inchangé.
- Étant donné un cours d'une autre semaine, quand Aurélie y reporte l'élève, alors le report est refusé.
- Étant donné une absence justifiée et validée, quand Aurélie reporte l'élève sur un autre jour de la même semaine, alors le carnet est utilisé par le rattrapage et non par le cours manqué.
