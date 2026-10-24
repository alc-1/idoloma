# UC-004 – Gérer les disponibilités

**Acteur** : Aurélie

**Préconditions** : Aurélie est connectée.

## Scénario nominal

1. Aurélie crée une disponibilité, récurrente (ex. mardi 17h) ou unique, avec ses horaires et sa plage de temps (ex. de janvier à septembre).
2. Elle peut la modifier ou l'archiver sur une plage de temps donnée (ex. à partir d'octobre).

## Variantes et erreurs

- Si un élève est inscrit à un cours de la plage concernée, la modification ou l'archivage est refusé : aucun élève ne doit être impacté.
- Une disponibilité archivée n'est plus proposée pour de nouvelles inscriptions sur la plage archivée.

## Règles liées

RG-002, RG-020

## Critères d'acceptation

- Étant donné une disponibilité récurrente le mardi à 17h de janvier à septembre, quand Aurélie la crée, alors des cours de groupe sont proposés chaque mardi à 17h sur cette plage.
- Étant donné une disponibilité de cours de groupe déjà présente un jour donné, quand Aurélie en crée une seconde le même jour, alors la création est refusée (RG-002).
- Étant donné une disponibilité sans élève inscrit à partir d'octobre, quand Aurélie la modifie à partir d'octobre, alors la modification est acceptée.
- Étant donné un élève inscrit à un cours d'octobre, quand Aurélie tente de modifier ou d'archiver la disponibilité à partir d'octobre, alors l'opération est refusée.
