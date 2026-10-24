# 00 – Vision

## Contexte

L'atelier d'Aurélie gère ses cours sur un agenda 100 % papier. Ce document est vital au fonctionnement de l'atelier, mais il est sujet à erreurs, difficile à suivre, et sa perte (frayeur de début 2021) paralyserait l'activité. Les élèves ne suivent pas l'avancement de leur carnet de cours et s'en remettent entièrement à Aurélie pour savoir quand repasser à la caisse.

**Idoloma** (« I DOn't LOose My Agenda ») numérise cet agenda.

## Objectif de la V1

Reproduire numériquement l'agenda papier tel qu'il existe, en le rendant plus fiable et plus lisible. Répondre rapidement à :

- Quels cours peuvent accueillir un élève ?
- Où en est chaque élève dans son carnet de cours ?
- Qui doit payer (impayés et dettes visibles) ?
- Quels cours privés sont prévus ?
- À quelles dates un élève a-t-il été présent ?

## Périmètre V1

- **Planning** : disponibilités, cours de groupe, cours privés, avec leurs participants.
- **Gestion des élèves et des carnets** : suivi de l'avancement (n° du cours / total du carnet : 5, 15, 30 ou 60).
- **Gestion des paiements** : moyen de paiement (TWINT, QR-facture ou cash) et statut de paiement par carnet. Le paiement en retard est autorisé et affiché comme impayé ou dette, jamais bloqué.
- **Traçabilité** : présences, reports et fermetures (avec leur raison). Les opérations sont conservées dans leur dernière version uniquement, sans journal d'audit.
- **Vues** : mois (lecture seule, disponibilités), semaine (détail et report par glisser-déposer au sein de la semaine), jour (édition complète).

## Phases

1. **Digitalisation de l'agenda existant** (V1, périmètre ci-dessus).
2. **Suivi financier** : sommes encaissées (en ligne / cash) par élève, par mois et en total actuel, pour que Aurélie détermine son salaire ; distinction entre entrées effectives (argent réellement entré) et entrées attendues (prestations données).
3. **Réservation par les élèves** : choix des cours et paiement en ligne.

## Hors périmètre V1

- Suivi financier agrégé (phase 2) et réservation par les élèves (phase 3).
- Stages (événements de plusieurs jours).
- Journal d'audit des modifications (RG-021).
- Événements externes notés sur l'agenda papier (à ignorer).
- Concept d'« élève fantôme » (abandonné).
- Vue globale des impayés et dettes de l'atelier (liste des élèves à relancer) : voulue, mais pas en V1. Ils restent visibles dans le planning et sur la fiche élève.
- Contact et notes sur la fiche élève : la V1 ne conserve que le nom et le prénom.

## Utilisateurs

Aurélie est la seule utilisatrice en V1, pour son propre atelier. L'application doit toutefois être conçue dès le départ avec :

- une **isolation complète par atelier**, pour pouvoir servir d'autres ateliers plus tard : chaque atelier a son compte et son instance dédiés, sans aucun croisement de données. Une même personne physique qui gère deux ateliers aurait deux comptes distincts ;
- une **séparation des données par utilisateur**, pour permettre d'autres utilisateurs plus tard (dont, à terme, les élèves).

Les paramètres de l'atelier (6 places, carnets de 5/15/30/60, seuils d'alerte) sont **communs et fixes** pour l'instant, ceux d'Aurélie. Leur configuration par atelier est reportée.

## Règles métier validées

- Un cours de groupe accueille au plus 7 élèves : 6 places d'inscription et 1 place de rattrapage.
- Il n'y a jamais plus d'un cours de groupe par jour ; un cours de groupe et un cours privé, ou deux cours privés, le même jour sont possibles.
- Un élève reporté dans la semaine suit un rattrapage : son décompte de carnet est inchangé et le cours d'origine est conservé et barré. Le rattrapage est accordé à la discrétion d'Aurélie.
- Une disponibilité est définie sur une plage de temps ; la modifier ou l'archiver sur une plage donnée est refusé si un élève en est impacté.
- Une période de fermeture (vacances, maladie…) conserve sa raison ; pour chaque élève concerné, Aurélie choisit au cas par cas de décaler sa série ou de lui accorder un rattrapage.
- Les cours privés sont facturés à part (hors carnet), incluent des élèves identifiés et mentionnent leur nombre.

## Questions ouvertes

Voir [06-questions-ouvertes.md](06-questions-ouvertes.md).
