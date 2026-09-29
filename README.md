# Documentation Git — NovaWeb

## Objectif du projet

NovaWeb est une entreprise fictive de développement web composée de quatre personnes : Valentine, Réda, Amélie et Thomas.

Notre objectif est de créer une documentation interne pour expliquer comment utiliser Git et travailler en équipe. Elle doit permettre à un nouveau collègue de comprendre nos commandes, notre organisation et nos bonnes pratiques.

## Répartition des tâches

### Valentine — Commandes essentielles

**Fichier à créer :** `commandes.md`

Rédiger un rappel des commandes Git suivantes :

- `git clone`
- `git status`
- `git add`
- `git commit`
- `git log`
- `git diff`
- `git branch`
- `git switch`
- `git pull`
- `git push`

Pour chaque commande :
- Expliquer son utilité.
- Donner sa syntaxe et un exemple.
- Préciser à quel moment l’utiliser.

**Branche :** `docs/commandes`  
**Relecture par :** Thomas

### Réda — Workflow de collaboration

**Fichier à créer :** `workflow.md`

Présenter le workflow GitHub Flow choisi pour notre entreprise.

Expliquer :
- Le rôle de la branche `main`.
- La création d’une branche pour chaque tâche.
- Les règles de nommage des branches.
- L’enregistrement du travail avec des commits.
- L’envoi d’une branche sur GitHub.
- La création d’une pull request.
- La relecture par un autre membre.
- La fusion dans `main` et la suppression de la branche terminée.

Ajouter un exemple concret : un membre modifie la documentation et fait valider son travail par un collègue.

**Branche :** `docs/workflow`  
**Relecture par :** Valentine

### Amélie — Tutoriel pratique

**Fichier à créer :** `tutoriel.md`

Créer un tutoriel destiné à une personne qui rejoint NovaWeb.

Présenter les étapes dans l’ordre :
1. Vérifier que Git est installé.
2. Configurer son nom et son adresse e-mail.
3. Cloner le dépôt de l’entreprise.
4. Créer une branche de travail.
5. Créer ou modifier un fichier Markdown.
6. Vérifier les changements.
7. Ajouter le fichier et créer un commit.
8. Envoyer la branche sur GitHub.
9. Ouvrir une pull request et demander une relecture.
10. Après la fusion, revenir sur `main` et récupérer les changements.

Donner les commandes nécessaires, expliquer leur résultat et décrire les actions à effectuer sur GitHub.

**Branche :** `docs/tutoriel`  
**Relecture par :** Réda

### Thomas — Bonnes pratiques et conflits

**Fichier à créer :** `bonnes-pratiques.md`

Présenter les règles de collaboration de NovaWeb :
- Mettre à jour `main` avant de créer une branche.
- Utiliser des noms de branches compréhensibles.
- Faire des commits courts et cohérents.
- Écrire des messages de commit précis, avec des exemples.
- Vérifier les fichiers avant de les ajouter.
- Ne jamais ajouter de mots de passe ou de clés privées.
- Utiliser un fichier `.gitignore`.
- Relire les pull requests avant leur fusion.
- Communiquer pour éviter les modifications contradictoires.

Ajouter une courte procédure de résolution d’un conflit :
1. Identifier les fichiers en conflit.
2. Comprendre les deux versions avec le collègue concerné.
3. Modifier le fichier et supprimer les marqueurs de conflit.
4. Vérifier le résultat.
5. Ajouter le fichier corrigé et terminer la fusion.

**Branche :** `docs/bonnes-pratiques`  
**Relecture par :** Amélie

## Consignes communes

- Rédiger en français avec des explications accessibles aux débutants.
- Utiliser des titres, des listes et des blocs de code Markdown.
- Adapter les exemples à notre entreprise fictive.
- Vérifier les commandes proposées.
- Travailler sur sa propre branche.
- Ouvrir une pull request vers `main` lorsque le document est prêt.
- Attendre la relecture d’un collègue avant de fusionner.
- Corriger les remarques reçues.
- Compléter ensemble ce README et vérifier les liens avant la livraison.

## Documentation

- [Commandes essentielles](commandes.md)
- [Workflow de collaboration](workflow.md)
- [Tutoriel pratique](tutoriel.md)
- [Bonnes pratiques et conflits](bonnes-pratiques.md)


## Création du site de documentation Git

### Objectif

Créer une page HTML claire et soignée pour présenter la documentation
Git de NovaWeb. Le site doit être agréable à lire sur ordinateur et mobile.

### Valentine — Structure HTML et commandes

**Fichier :** `index.html`
**Branche :** `feat/structure-html`

- Créer la structure HTML avec la langue française et la configuration mobile.
- Ajouter l’en-tête, le titre du site et une présentation de NovaWeb.
- Créer le menu de navigation.
- Ajouter une section présentant les commandes Git essentielles.
- Préparer les emplacements des sections Workflow et Tutoriel.
- Ajouter le pied de page.
- Relier la page au fichier `style.css`.

Utiliser ces identifiants pour les sections :
`commandes`, `workflow`, `tutoriel`, `bonnes-pratiques`.

### Réda — Section Workflow

**Fichier :** `sections/workflow.html`
**Branche :** `feat/section-workflow`

- Créer un bloc `<section id="workflow">` destiné à la page principale.
- Présenter GitHub Flow sous forme d’étapes numérotées.
- Expliquer les branches, commits, push, pull requests, relectures et fusions.
- Ajouter des exemples de commandes avec `<pre><code>`.
- Illustrer le parcours d’une modification de Réda relue par Valentine.

Ce fichier contient uniquement la section, sans `<html>`, `<head>` ni `<body>`.

### Amélie — Tutoriel et bonnes pratiques

**Fichier :** `sections/tutoriel.html`
**Branche :** `feat/section-tutoriel`

- Créer un bloc `<section id="tutoriel">`.
- Présenter les étapes à suivre pour contribuer au projet.
- Ajouter les commandes utiles avec `<pre><code>`.
- Créer un second bloc `<section id="bonnes-pratiques">`.
- Résumer les règles importantes : commits précis, relecture et absence de secrets.
- Utiliser des listes et des paragraphes courts.

Ce fichier contient uniquement les deux sections, sans structure HTML complète.

### Thomas — Apparence et adaptation mobile

**Fichier :** `style.css`
**Branche :** `feat/style-css`

- Définir les couleurs, la typographie et les espacements.
- Styliser l’en-tête et le menu.
- Présenter les sections dans des cartes lisibles.
- Mettre en valeur les blocs de commandes.
- Ajouter des effets discrets au survol des liens.
- Prévoir un indicateur de focus visible pour la navigation au clavier.
- Adapter la mise en page aux petits écrans.
- Vérifier le contraste et éviter les débordements horizontaux.

### Conventions communes

- Utiliser `.container` pour limiter la largeur du contenu.
- Utiliser `.card` pour les cartes et `.steps` pour les étapes numérotées.
- Utiliser `<pre><code>` pour les commandes.
- Garder les mêmes noms de sections et de classes.
- Faire un commit après chaque ajout cohérent.
- Ouvrir une pull request et obtenir une relecture avant de fusionner.

### Assemblage et vérification

1. Valentine prépare et fait fusionner la structure HTML.
2. Chaque membre récupère cette version avant de poursuivre.
3. Réda, Amélie et Thomas proposent leurs fichiers par pull request.
4. Une fois les fichiers fusionnés, Valentine crée une branche
   `feat/integration-page` et copie les sections dans `index.html`.
5. L’équipe vérifie la navigation, les commandes et l’affichage mobile.

Attention : les fichiers du dossier `sections` ne s’affichent pas
automatiquement dans la page. Leur contenu doit être intégré à `index.html`.