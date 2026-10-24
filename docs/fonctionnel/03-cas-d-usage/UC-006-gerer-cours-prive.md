# UC-006 – Gérer un cours privé

**Acteur** : Aurélie

**Préconditions** : Aurélie est connectée.

## Scénario nominal

1. Aurélie crée un cours privé avec un ou plusieurs élèves identifiés, la date et l'heure.
2. Elle peut le modifier ou l'annuler.

## Variantes et erreurs

- Un cours privé ne consomme aucune place de cours de groupe.

## Règles liées

RG-005, RG-018

## Critères d'acceptation

- Étant donné un cours de groupe à 6 élèves, quand Aurélie crée un cours privé le même jour sur un autre horaire, alors il est accepté.
- Étant donné un cours privé avec 2 élèves identifiés, quand Aurélie le crée, alors les deux élèves sont enregistrés et leur nombre est affiché.
- Étant donné un cours de groupe et un cours privé le même jour, quand Aurélie crée un second cours privé le même jour, alors il est accepté.
- Étant donné un cours privé, quand Aurélie consulte la vue semaine, alors il apparaît sous la forme « Christelle 14h ».
