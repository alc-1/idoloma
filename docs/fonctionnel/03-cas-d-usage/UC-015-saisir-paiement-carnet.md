# UC-015 – Saisir ou modifier le paiement d'un carnet

**Acteur** : Aurélie

**Préconditions** : Le carnet existe.

## Scénario nominal

1. Aurélie saisit le paiement du carnet entier et son moyen (en ligne ou cash).
2. Elle peut le modifier après coup, moyen compris.

## Règles liées

RG-014, RG-015, RG-019

## Critères d'acceptation

- Étant donné un carnet impayé ou en dette, quand Aurélie saisit son paiement en cash, alors le carnet est marqué payé cash et l'impayé ou la dette disparaît.
- Étant donné un paiement saisi avec un mauvais moyen, quand Aurélie le corrige, alors le moyen est mis à jour.
