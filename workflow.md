# Workflow de collaboration chez NovaWeb

Notre équipe utilise GitHub Flow pour travailler à plusieurs.
Chaque tâche est réalisée sur une branche dédiée, puis relue par
un collègue avant d’être intégrée à la branche principale.

## 1. Le rôle de la branche main

La branche `main` contient la version validée de notre documentation.
Elle sert de référence commune aux quatre membres de NovaWeb.

Dans notre équipe, chaque modification est préparée sur une branche
séparée. Elle est ensuite proposée dans une pull request et relue
par un collègue avant d’être fusionnée dans `main`.

## 2. Créer et nommer une branche

Chez NovaWeb, chaque tâche est réalisée sur une branche dédiée.
Cela permet aux membres de travailler en parallèle.

Avant de créer une nouvelle branche, nous partons de `main` à jour :

```bash
git switch main
git pull origin main
git switch -c docs/nom-de-la-tache
```

Nous utilisons des noms courts, en minuscules, sans espaces ni accents.
Le préfixe indique le type de tâche :

- `docs/` pour la documentation : `docs/workflow`.
- `feat/` pour une fonctionnalité : `feat/formulaire-contact`.
- `fix/` pour une correction : `fix/lien-contact`.

Pour ce projet, nos branches sont :

- Valentine : `docs/commandes`.
- Réda : `docs/workflow`.
- Amélie : `docs/tutoriel`.
- Thomas : `docs/bonnes-pratiques`.

## 3. Enregistrer son travail avec des commits

Un commit enregistre une version des changements sélectionnés.
Il permet de suivre l’évolution du projet et de comprendre les modifications.

Chez NovaWeb, nous faisons un commit après chaque ajout ou correction
cohérente, avec un message qui explique le changement.

Nous vérifions d’abord les fichiers modifiés et leur contenu :

```bash
git status
git diff
```

Nous sélectionnons ensuite le fichier à enregistrer :

```bash
git add workflow.md
```

Puis nous créons le commit :

```bash
git commit -m "docs: expliquer le role de la branche main"
```

Le message doit être précis : « docs: expliquer le role de la branche main »
est plus utile que « modification ».

Un commit reste sur notre ordinateur tant qu’il n’a pas été envoyé sur GitHub.

## 4. Envoyer sa branche sur GitHub

Une fois les commits créés, nous envoyons notre branche sur GitHub
pour partager notre travail avec l’équipe.

Lors du premier envoi de la branche :

```bash
git push -u origin docs/workflow
```

- `origin` désigne le dépôt distant sur GitHub.
- `docs/workflow` est la branche à envoyer.
- `-u` associe notre branche locale à la branche distante.

Pour les envois suivants depuis cette même branche, après de nouveaux commits :

```bash
git push
```

Chaque membre adapte le nom de branche à sa tâche.
L’envoi publie les commits sur GitHub, mais ne les fusionne pas dans `main`.