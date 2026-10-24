# 01 – Glossaire

Vocabulaire métier de référence. En cas de doute, ce document prévaut sur les notes brutes d'Aurélie.

| Terme | Définition |
|---|---|
| **Fiche élève** | Écran propre à un élève : ses carnets (décompte, paiement, impayé, dette), la saisie du paiement d'un carnet et l'historique de ses présences. |
| **Atelier** | Structure qui donne les cours (aujourd'hui celui d'Aurélie). Les données (élèves, disponibilités, cours, carnets, paiements) sont totalement isolées par atelier : aucun croisement entre ateliers. |
| **Utilisateur** | Compte qui se connecte à l'application, propre à un atelier (une même personne physique aurait un compte distinct par atelier). Aurélie en V1. |
| **Élève** | Personne susceptible de s'inscrire à des cours. Existe indépendamment de ses carnets et de ses cours. |
| **Disponibilité** | Ce qu'Aurélie ouvre pour accueillir des cours : récurrente (ex. mardi 17h) ou unique, définie sur une plage de temps (ex. de janvier à septembre), active ou archivée. Remplace « plage de cours ouverte », « créneau » et « Availability ». |
| **Cours** | Occurrence datée issue d'une disponibilité. Un cours de groupe accueille jusqu'à 6 élèves à l'inscription ; un report peut en faire dépasser ce nombre. |
| **Cours de groupe** | Cours collectif, issu d'une disponibilité récurrente. Par défaut, 1 par jour au maximum. |
| **Rendez-vous privé** | Cours privé : occurrence unique, sur une période fixée dans la même journée. Facturé à part, hors carnet. Affiché sous la forme « Christelle 14h ». |
| **Carnet de cours** | Inscription d'un élève pour un nombre donné de cours (5, 15, 30 ou 60), à partir d'une date donnée, sur une disponibilité de cours de groupe. Reste valable tant qu'il reste des cours à utiliser (pas d'expiration). Porte le suivi financier : est-il payé ? Remplace « abonnement ». |
| **Inscription** | Présence d'un élève sur un cours précis. Elle découle du carnet : le carnet inscrit l'élève aux cours, mais l'élève peut être reporté dans la même semaine. |
| **Décompte** | Avancement d'un élève dans son carnet, noté « n° du cours actuel / total » (ex. 12/15). Le carnet est utilisé quand l'élève participe à un cours, ou est absent sans justification valide ; il ne l'est pas en cas d'absence justifiée validée par Aurélie ni de fermeture. Le dernier cours du carnet est mis en évidence. |
| **Absence** | Un élève inscrit à un cours n'y participe pas. Concerne un seul cours. L'élève libère sa place dans le cours. Le carnet est utilisé, sauf si l'absence est justifiée et validée par Aurélie. Remplace « retrait ». |
| **Rattrapage** | Cours de remplacement d'un cours manqué ou reporté, sur un autre jour de la même semaine, accordé à la discrétion d'Aurélie (absence justifiée, fermeture…). Utilise le carnet comme tout cours auquel l'élève participe ; le cours d'origine est conservé et barré. |
| **Report** | Action d'Aurélie qui fait passer un élève d'un cours de groupe à un autre de la même semaine. Elle mène à un rattrapage. Le décompte est inchangé. |
| **Fermeture** | Période pendant laquelle des cours n'ont pas lieu. Les cours restent enregistrés avec un statut indisponible et une raison (vacances, maladie…). Pour chaque élève concerné, Aurélie choisit au cas par cas de décaler sa série ou de lui accorder un rattrapage. |
| **Impayé** | Statut visible d'un carnet non payé dont aucun cours n'a encore été utilisé. Appelle un suivi d'Aurélie. Jamais bloquant. |
| **Dette** | Statut visible d'un carnet non payé dont au moins un cours a été utilisé. Appelle un suivi d'Aurélie. Jamais bloquante. |
| **Entrées effectives** | Argent réellement encaissé. |
| **Entrées attendues** | Argent correspondant à toutes les prestations données, payées ou non. |
| **Moyen de paiement** | En ligne ou cash. |

## Termes abandonnés

- **Abonnement** : remplacé par *carnet de cours*.
- **Plage de cours (ouverte)**, **créneau**, **Availability** : remplacés par *disponibilité* (ou *cours* selon le cas).
- **Élève fantôme** : concept abandonné.
- **Stage** : hors périmètre V1.
- **Retrait** : fusionné dans *absence*.
- **Déplacement** : abandonné, remplacé par *report* (l'action) et *rattrapage* (le cours).
