### Documentation faite par IA ###

# Tutoriel pratique : rejoindre NovaWeb

Ce tutoriel présente le parcours habituel pour contribuer à la documentation de NovaWeb avec Git et GitHub. Remplacez les exemples entre chevrons par vos propres informations. L’URL du dépôt est à demander à un collègue ou à récupérer dans le bouton **Code** de la page GitHub de l’entreprise.

## 1. Vérifier que Git est installé

Ouvrez un terminal (PowerShell sous Windows, Terminal sous macOS ou Linux), puis lancez :

```bash
git --version
```

Si Git est installé, le terminal affiche sa version, par exemple `git version 2.x.x`. Si la commande n’est pas reconnue, installez Git depuis [git-scm.com](https://git-scm.com/downloads), puis ouvrez un nouveau terminal et relancez la commande.

## 2. Configurer son nom et son adresse e-mail

Indiquez le nom et l’adresse que Git inscrira dans vos commits :

```bash
git config --global user.name "Prénom Nom"
git config --global user.email "prenom.nom@example.com"
```

Remplacez ces valeurs par votre nom et l’adresse associée à votre compte GitHub (ou l’adresse recommandée par l’entreprise). L’option `--global` applique ces réglages à tous les dépôts de votre ordinateur. Vérifiez-les avec :

```bash
git config --global user.name
git config --global user.email
```

Chaque commande doit afficher la valeur configurée.

## 3. Cloner le dépôt de l’entreprise

Sur GitHub, ouvrez le dépôt NovaWeb, cliquez sur **Code**, puis copiez son URL HTTPS ou SSH. Dans le terminal, placez-vous dans le dossier où vous souhaitez enregistrer le projet et exécutez :

```bash
git clone <URL_DU_DEPOT>
cd <NOM_DU_DEPOT>
```

Par exemple, la première commande télécharge une copie du dépôt dans un nouveau dossier. La seconde entre dans ce dossier afin que les prochaines commandes Git s’appliquent au bon projet. Si vous utilisez SSH, votre clé SSH doit être configurée avec GitHub ; avec HTTPS, GitHub peut vous demander de vous authentifier.

## 4. Créer une branche de travail

Vérifiez que vous partez de la branche principale à jour, puis créez une branche dédiée à votre tâche :

```bash
git switch main
git pull origin main
git switch -c docs/guide-nouveau
```

`git pull` récupère les derniers changements de `main`. `git switch -c` crée la branche `docs/guide-nouveau` et s’y place. Une branche séparée permet de préparer votre contribution sans modifier directement `main`.

## 5. Créer ou modifier un fichier Markdown

Dans VS Code, créez `docs/guide-nouveau.md` (ou ouvrez un fichier Markdown existant), rédigez vos changements, puis enregistrez le fichier. Markdown est un format texte : les titres s’écrivent avec `#`, les listes avec `-` et les liens avec `[texte](URL)`.

Exemple de contenu :

```markdown
# Guide du nouveau membre

Bienvenue chez NovaWeb !

## Premiers pas

- Installer les outils nécessaires.
- Lire le workflow de l’équipe.
```

Adaptez le nom du fichier et son contenu à la tâche confiée.

## 6. Vérifier les changements

Dans le terminal, contrôlez l’état du dépôt et le contenu des modifications :

```bash
git status
git diff --check
git diff
```

`git status` indique les fichiers modifiés ou nouveaux. `git diff --check` repère notamment les espaces superflus en fin de ligne. `git diff` affiche les modifications des fichiers déjà suivis ; un nouveau fichier n’apparaît pas encore dans ce diff. Relisez le fichier dans VS Code et vérifiez que seuls les changements attendus sont présents.

## 7. Ajouter le fichier et créer un commit

Ajoutez le fichier voulu à la zone de préparation, vérifiez ce qui sera enregistré, puis créez un commit :

```bash
git add docs/guide-nouveau.md
git diff --cached
git commit -m "docs: ajouter le guide du nouveau membre"
```

Adaptez le chemin si vous avez modifié un autre fichier. `git add` prépare le fichier pour le prochain commit ; `git diff --cached` permet de relire exactement ce qui sera enregistré. Le commit sauvegarde ce lot de changements dans l’historique local. Son message doit décrire clairement la modification.

## 8. Envoyer la branche sur GitHub

Publiez votre branche et configurez son suivi distant :

```bash
git push -u origin docs/guide-nouveau
```

`origin` désigne le dépôt GitHub et `-u` associe la branche locale à sa branche distante. Les prochains envois pourront généralement se faire avec `git push`. Si l’authentification est demandée, suivez la procédure GitHub configurée pour votre compte.

## 9. Ouvrir une pull request et demander une relecture

Sur GitHub :

1. Ouvrez le dépôt. GitHub peut proposer **Compare & pull request** pour la branche que vous venez d’envoyer ; sinon, ouvrez **Pull requests**, puis **New pull request**.
2. Choisissez `main` comme branche de base (**base**) et `docs/guide-nouveau` comme branche à intégrer (**compare**).
3. Vérifiez le diff, donnez un titre et décrivez brièvement le changement ainsi que les vérifications effectuées.
4. Dans **Reviewers**, demandez la relecture au collègue responsable de votre tâche. Pour le tutoriel de prise en main, le README du projet désigne Réda.
5. Cliquez sur **Create pull request**.

> Une pull request (PR) permet à l’équipe de relire et de discuter les changements avant leur intégration. Répondez aux remarques en modifiant votre branche, puis envoyez les nouveaux commits avec `git push`. Attendez la validation et la fusion dans `main` selon les règles de l’équipe ; ne fusionnez pas vous-même si vous n’y êtes pas autorisé.

## 10. Après la fusion, mettre à jour `main`

Une fois la pull request fusionnée, revenez sur `main` et récupérez la version à jour :

```bash
git switch main
git pull origin main
```

`git switch main` vous replace sur la branche principale et `git pull` récupère la fusion depuis GitHub. Vous pouvez ensuite supprimer votre branche locale terminée :

```bash
git branch -d docs/guide-nouveau
```

Sur GitHub, vous pouvez également supprimer la branche distante avec **Delete branch** depuis la pull request fusionnée, si elle n’a pas déjà été supprimée automatiquement. Vérifiez d’abord que vous n’avez plus de travail non enregistré sur cette branche.
