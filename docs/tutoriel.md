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

