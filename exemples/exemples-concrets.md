# Exemples concrets et mises en situation

Ce document complète nos bonnes pratiques en proposant des scénarios de la vie réelle de l'équipe NovaWeb.

## Situation 1 : Vous devez corriger un bug en urgence

Vous êtes en plein développement d'une nouvelle page sur votre branche `feat/nouvelle-page`, mais un bug urgent a été détecté en production sur la branche `main`. Vous devez intervenir tout de suite sans perdre votre travail en cours.

**Les commandes :**
```bash
# 1. Sauvegarder temporairement votre travail en cours
git stash

# 2. Revenir sur la branche principale
git switch main

# 3. Récupérer la dernière version du code
git pull origin main

# 4. Créer une nouvelle branche pour le correctif
git switch -c fix/bug-urgent

# ... vous corrigez le bug ...

# 5. Commiter et envoyer le correctif
git add .
git commit -m "fix: corrige le bug urgent en production"
git push origin fix/bug-urgent

# 6. Revenir sur votre branche de fonctionnalité et récupérer votre travail
git switch feat/nouvelle-page
git stash pop
```

## Situation 2 : Vous avez commité trop tôt (ou fait une erreur de message)

Vous venez de faire un `git commit`, mais vous avez oublié d'ajouter un fichier, ou votre message de commit comportait une faute de frappe, et vous n'avez pas encore fait de `git push`.

**Les commandes :**
```bash
# 1. Ajouter le fichier manquant (si besoin)
git add le-fichier-oublie.md

# 2. Modifier le dernier commit sans en créer un nouveau
git commit --amend -m "docs: ajoute les bonnes pratiques (correction)"
```

## Situation 3 : Vous voulez annuler des modifications locales non commitées

Vous avez modifié un fichier pour faire des tests locaux, mais vous voulez retrouver la version propre du fichier (version du dernier commit) sans garder vos modifications.

**Les commandes :**
```bash
# Pour annuler les modifications sur un fichier spécifique
git restore nom-du-fichier.md

# Pour annuler TOUTES les modifications non commitées de votre projet (Attention !)
git restore .
```
