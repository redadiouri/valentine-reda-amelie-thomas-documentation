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