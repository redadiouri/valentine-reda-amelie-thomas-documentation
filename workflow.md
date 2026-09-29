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