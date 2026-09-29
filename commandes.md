Voici une fiche de rappel simple des commandes Git essentielles, avec leur rôle et les variantes les plus utiles.
git clone — Récupérer un dépôt
Permet de copier un dépôt distant sur ton ordinateur.
git clone <URL>

Exemple :
git clone https://github.com/utilisateur/projet.git

git status — Voir l'état du projet
Affiche les fichiers modifiés, ajoutés, supprimés et ceux qui sont prêts à être commit.
git status

Très utile pour savoir où tu en es avant un commit.
git add — Préparer les modifications
Ajoute des modifications à la zone de staging, afin de les inclure dans le prochain commit.
Un fichier précis :
git add fichier.py

Tous les changements :
git add .

git commit — Enregistrer les modifications
Crée un point de sauvegarde dans l'historique Git avec les fichiers précédemment ajoutés avec git add.
git commit -m "Description des modifications"

Exemple :
git commit -m "Ajout de la page de connexion"

Le cycle classique est donc :
git add .
git commit -m "Mon message"

git log — Consulter l'historique
Affiche l'historique des commits.
git log

Version plus compacte :
git log --oneline

Exemple :
a43cf81 Ajout page connexion
81fe321 Correction du menu
51cd182 Initial commit

git diff — Voir les modifications
Affiche précisément ce qui a été modifié dans les fichiers depuis le dernier commit.
git diff

Pour voir les modifications déjà ajoutées avec git add :
git diff --staged

git branch — Gérer les branches
Voir les branches :
git branch

La branche actuelle est indiquée par *.
Créer une branche :
git branch <nom>

Exemple :
git branch nouvelle-feature

Supprimer une branche locale :
git branch -d <nom>

git switch — Changer de branche
Se déplacer vers une autre branche :
git switch <nom>

Exemple :
git switch develop

Créer et directement rejoindre une nouvelle branche :
git switch -c <nom>

Exemple :
git switch -c nouvelle-feature

git pull — Récupérer les changements
Récupère les nouvelles modifications du dépôt distant et les intègre dans ta branche locale.
git pull

Typiquement, tu l'utilises avant de commencer à travailler pour récupérer les dernières modifications de tes collègues.
git push — Envoyer ses commits
Envoie tes commits locaux vers le dépôt distant.
git push

Pour publier une nouvelle branche pour la première fois :
git push -u origin <nom-branche>

Exemple :
git push -u origin nouvelle-feature

🔄 Workflow classique
Dans la pratique, tu utiliseras très souvent les commandes dans cet ordre :
# Récupérer les dernières modifications
git pull

# Voir l'état du projet
git status

# ... modifier ton code ...

# Voir ce qui a changé
git diff

# Préparer les modifications
git add .

# Créer le commit
git commit -m "Ajout de ma fonctionnalité"

# Envoyer les modifications
git push

Et si tu travailles avec des branches :
git switch -c ma-feature

# ... travail ...

git add .
git commit -m "Ajout de ma feature"
git push -u origin ma-feature