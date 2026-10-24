# UC-014 – Consulter la fiche élève

**Acteur** : Aurélie

**Préconditions** : L'élève existe.

## Scénario nominal

1. Aurélie ouvre la fiche d'un élève.
2. Elle voit ses carnets (décompte, état de paiement, impayé, dette) et toutes les dates auxquelles l'élève a été présent.
3. Elle peut saisir ou modifier le paiement d'un carnet depuis la fiche (UC-015).

## Règles liées

RG-008, RG-009, RG-014, RG-015, RG-016

## Critères d'acceptation

- Étant donné un élève avec deux carnets dont un non payé, quand Aurélie ouvre sa fiche, alors elle voit le décompte et l'état de paiement de chaque carnet, et l'impayé ou la dette.
- Étant donné un élève présent à plusieurs cours, quand Aurélie ouvre sa fiche, alors elle voit toutes les dates de présence.
- Étant donné un carnet non payé sur la fiche d'un élève, quand Aurélie y saisit le paiement, alors le carnet est marqué payé sans quitter la fiche.
