# Master form — Email responder (échantillons de ton)

Ce document décrit la structure d'un **échantillon d'apprentissage** utilisé
pour calibrer le ton des réponses suggérées par l'assistant, ainsi que la
catégorisation par relation qui permet de construire des profils de ton
distincts. Format Markdown descriptif, pas de schéma formel à ce stade.

## Structure d'un échantillon

| Champ | Description | Exemple |
|---|---|---|
| `contexte / destinataire` | Qui est le destinataire et dans quel contexte | "Manager direct, suite à une demande de congés" |
| `email reçu` | Contenu (ou résumé) de l'email reçu, déclencheur de la réponse | "Bonjour Elie, est-ce que tu peux..." |
| `réponse envoyée` | Réponse réellement envoyée par l'utilisateur | "Bonjour, oui pas de souci, je m'en occupe dès demain." |
| `tags de ton` | Un ou plusieurs tags caractérisant le ton employé | formel / familier / chaleureux / sec |
| `style de salutation` | Formule d'ouverture utilisée | "Bonjour", "Salut", "Hello" |
| `style de signature` | Formule de clôture utilisée | "Cordialement", "À bientôt", "Bisous" |

## Catégorisation par relation

Chaque échantillon est rattaché à une catégorie de relation, afin de
construire des profils de ton distincts par catégorie plutôt qu'un ton
unique :

- **Boss** — hiérarchie directe ou indirecte.
- **Collègue** — pairs, même niveau hiérarchique.
- **Client** — contacts externes professionnels.
- **Famille** — proches familiaux.
- **Amis** — relations personnelles informelles.

Un même destinataire peut, en théorie, relever de plusieurs catégories
suivant le sujet de l'échange (ex. un collègue devenu ami) ; dans ce cas
l'échantillon précise la catégorie qui correspond au contexte de l'échange,
et non au destinataire en général.

## Exemples concrets

**Échantillon — Boss**

> Contexte : Manager direct, suite à une demande de congés
> Email reçu : "Bonjour Elie, est-ce que tu peux confirmer tes dates de congés pour juillet ?"
> Réponse envoyée : "Bonjour, oui je confirme du 14 au 21 juillet. N'hésitez pas si besoin d'infos complémentaires."
> Tags de ton : formel
> Salutation : "Bonjour"
> Signature : (aucune signature explicite, fin directe)

**Échantillon — Ami**

> Contexte : Ami proche, organisation d'un week-end
> Email reçu : "Hey, toujours ok pour ce week-end ?"
> Réponse envoyée : "Yes carrément, j'arrive samedi matin, on se cale ça !"
> Tags de ton : familier, chaleureux
> Salutation : (aucune, réponse directe)
> Signature : (aucune)

**Échantillon — Client**

> Contexte : Client externe, suivi de dossier
> Email reçu : "Bonjour, pourriez-vous nous donner un état d'avancement du dossier ?"
> Réponse envoyée : "Bonjour, le dossier avance comme prévu, livraison estimée la semaine prochaine. Cordialement,"
> Tags de ton : formel
> Salutation : "Bonjour"
> Signature : "Cordialement"
