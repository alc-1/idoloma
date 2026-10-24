# UC-002 – Consulter le planning de la semaine

**Acteur** : Aurélie

**Préconditions** : Aurélie est connectée.

## Scénario nominal

1. Aurélie ouvre la vue semaine.
2. Pour chaque cours, elle voit les participants avec leur décompte et leurs états, ainsi que les rendez-vous privés détaillés.

## Variantes et erreurs

- Le seul geste d'édition est le report d'un élève (UC-010).

## Règles liées

RG-003, RG-004, RG-008

## Critères d'acceptation

- Étant donné un élève au 12e cours d'un carnet de 15, quand Aurélie ouvre la vue semaine, alors elle voit « 12/15 » à côté de son nom.
- Étant donné un cours à 5 élèves, quand Aurélie ouvre la vue semaine, alors le cours est grisé.
- Étant donné un cours à 2 élèves, quand Aurélie ouvre la vue semaine, alors le cours est mis en évidence comme annulable.
- Étant donné un rendez-vous privé de Christelle à 14h, quand Aurélie ouvre la vue semaine, alors elle voit « Christelle 14h ».
- Étant donné un élève au dernier cours de son carnet et en dette, quand Aurélie ouvre la vue semaine, alors les deux états sont visibles ensemble.
