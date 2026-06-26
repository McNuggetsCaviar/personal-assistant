# Personal Assistant — Assistant personnel autonome

## Objectif

Construire un assistant personnel autonome qui observe et assiste l'utilisateur
sur quatre domaines du quotidien, en s'appuyant sur un principe strict de
**human-in-the-loop** : l'assistant propose, l'utilisateur décide.

## Architecture

Le projet est composé de 4 skills modulaires, plus un module de traitement vocal :

- **Scheduler** — gestion du calendrier et des reminders (création, blocage de
  temps, rapprochement événement ↔ tâche).
- **Email responder** — suggestion de réponses aux emails, en respectant le ton
  propre à chaque relation (boss, collègue, client, famille, amis).
- **Knowledge retriever** — récupération d'informations pertinentes à partir des
  sources de l'utilisateur (mails, documents, notes).
- **Task suggester** — détection et catégorisation des tâches, y compris les
  tâches répétitivement repoussées, avec suggestion d'action.
- **Voice processor** — couche de traitement vocal transverse aux 4 skills
  (entrée/sortie vocale).

## Principe human-in-the-loop

Aucune action irréversible (envoi de mail, modification de calendrier,
complétion de tâche) n'est effectuée sans validation explicite de
l'utilisateur. L'assistant propose des brouillons, des suggestions ou des
résumés ; l'utilisateur valide, corrige ou rejette.

## Phase d'essai d'une semaine

Avant tout développement, une phase d'observation d'une semaine permet
d'ingérer :

- le calendrier et les reminders existants,
- les mails envoyés (pour en extraire les échantillons de ton),

afin de calibrer les master forms définis dans `docs/` sur des données réelles
plutôt que sur des hypothèses.

## Master forms

Les schémas de référence (format Markdown descriptif, pas de JSON Schema à ce
stade) sont disponibles dans `docs/` :

- [`docs/01-scheduler-calendar-schema.md`](docs/01-scheduler-calendar-schema.md)
- [`docs/02-email-tone-samples.md`](docs/02-email-tone-samples.md)
- [`docs/03-task-categories.md`](docs/03-task-categories.md)

## Prochaines étapes

- Reporting hebdomadaire sur les données ingérées pendant la phase d'essai.
- Intégration avec Lynx.
- Choix de la stack technique et passage des master forms à un schéma formel
  si nécessaire.
