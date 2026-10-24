# 04 – Règles métier

Les identifiants sont stables : ne jamais renuméroter. Une règle abandonnée est marquée « abandonnée », pas supprimée. Vocabulaire : voir [01-glossaire.md](01-glossaire.md).

## Cours et capacité

### RG-001 – Capacité d'un cours de groupe
Un cours de groupe accueille au plus 6 élèves par inscription. Un report vers un cours complet (RG-010) peut dépasser cette limite.
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
Quand Aurélie inscrit un élève à partir d'une date donnée, sur une disponibilité donnée, pour un carnet, tous les cours correspondant au nombre de cours du carnet sont générés à l'avance. L'inscription n'est possible que si chacun de ces cours a une place libre. Une série qui traverse une fermeture est normale : voir RG-013. L'inscription est refusée si la série dépasse la plage de temps de la disponibilité (RG-020).
- Étant donné un carnet de 15 cours et un cours de la série déjà à 6 élèves, quand Aurélie tente l'inscription, alors elle est refusée.
- Étant donné une place libre sur chaque cours de la série, quand Aurélie inscrit l'élève, alors l'élève apparaît sur tous les cours de la série.
- Étant donné une disponibilité qui s'arrête en septembre et une série de 15 cours qui irait jusqu'en octobre, quand Aurélie tente l'inscription, alors elle est refusée.

### RG-008 – Décompte
L'avancement d'un élève dans son carnet est noté « n° du cours / total » (ex. 12/15). Le dernier cours du carnet est mis en évidence.

### RG-009 – Fin de carnet et dette
Un élève peut continuer à venir après avoir utilisé tous les cours de son carnet. Les cours suivants sont alors rattachés à un nouveau carnet non payé : ils constituent une dette. Ce nouveau carnet a une taille par défaut de 5 cours ; elle peut être modifiée une fois la taille confirmée avec l'élève.
- Étant donné un élève ayant utilisé tous les cours de son carnet, quand il vient à un cours supplémentaire, alors ce cours est rattaché à un nouveau carnet non payé et l'élève est signalé en dette.

## Report, absences, fermetures

### RG-010 – Report et rattrapage
Aurélie peut reporter un élève d'un cours de groupe vers un autre cours de groupe de la même semaine, y compris un cours déjà complet. Le cours de destination est un rattrapage, accordé à la discrétion d'Aurélie. Le cours d'origine est conservé et barré pour tracer le report. Le décompte du carnet est inchangé : le cours d'origine n'utilise pas le carnet, le rattrapage l'utilise comme tout cours auquel l'élève participe.
- Étant donné un élève inscrit le mardi et un cours complet le jeudi de la même semaine, quand Aurélie reporte l'élève au jeudi, alors le report est accepté, le jeudi est un rattrapage et le cours du mardi est conservé et barré.
- Étant donné un cours dans une autre semaine, quand Aurélie tente d'y reporter l'élève, alors le report est refusé.

### RG-011 – Absence
Une absence à un cours sans justification valide utilise le carnet par défaut. Dans tous les cas, un élève absent libère sa place dans le cours : il n'est pas compté pour la capacité, le grisage (RG-003) ni le caractère annulable (RG-004). Une absence justifiée et validée par Aurélie ne l'utilise pas et permet un rattrapage sur un autre jour de la même semaine (RG-010).
- Étant donné un élève absent sans justification valide, quand le cours a lieu, alors le carnet est utilisé.
- Étant donné un cours à 6 élèves dont un est absent, quand Aurélie consulte le planning, alors le cours compte 5 élèves et 1 place est libre.
- Étant donné une absence justifiée et validée par Aurélie, quand le cours a lieu, alors le carnet n'est pas utilisé et un rattrapage est possible sur un autre jour de la même semaine.

### RG-012 – Rattrapage (abandonnée)
Fusionnée dans RG-010 : rattrapage et déplacement désignent le même concept. L'identifiant est conservé.

### RG-013 – Fermeture
Une période de fermeture (vacances, maladie…) rend les cours concernés indisponibles. Les cours restent enregistrés avec leur statut et la raison de la fermeture. Le carnet des élèves inscrits n'est pas utilisé. Pour chaque élève inscrit, Aurélie choisit au cas par cas entre :
- décaler sa série : un cours est ajouté à la fin de sa série pour chaque cours fermé ;
- lui accorder un rattrapage sur un autre jour de la même semaine (RG-010).

Le cours ajouté en fin de série exige une place libre ; le cas d'un cours complet n'est pas traité, car il ne se présente pas dans l'organisation d'Aurélie.
- Étant donné un cours inscrit un jour de fermeture, quand la fermeture est enregistrée avec sa raison, alors le cours devient indisponible et le carnet n'est pas utilisé.
- Étant donné cette fermeture, quand Aurélie choisit de décaler la série d'un élève, alors un cours est ajouté à la fin de sa série.
- Étant donné cette fermeture, quand Aurélie choisit un rattrapage pour un élève, alors il est reporté sur un autre jour de la même semaine.

## Paiement

### RG-014 – Paiement d'un carnet
Pour les cours de groupe, un paiement porte toujours sur un carnet entier. Le moyen de paiement est en ligne ou cash. Les paiements sont saisis manuellement par Aurélie et peuvent être modifiés après coup (moyen de paiement compris).

### RG-015 – Impayé et dette
Un élève peut être inscrit et suivre des cours sans avoir payé son carnet. Un carnet non payé est un impayé tant qu'aucun de ses cours n'est utilisé, et une dette dès qu'un de ses cours est utilisé. Ces deux statuts sont visibles, appellent un suivi d'Aurélie et ne bloquent jamais l'inscription ni la participation.
- Étant donné un carnet non payé dont aucun cours n'est utilisé, quand Aurélie consulte l'élève, alors le carnet est signalé impayé.
- Étant donné un carnet non payé dont un cours est utilisé, quand Aurélie consulte l'élève, alors le carnet est signalé en dette.

### RG-018 – Paiement d'un rendez-vous privé
Un rendez-vous privé, facturé à part, est enregistré avec un montant, un statut payé ou non, et un moyen de paiement (en ligne ou cash). Il est saisi manuellement par Aurélie et modifiable après coup.
- Étant donné un rendez-vous privé non payé, quand Aurélie saisit le paiement et son moyen, alors le rendez-vous est marqué payé.

## Disponibilités

### RG-020 – Modification d'une disponibilité
Une disponibilité est définie sur une plage de temps (par exemple de janvier à septembre). Elle est modifiée ou archivée sur une plage de temps donnée (par exemple à partir d'octobre). La modification ou l'archivage est refusé si au moins un élève inscrit à un cours concerné est impacté : l'application garantit qu'aucun élève n'est impacté.
- Étant donné une disponibilité de janvier à septembre sans élève inscrit à partir d'octobre, quand Aurélie la modifie à partir d'octobre, alors la modification est acceptée.
- Étant donné un élève inscrit à un cours d'octobre, quand Aurélie tente de modifier la disponibilité à partir d'octobre, alors la modification est refusée.

## Corrections

### RG-019 – Correction par action inverse
Une action (report, absence, fermeture, paiement…) se corrige par l'action inverse. Il n'y a pas de fonction générique d'annulation.
- Étant donné un élève marqué absent par erreur, quand Aurélie retire l'absence, alors la situation est rétablie.

## Traçabilité et isolation

### RG-016 – Historique des présences
Un élève inscrit à un cours est présent par défaut, sauf absence marquée (RG-011). Toutes les dates auxquelles un élève a été présent peuvent être retracées.
- Étant donné un élève inscrit à un cours sans absence marquée, quand le cours a eu lieu, alors l'élève est présent à cette date.
- Étant donné un élève dont l'absence est marquée à un cours, quand Aurélie consulte l'historique, alors cette date n'apparaît pas comme présence.

### RG-021 – Dernière version uniquement
Les opérations sont conservées dans leur dernière version uniquement : il n'y a pas de journal d'audit des modifications successives.

### RG-017 – Isolation par atelier
Les données d'un atelier ne sont jamais accessibles depuis un autre atelier, et aucune opération ne croise les données de plusieurs ateliers.
