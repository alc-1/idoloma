# 05 – Vues et légende

Ce document décrit ce que l'utilisateur voit et peut faire sur chaque écran, et les états à représenter. Les règles de gestion sont dans [04-regles-metier.md](04-regles-metier.md). Le choix des couleurs et des marqueurs n'est pas encore fait (voir « Légende »).

## Écrans

Il y a quatre écrans : trois vues du planning (mois, semaine, jour) et la fiche élève.

### Vue mois

Vision globale, minimaliste, **sans aucune fonctionnalité d'édition**.

- Met en évidence les cours qui ont de la disponibilité et indique le nombre de places encore libres.
- Signale la présence d'un rendez-vous privé en affichant uniquement l'heure.
- N'affiche ni les cours annulables, ni les fermetures.

Question à laquelle elle répond rapidement : « Quels cours peuvent accueillir un élève ? »

### Vue semaine

Vision affinée, avec une seule fonctionnalité d'édition.

- Détail des participants de chaque cours, avec le décompte de chacun (ex. 12/15).
- États de chaque participant (voir « Légende »).
- Détail des rendez-vous privés, affichés sous la forme « Christelle 14h ».
- Cours grisé à partir de 5 élèves (RG-003) ; cours annulable mis en évidence (RG-004).
- Édition : déplacer un élève d'un cours de groupe à un autre de la même semaine par glisser-déposer (RG-010).

### Vue jour

Vision détaillée, avec l'édition complète sur la journée concernée. Actions :

- inscrire un élève (RG-007) ;
- retirer un élève ;
- marquer une absence, justifiée ou non (RG-011) ;
- accorder un rattrapage (RG-012) ;
- saisir un paiement (RG-014, RG-018) ;
- créer un rendez-vous privé (RG-005) ;
- enregistrer une fermeture avec sa raison (RG-013).

La liste des actions pourra évoluer si des besoins manquent.

### Fiche élève

Écran propre à un élève, important dès la V1. Il permet de :

- consulter ses carnets de cours : décompte, état de paiement, dette (RG-008, RG-009, RG-015) ;
- retracer toutes les dates auxquelles l'élève a été présent (RG-016).

## Légende

États à représenter. La représentation (couleur, barré, marqueur…) reste à définir.

| Objet | État |
|---|---|
| Élève | carnet payé en ligne |
| Élève | carnet payé cash |
| Élève | en dette |
| Élève | dernier cours du carnet |
| Élève | rattrapage |
| Élève | déplacé (cours d'origine barré) |
| Cours | presque plein ou complet (grisé) |
| Cours | annulable (moins de 3 élèves) |
| Cours | fermé, avec sa raison |
| Rendez-vous privé | présent |

**Les états se cumulent** : un élève peut cumuler plusieurs états (par exemple dernier cours du carnet et en dette), et la représentation doit permettre de tous les voir ensemble.

Le premier cours d'un carnet et le surlignage rose « à élucider » de l'agenda papier ne font pas partie de la liste retenue. La légende des couleurs de l'agenda papier est contradictoire et ne doit pas être reprise telle quelle.
