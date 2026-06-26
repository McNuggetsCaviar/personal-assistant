# Master form — Scheduler (calendrier & reminders)

Ce document décrit, en langage naturel, les champs attendus pour un
**événement** et pour un **reminder**, ainsi que le lien entre un événement et
une tâche pour le blocage de temps. Il sert de référence pendant la phase
d'ingestion (calendrier + reminders réels) et n'est pas un schéma formel.

## Événement (event)

| Champ | Description | Exemple |
|---|---|---|
| `titre` | Intitulé court de l'événement | "Point équipe hebdo" |
| `début` | Date et heure de début | 2026-06-29 09:00 |
| `fin` | Date et heure de fin | 2026-06-29 09:30 |
| `fuseau` | Fuseau horaire de l'événement | Europe/Paris |
| `lieu` | Lieu physique ou lien de visio | "Salle 3" / "https://meet..." |
| `participants` | Liste des personnes invitées | ["Elie", "Marc"] |
| `récurrence` | Règle de répétition, si applicable | "toutes les semaines, le lundi" |
| `source` | Origine de l'événement (calendrier ingéré, créé par l'assistant, etc.) | "Google Calendar perso" |
| `statut` | État de l'événement | confirmé / provisoire / annulé |

## Reminder

| Champ | Description | Exemple |
|---|---|---|
| `échéance` | Date (et heure si pertinente) à laquelle le reminder doit être traité | 2026-06-30 |
| `complété` | Booléen indiquant si le reminder a été traité | true / false |
| `liste / catégorie` | Liste ou catégorie d'appartenance | "Maison", "Pro" |
| `priorité` | Niveau d'importance | basse / moyenne / haute |

## Lien événement ↔ tâche (blocage de temps)

Un événement peut être créé pour bloquer du temps dédié à une tâche. Dans ce
cas, l'événement référence la tâche d'origine (identifiant ou titre de la
tâche), de façon à ce que :

- compléter la tâche puisse proposer de libérer ou clôturer l'événement
  associé,
- déplacer l'événement de blocage de temps n'affecte pas l'échéance réelle de
  la tâche, mais seulement le moment prévu pour y travailler.

## Exemples concrets

**Événement classique**

> Titre : "Dentiste"
> Début : 2026-07-02 14:00 — Fin : 2026-07-02 14:45
> Fuseau : Europe/Paris
> Lieu : "12 rue de la Paix"
> Participants : []
> Récurrence : aucune
> Source : "Google Calendar perso"
> Statut : confirmé

**Reminder simple**

> Échéance : 2026-06-27
> Complété : false
> Liste : "Admin"
> Priorité : moyenne

**Blocage de temps lié à une tâche**

> Titre : "Préparer le rapport trimestriel"
> Début : 2026-06-26 16:00 — Fin : 2026-06-26 18:00
> Lien tâche : "Rapport trimestriel Q2"
> Source : "créé par l'assistant"
> Statut : provisoire
