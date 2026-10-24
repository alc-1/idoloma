# Idoloma — « I Don't LOose My Agenda »

Application de suivi des cours de l'atelier d'Aurélie : agenda, carnets de cours, paiements. Phase actuelle : **documentation fonctionnelle uniquement**.

## Phases

1. Digitalisation de l'agenda existant
2. Suivi financier
3. Réservation par les élèves

## Sources

- [docs/sources/notes-aurelie.md](docs/sources/notes-aurelie.md) : notes brutes d'Aurélie (incohérences connues, pas une spécification).
- [docs/sources/agenda-papier.png](docs/sources/agenda-papier.png) : photo de l'agenda papier, janvier 2023.

## Règles

- Toute la documentation est en **français** (le client la lit).
- Aucune mention de technologie dans `docs/fonctionnel/` (ça ira dans `docs/adr/`).
- Les notes brutes dans `docs/sources/` ne sont jamais modifiées.
- Identifiants stables : UC-001 (cas d'usage), RG-001 (règle de gestion), US-001 (user story). Ne jamais renuméroter.
- Critères d'acceptation au format Étant donné / Quand / Alors.
- Vocabulaire : respecter [docs/fonctionnel/01-glossaire.md](docs/fonctionnel/01-glossaire.md). Pour un nouveau terme, l'ajouter au glossaire avant de l'utiliser.
- **En cas d'ambiguïté ou de règle manquante : ne pas supposer.** Ajouter la question à [docs/fonctionnel/06-questions-ouvertes.md](docs/fonctionnel/06-questions-ouvertes.md) et la poser à l'utilisateur.
- Un document validé = un commit.

## Méthode de travail

- Avant de produire un document : lister les incohérences et zones floues, puis poser les questions par lots de 5 maximum jusqu'à lever les points bloquants.
- Arborescence de docs/ :
  - sources/ : notes brutes (lecture seule)
  - fonctionnel/ : 00-vision, 01-glossaire (rédigés), puis 02-acteurs, 03-cas-d-usage/, 04-regles-metier, 05-vues-et-legende (3 vues + code couleur, séparés des règles), 06-questions-ouvertes, 07-suivi-financier (phase 2)
  - adr/ : décisions d'architecture

## Décisions validées

- Capacité d'un cours de groupe : 6 places.
- Par défaut, 1 seul cours de groupe par jour ; plusieurs le même jour sont possibles mais exceptionnels.
- Tailles de carnet : 5, 15, 30 et 60 cours.
- Le paiement en retard reste autorisé : c'est un statut visible (« dette »), jamais un blocage.
- Vocabulaire : « carnet de cours » (jamais « abonnement ») ; « Disponibilité » (récurrente ou unique, sur une plage de temps, active ou archivée) pour ce qu'Aurélie ouvre ; « Cours » pour l'occurrence datée.
- Report (l'action) et rattrapage (le cours de remplacement) : ne pas utiliser « déplacement ». Un élève est reporté sur un autre cours de groupe de la même semaine, y compris complet ; décompte inchangé ; cours d'origine conservé et barré ; rattrapage à la discrétion d'Aurélie, il utilise le carnet.
- Retrait d'un cours : le carnet est utilisé par défaut ; absence justifiée et validée : carnet non utilisé et rattrapage possible sur un autre jour de la même semaine.
- Disponibilité : définie sur une plage de temps, modifiée ou archivée sur une plage donnée ; refusé si un élève est impacté.
- Cours qui n'ont pas lieu (vacances, maladie…) : la raison est conservée.
- Rendez-vous privés : facturés à part, hors carnet.
- Hors V1 : stages, réservation par les élèves, événements externes de la photo (ignorés), « élèves fantômes » (concept abandonné).
- Utilisateurs : Aurélie seule en V1, mais données ségréguées par atelier et par utilisateur dès la conception. Isolation totale : un compte et une instance dédiés par atelier, aucun croisement de données, même pour une même personne physique.
- Paramètres (6 places, carnets 5/15/30/60, seuils) : fixes pour l'instant, configuration par atelier reportée.
- Cours grisé à partir de 5 élèves (presque plein ou complet, capacité 6).
- Cours mis en évidence comme annulable si moins de 3 élèves, 0 compris.
- Rendez-vous privé : indépendant des cours de groupe, sur d'autres horaires, aucune place consommée.
- Un carnet n'expire pas : il reste valable tant qu'il reste des cours à utiliser.
- Absence sans justification valide : le carnet est utilisé par défaut. Absence justifiée et validée par Aurélie : le carnet n'est pas utilisé.
- Vocabulaire : ne pas utiliser « séance » ; on parle d'un carnet de cours, d'un élève qui va à un cours, et d'un carnet utilisé ou non.
- Inscription : tous les cours du carnet sont générés à l'avance, une place libre est requise sur chacun (6 max).
- Fin de carnet : l'élève peut continuer, cours rattachés à un nouveau carnet non payé (dette).
- Paiement d'un carnet de cours de groupe : toujours sur le carnet entier.
- Fermeture : le carnet n'est pas utilisé ; la série de l'élève est décalée (un cours ajouté en fin de série, qui exige une place libre ; le cas « complet » est ignoré, il ne se produit pas chez Aurélie). Une inscription qui traverse une fermeture est normale.
- Nouveau carnet de fin de carnet : taille par défaut 5, modifiable une fois confirmée avec l'élève.
- Rendez-vous privé : montant, statut payé ou non, moyen de paiement (en ligne ou cash).
- Paiements : saisie manuelle par Aurélie, modifiable après coup.
- Vues : quatre écrans (mois en lecture seule, semaine avec glisser-déposer uniquement, jour avec édition complète, fiche élève). Les états de la légende se cumulent. Mois : ni cours annulables ni fermetures.
- Retrait d'un élève : au niveau d'un seul cours. Corrections par action inverse (pas d'annulation générique). Fiche élève V1 : nom et prénom seulement ; vue globale des dettes hors V1. « Se connecter » relève des ADR.
- Légende des couleurs : à définir plus tard (celle de l'agenda papier est contradictoire).

## Questions ouvertes

Source unique : [docs/fonctionnel/06-questions-ouvertes.md](docs/fonctionnel/06-questions-ouvertes.md).
