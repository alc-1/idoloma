# 04 – Règles métier

Les identifiants sont stables : ne jamais renuméroter. Une règle abandonnée est marquée « abandonnée », pas supprimée. Vocabulaire : voir [01-glossaire.md](01-glossaire.md).

## Cours et capacité

### RG-001 – Capacité d'un cours de groupe
Un cours de groupe accueille au plus 6 élèves par inscription.
- Étant donné un cours de groupe à 6 élèves, quand Aurélie inscrit un élève, alors l'inscription est refusée pour ce cours (voir RG-007).

### RG-002 – Un cours de groupe par jour
Par défaut, il y a au plus un cours de groupe par jour. Plusieurs cours de groupe le même jour restent possibles, à titre exceptionnel.

### RG-003 – Cours grisé
Un cours de groupe est grisé à partir de 5 élèves (presque plein ou complet). Il n'y a pas de distinction entre 5 et 6.
- Étant donné un cours à 4 élèves, quand un cinquième est inscrit, alors le cours devient grisé.

### RG-004 – Cours annulable
Un cours de groupe à moins de 3 élèves, y compris 0, est mis en évidence comme pouvant être annulé.
- Étant donné un cours à 2 élèves, quand on consulte le planning, alors il est mis en évidence.
- Étant donné un cours à 0 élève, quand on consulte le planning, alors il est mis en évidence.

### RG-005 – Rendez-vous privé
Un rendez-vous privé est une occurrence unique sur une période fixée dans la même journée. Il est indépendant des cours de groupe : il a lieu sur d'autres horaires et ne consomme aucune place d'un cours de groupe. Il est facturé à part, hors carnet.

## Carnet de cours

### RG-006 – Taille et validité
Un carnet porte 5, 15, 30 ou 60 cours. Il n'expire pas : il reste valable tant qu'il reste des cours à utiliser.

### RG-007 – Inscription et génération des cours
Quand Aurélie inscrit un élève à partir d'une date donnée, sur une disponibilité donnée, pour un carnet, tous les cours correspondant au nombre de cours du carnet sont générés à l'avance. L'inscription n'est possible que si chacun de ces cours a une place libre. Une série qui traverse une fermeture est normale : voir RG-013.
- Étant donné un carnet de 15 cours et un cours de la série déjà à 6 élèves, quand Aurélie tente l'inscription, alors elle est refusée.
- Étant donné une place libre sur chaque cours de la série, quand Aurélie inscrit l'élève, alors l'élève apparaît sur tous les cours de la série.

### RG-008 – Décompte
L'avancement d'un élève dans son carnet est noté « n° du cours / total » (ex. 12/15). Le dernier cours du carnet est mis en évidence.

### RG-009 – Fin de carnet et dette
Un élève peut continuer à venir après avoir utilisé tous les cours de son carnet. Les cours suivants sont alors rattachés à un nouveau carnet non payé : ils constituent une dette. Ce nouveau carnet a une taille par défaut de 5 cours ; elle peut être modifiée une fois la taille confirmée avec l'élève.
- Étant donné un élève ayant utilisé tous les cours de son carnet, quand il vient à un cours supplémentaire, alors ce cours est rattaché à un nouveau carnet non payé et l'élève est signalé en dette.

## Déplacements, absences, fermetures

### RG-010 – Déplacement
Aurélie peut déplacer un élève d'un cours de groupe vers un autre cours de groupe de la même semaine, y compris un cours déjà complet. Le décompte du carnet est inchangé. Le cours d'origine est conservé et barré pour tracer le déplacement.
- Étant donné un élève inscrit le mardi et un cours complet le jeudi de la même semaine, quand Aurélie déplace l'élève au jeudi, alors le déplacement est accepté et le cours du mardi est conservé et barré.
- Étant donné un cours dans une autre semaine, quand Aurélie tente d'y déplacer l'élève, alors le déplacement est refusé.

### RG-011 – Absence
Une absence sans justification valide utilise le carnet par défaut. Une absence justifiée et validée par Aurélie ne l'utilise pas et peut donner lieu à un rattrapage (RG-012).
- Étant donné un élève absent sans justification valide, quand le cours a lieu, alors le carnet est utilisé.
- Étant donné une absence justifiée et validée par Aurélie, quand le cours a lieu, alors le carnet n'est pas utilisé.

### RG-012 – Rattrapage
Un rattrapage est accordé à la discrétion d'Aurélie, notamment pour une fermeture de l'atelier ou une absence justifiée. Il utilise le carnet comme tout cours auquel l'élève participe.

### RG-013 – Fermeture
Une période de fermeture (vacances, maladie…) rend les cours concernés indisponibles. Les cours restent enregistrés avec leur statut et la raison de la fermeture. Le carnet des élèves inscrits n'est pas utilisé. La série de chaque élève inscrit est décalée : un cours est ajouté à la fin de sa série pour chaque cours fermé. Ce cours ajouté exige une place libre ; le cas d'un cours complet n'est pas traité, car il ne se présente pas dans l'organisation d'Aurélie.
- Étant donné un cours inscrit un jour de fermeture, quand la fermeture est enregistrée avec sa raison, alors le cours devient indisponible, le carnet n'est pas utilisé et un cours est ajouté à la fin de la série de l'élève.

## Paiement

### RG-014 – Paiement d'un carnet
Pour les cours de groupe, un paiement porte toujours sur un carnet entier. Le moyen de paiement est en ligne ou cash. Les paiements sont saisis manuellement par Aurélie et peuvent être modifiés après coup (moyen de paiement compris).

### RG-015 – Paiement en retard
Un élève peut être inscrit et suivre des cours sans avoir payé son carnet. Le défaut de paiement est un statut visible (dette) et ne bloque jamais l'inscription ni la participation.

## Traçabilité et isolation

### RG-018 – Paiement d'un rendez-vous privé
Un rendez-vous privé, facturé à part, est enregistré avec un montant, un statut payé ou non, et un moyen de paiement (en ligne ou cash). Il est saisi manuellement par Aurélie et modifiable après coup.
- Étant donné un rendez-vous privé non payé, quand Aurélie saisit le paiement et son moyen, alors le rendez-vous est marqué payé.

### RG-016 – Historique des présences
Toutes les dates auxquelles un élève a été présent peuvent être retracées.

### RG-017 – Isolation par atelier
Les données d'un atelier ne sont jamais accessibles depuis un autre atelier, et aucune opération ne croise les données de plusieurs ateliers.
