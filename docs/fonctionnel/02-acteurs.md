# 02 – Acteurs

## Utilisateur (Aurélie)

Personne qui se connecte à l'application pour gérer son atelier. En V1, c'est Aurélie, seule.

Elle peut :

- consulter le planning (vues mois, semaine, jour) ;
- gérer ses élèves et leurs carnets de cours ;
- inscrire et reporter des élèves sur les cours, et marquer leurs absences ;
- gérer les disponibilités, les fermetures et les cours privés ;
- enregistrer les paiements (moyen, statut) et consulter les impayés et les dettes ;
- retracer toutes les dates de présence d'un élève.

Elle n'accède qu'aux données de son atelier. Son compte est propre à son atelier : une même personne qui gérerait deux ateliers aurait deux comptes distincts, sans aucun croisement de données.

## Élève

Personne suivie par l'atelier : elle a un ou plusieurs carnets et participe à des cours. En V1, **l'élève n'est pas un acteur de l'application** : il n'y a pas d'accès, c'est Aurélie qui tient son suivi. Il s'en remet entièrement à elle pour savoir où en est son carnet et quand repasser à la caisse.

En phase 3, l'élève deviendra un acteur : consultation des disponibilités, réservation de cours et paiement en ligne. Les droits correspondants seront définis à ce moment-là.

## Hors périmètre

- Autres utilisateurs d'un même atelier (assistante, remplaçante…) : non tranché, sans objet en V1 (voir [06-questions-ouvertes.md](06-questions-ouvertes.md)).
- Administrateur de la plateforme entre ateliers : non prévu.
