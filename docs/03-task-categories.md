# Master form — Task suggester (catégories de tâches)

Ce document décrit la taxonomie des catégories de tâches, les champs
attendus pour une tâche, et les critères permettant de détecter une tâche
"repoussée". Format Markdown descriptif, pas de schéma formel à ce stade.

## Taxonomie des catégories

- **Admin** — démarches administratives (impôts, papiers, factures, RDV
  administratifs).
- **Perso** — vie personnelle hors administratif (santé, maison, loisirs,
  relations).
- **Pro non-urgent** — tâches professionnelles sans échéance immédiate
  (par opposition aux tâches pro urgentes, gérées en dehors de ce suggester).
- **Récurrent vs ponctuel** — axe transverse aux catégories ci-dessus :
  une tâche récurrente revient à intervalle régulier (ex. "payer le loyer"),
  une tâche ponctuelle est à traiter une seule fois (ex. "renouveler la carte
  d'identité").

## Champs d'une tâche

| Champ | Description | Exemple |
|---|---|---|
| `source` | Origine de la détection de la tâche | "mail reçu", "reminder", "mention en conversation" |
| `urgence` | Niveau d'urgence perçu | basse / moyenne / haute |
| `nombre de fois repoussée` | Compteur d'occurrences où la tâche a été reportée sans être traitée | 3 |
| `dernière mention` | Date de la dernière fois où la tâche a été évoquée ou détectée | 2026-06-20 |
| `action suggérée` | Action proposée par l'assistant | "bloquer 30 min demain matin", "relancer le contact" |

## Critères de détection d'une tâche "repoussée"

Une tâche est considérée comme repoussée lorsqu'au moins un des critères
suivants est observé :

- la même tâche (ou une tâche très similaire) est mentionnée à plusieurs
  reprises dans des sources différentes (mails, reminders, conversations)
  sans avoir été marquée complétée entre ces mentions,
- une échéance associée à la tâche est dépassée sans que la tâche soit
  complétée,
- un événement de blocage de temps lié à la tâche a été déplacé ou annulé
  plusieurs fois.

## Exemples concrets

**Tâche Admin récurrente**

> Source : reminder
> Catégorie : Admin, récurrent
> Urgence : moyenne
> Nombre de fois repoussée : 0
> Dernière mention : 2026-06-25
> Action suggérée : "bloquer 15 min vendredi pour payer la facture EDF"

**Tâche Perso ponctuelle repoussée**

> Source : mail reçu + mention en conversation
> Catégorie : Perso, ponctuel
> Urgence : haute
> Nombre de fois repoussée : 4
> Dernière mention : 2026-06-24
> Action suggérée : "prendre RDV chez le dentiste cette semaine"

**Tâche Pro non-urgente**

> Source : mail reçu
> Catégorie : Pro non-urgent, ponctuel
> Urgence : basse
> Nombre de fois repoussée : 1
> Dernière mention : 2026-06-22
> Action suggérée : "relire le compte-rendu avant la prochaine réunion d'équipe"
