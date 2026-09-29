# 🐙 Rappel des commandes Git essentielles

> Une fiche de référence rapide pour retrouver les principales commandes Git et leur utilisation.

---

## 📥 `git clone` — Récupérer un dépôt

Permet de **copier un dépôt distant sur ton ordinateur**.

### Syntaxe

```bash
git clone <URL>
```

### Exemple

```bash
git clone https://github.com/utilisateur/projet.git
```

---

## 🔎 `git status` — Voir l'état du projet

Affiche les fichiers **modifiés, ajoutés, supprimés** et ceux qui sont prêts à être commit.

```bash
git status
```

> 💡 Très utile pour savoir **où tu en es avant un commit**.

---

## ➕ `git add` — Préparer les modifications

Ajoute des modifications à la **zone de staging**, afin de les inclure dans le prochain commit.

### Ajouter un fichier précis

```bash
git add fichier.py
```

### Ajouter tous les changements

```bash
git add .
```

---

## 💾 `git commit` — Enregistrer les modifications

Crée un **point de sauvegarde** dans l'historique Git avec les fichiers précédemment ajoutés avec `git add`.

```bash
git commit -m "Description des modifications"
```

### Exemple

```bash
git commit -m "Ajout de la page de connexion"
```

### 🔄 Cycle classique

```bash
git add .
git commit -m "Mon message"
```

---

## 🕐 `git log` — Consulter l'historique

Affiche l'historique des commits.

```bash
git log
```

### Version plus compacte

```bash
git log --oneline
```

### Exemple

```text
a43cf81 Ajout page connexion
81fe321 Correction du menu
51cd182 Initial commit
```

---

## 🔀 `git diff` — Voir les modifications

Affiche précisément **ce qui a été modifié dans les fichiers** depuis le dernier commit.

```bash
git diff
```

### Voir les modifications déjà ajoutées avec `git add`

```bash
git diff --staged
```

---

## 🌿 `git branch` — Gérer les branches

### Voir les branches

```bash
git branch
```

> La branche actuelle est indiquée par `*`.

### Créer une branche

```bash
git branch <nom>
```

**Exemple :**

```bash
git branch nouvelle-feature
```

### Supprimer une branche locale

```bash
git branch -d <nom>
```

---

## 🔄 `git switch` — Changer de branche

### Se déplacer vers une autre branche

```bash
git switch <nom>
```

**Exemple :**

```bash
git switch develop
```

### Créer et directement rejoindre une nouvelle branche

```bash
git switch -c <nom>
```

**Exemple :**

```bash
git switch -c nouvelle-feature
```

---

## ⬇️ `git pull` — Récupérer les changements

Récupère les nouvelles modifications du dépôt distant et les **intègre dans ta branche locale**.

```bash
git pull
```

> 💡 Typiquement, tu l'utilises avant de commencer à travailler pour récupérer les dernières modifications de tes collègues.

---

## ⬆️ `git push` — Envoyer ses commits

Envoie tes commits locaux vers le **dépôt distant**.

```bash
git push
```

### Publier une nouvelle branche pour la première fois

```bash
git push -u origin <nom-branche>
```

**Exemple :**

```bash
git push -u origin nouvelle-feature
```

---

# 🚀 Workflow classique

Dans la pratique, tu utiliseras très souvent les commandes dans cet ordre :

```bash
# 1. Récupérer les dernières modifications
git pull

# 2. Voir l'état du projet
git status

# ... modifier ton code ...

# 3. Voir ce qui a changé
git diff

# 4. Préparer les modifications
git add .

# 5. Créer le commit
git commit -m "Ajout de ma fonctionnalité"

# 6. Envoyer les modifications
git push
```

---

# 🌿 Workflow avec une branche

Si tu travailles avec des **branches** :

```bash
# Créer et rejoindre la branche
git switch -c ma-feature

# ... travail ...

# Préparer les modifications
git add .

# Créer le commit
git commit -m "Ajout de ma feature"

# Publier la branche
git push -u origin ma-feature
```

---

# 📌 Récapitulatif rapide

| Commande | Utilité |
|---|---|
| `git clone` | 📥 Copier un dépôt distant |
| `git status` | 🔎 Voir l'état du projet |
| `git add` | ➕ Préparer les modifications |
| `git commit` | 💾 Enregistrer les modifications |
| `git log` | 🕐 Consulter l'historique |
| `git diff` | 🔀 Voir les modifications |
| `git branch` | 🌿 Gérer les branches |
| `git switch` | 🔄 Changer de branche |
| `git pull` | ⬇️ Récupérer les changements distants |
| `git push` | ⬆️ Envoyer ses commits |
