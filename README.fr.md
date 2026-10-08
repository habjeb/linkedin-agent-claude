# linkedin-agent-claude

Un skill qui transforme Claude en agent de prospection LinkedIn pour **votre** activité.

Vous dites qui vous ciblez et ce que vous proposez. Claude trouve des prospects qualifiés, vérifie chacun pour de vrai (site web, dirigeant, profil LinkedIn), écrit une note de connexion personnelle qui sonne comme si vous l'aviez écrite, consigne tout dans un registre partagé et, une fois la liste validée par vous, envoie les invitations depuis votre propre compte LinkedIn.

[English version](README.md)

## Ce qu'il fait

1. **Mise en place.** Au premier lancement, deux questions : qui ciblez-vous, que proposez-vous. Claude enregistre vos réponses et crée un registre. Il lit ensuite quel compte LinkedIn est connecté, pour attribuer chaque invitation à la bonne personne.
2. **Recherche.** Par région et par segment : ouverture du site de chaque prospect, dirigeant identifié dans les registres officiels, profil LinkedIn confirmé. Un candidat qui ne passe pas la vérification est écarté, jamais ajouté pour faire du volume.
3. **Rédaction.** Une note par prospect, construite sur un détail vérifié, votre offre principale en premier, une question simple pour finir. Règles strictes contre les tournures « IA » et les messages répétitifs.
4. **Validation.** Vous voyez la liste complète avec chaque note. Rien ne part sans votre feu vert.
5. **Envoi.** Pour chaque prospect : réservation dans le registre, ouverture du profil, invitation envoyée avec sa note, vérification qu'elle est en attente. Puis contrôle final dans les invitations envoyées de LinkedIn et compte rendu court.

Pensé pour les équipes : deux personnes qui prospectent avec deux comptes LinkedIn partagent un registre et n'invitent jamais deux fois la même personne. Chaque ligne indique quel compte l'a contactée.

## Exemples

> Trouve-moi 20 clubs de padel en Belgique et en Suisse qui auraient besoin d'un meilleur outil de réservation, et prépare les invitations.

> Lance 15 invitations parmi les prospects « À contacter ».

> Marie a accepté, prépare-moi une relance.

## Prérequis

- Claude avec les skills activés : claude.ai (offre payante avec exécution de code) ou Claude Code.
- Un outil de navigateur que Claude peut piloter dans votre session connectée : le navigateur intégré à l'app de bureau Claude, l'extension Claude in Chrome, ou un autre outil d'automatisation. Sans cela, le skill fait la recherche et la rédaction, et vous envoyez vous-même.
- La recherche web.
- En option : les Artifacts avec base de données (claude.ai) pour un registre partagé en page web. Sinon, le registre est un fichier CSV.

## Installation

**claude.ai :** téléchargez ce dépôt en zip, gardez seulement le dossier `skills/linkedin-agent`, zippez ce dossier et importez-le dans les Paramètres (section Fonctionnalités / Skills). Le menu exact peut changer : voir la documentation Anthropic sur les Agent Skills.

**Claude Code :** copiez `skills/linkedin-agent` dans `~/.claude/skills/` (tous les projets) ou `.claude/skills/` (un projet).

Ensuite, demandez simplement à Claude de prospecter : le skill se déclenche tout seul.

## Garde-fous intégrés

- Claude ne saisit jamais votre mot de passe ni aucun code. Vous vous connectez vous-même.
- Rien n'est envoyé sans votre validation explicite de la liste exacte.
- Plafond par défaut : 20 invitations par session et par compte.
- Claude s'arrête et vous rend la main au moindre CAPTCHA, vérification, limite ou avertissement. Il ne tente jamais de les contourner.
- Chaque fait cité dans une note doit avoir été vérifié sur une vraie source.

## Important : conditions de LinkedIn et votre compte

**À lire avant d'utiliser l'envoi automatique.**

Les conditions d'utilisation de LinkedIn interdisent l'usage de bots ou d'autres méthodes automatisées non autorisées pour ajouter des contacts ou envoyer des messages. Un agent IA qui clique sur « Se connecter » et « Envoyer » dans votre navigateur entre dans ce cadre. LinkedIn peut restreindre ou fermer les comptes concernés et ne publie pas ses seuils de détection.

Ce skill réduit le risque (faible volume, validation humaine, notes personnelles, arrêt au moindre avertissement) mais **ne peut pas le supprimer**. Vous utilisez l'envoi automatique à vos risques, sur votre propre compte. Pour un risque nul côté automatisation, arrêtez-vous à l'étape de validation et envoyez les invitations vous-même avec les notes préparées par Claude.

## Données personnelles

Prospecter des professionnels dans l'UE (RGPD) ou ailleurs implique de traiter des données personnelles. Limitez-vous aux informations professionnelles, ayez un intérêt légitime que vous savez expliquer, respectez les demandes d'opposition (passez le prospect en « Sans suite » et ne le recontactez jamais) et ne collectez pas de coordonnées privées. Ceci est une information générale, pas un conseil juridique.

## Licence

MIT. Voir [LICENSE](LICENSE).

Projet indépendant, sans lien avec Anthropic ni LinkedIn, ni approuvé ou sponsorisé par eux. « Claude » est une marque d'Anthropic ; « LinkedIn » est une marque de LinkedIn Corporation.
