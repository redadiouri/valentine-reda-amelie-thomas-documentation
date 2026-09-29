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

## 5. Créer une pull request

Une pull request est une demande de fusion des changements d’une branche
vers une autre. Elle permet à l’équipe de discuter des modifications
et de les relire avant leur intégration.

Chez NovaWeb, chaque membre ouvre une pull request vers `main` :

1. Ouvrir le dépôt sur GitHub.
2. Aller dans « Pull requests », puis « New pull request ».
3. Choisir `main` comme branche de destination (« base »).
4. Choisir sa branche de travail comme source (« compare »).
5. Vérifier les modifications affichées.
6. Saisir un titre précis et une description des changements.
7. Cliquer sur « Create pull request ».
8. Demander une relecture au collègue prévu.

Par exemple, Réda propose la fusion de `docs/workflow` vers `main`
et demande une relecture à Valentine.

La création de la pull request ne fusionne pas les branches.
Les nouveaux commits envoyés sur la même branche sont automatiquement
ajoutés à la pull request.

## 6. Faire relire son travail

Chez NovaWeb, chaque pull request doit être relue par un autre membre
avant sa fusion dans `main`. Valentine relit le document de Réda.

La personne chargée de la relecture consulte l’onglet « Files changed »
de la pull request et vérifie :

- La clarté des explications.
- L’exactitude des commandes et des exemples.
- L’orthographe et la présentation Markdown.
- Le respect des consignes du projet.

Elle peut laisser des commentaires, demander des corrections
ou approuver les changements.

Si des corrections sont demandées, l’auteur modifie son fichier
sur la même branche, crée un nouveau commit et l’envoie avec `git push`.
La pull request se met automatiquement à jour.

Après vérification des corrections, le collègue approuve la pull request.
Cette approbation permet de passer à la fusion.

## 7. Fusionner la pull request

Après l’approbation du collègue et la résolution des éventuels conflits,
l’auteur peut fusionner sa pull request dans `main`.
Les changements rejoignent alors la documentation commune de NovaWeb.

### Supprimer la branche sur GitHub

Après la fusion, cliquer sur « Delete branch » dans la pull request
pour supprimer la branche distante devenue inutile.

Cette suppression conserve les modifications intégrées à `main`
et leur historique. Elle ne supprime pas la branche présente
sur notre ordinateur.

### Supprimer la branche locale terminée

Après la fusion et la mise à jour de `main`, nous pouvons supprimer
notre ancienne branche locale depuis `main` :

```bash
git branch -d docs/workflow
```

L’option `-d` vérifie que la branche a été fusionnée avant de la supprimer.

Pour nettoyer les références locales aux branches supprimées sur GitHub :

```bash
git fetch --prune
```

Chaque membre adapte le nom de branche à sa tâche.

## 8. Exemple concret chez NovaWeb

### Préparer la modification

Réda souhaite préciser les règles de nommage des branches dans
la documentation. Il crée une branche depuis `main` à jour :

```bash
git switch main
git pull origin main
git switch -c docs/preciser-nommage
```

Cette branche lui permet de préparer sa modification avant
de la proposer à Valentine pour relecture.

### Modifier le document

Sur sa branche `docs/preciser-nommage`, Réda ouvre `workflow.md`
et ajoute une règle dans la partie sur le nommage :

> Utiliser des tirets pour séparer les mots, par exemple :
> `docs/guide-installation`.

Il enregistre le fichier, puis vérifie sa modification :

```bash
git diff
```

Cette commande lui permet de relire les lignes ajoutées ou supprimées
avant de préparer son commit.

### Enregistrer la modification

Après avoir vérifié son ajout, Réda sélectionne le fichier modifié :

```bash
git add workflow.md
```

Il crée ensuite un commit avec un message précis :

```bash
git commit -m "docs: preciser les separateurs dans les noms de branches"
```

Ce commit conserve une trace de la modification sur sa branche locale.

### Publier la branche

Réda envoie sa branche et son commit sur GitHub :

```bash
git push -u origin docs/preciser-nommage
```

Valentine peut maintenant consulter cette branche sur le dépôt distant.
Les modifications ne sont pas encore intégrées à `main`.

### Demander une relecture à Valentine

Sur GitHub, Réda ouvre une pull request avec :

- Branche de destination : `main`.
- Branche source : `docs/preciser-nommage`.
- Titre : « Préciser les règles de nommage des branches ».
- Description : « Ajouter une règle sur les tirets avec un exemple de nom de branche ».

Il sélectionne Valentine dans la rubrique « Reviewers »
pour lui demander de vérifier cette modification avant la fusion.