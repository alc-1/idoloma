# UC-001 – Consulter le planning du mois

**Acteur** : Aurélie

**Préconditions** : Aurélie est connectée.

## Scénario nominal

1. Aurélie ouvre la vue mois.
2. Pour chaque jour, elle voit les cours qui ont de la disponibilité avec le nombre de places libres, et l'heure des rendez-vous privés.

## Variantes et erreurs

- Aucune édition n'est possible depuis cette vue.

## Règles liées

RG-001, RG-005

## Critères d'acceptation

- Étant donné un cours à 4 élèves, quand Aurélie ouvre la vue mois, alors elle voit 2 places libres pour ce cours.
- Étant donné un rendez-vous privé de Christelle à 14h, quand Aurélie ouvre la vue mois, alors elle voit 14h sans le nom.
- Étant donné un cours à 1 élève ou une fermeture, quand Aurélie ouvre la vue mois, alors ni le caractère annulable ni la fermeture n'apparaissent.
- Étant donné la vue mois, quand Aurélie cherche à modifier un cours, alors aucune action d'édition n'est proposée.
