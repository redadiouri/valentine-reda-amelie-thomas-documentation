# Bonnes pratiques et conflits

## Table des matières

- [Règles de collaboration de NovaWeb](#règles-de-collaboration-de-novaweb)
- [Procédure détaillée de résolution d’un conflit](#procédure-détaillée-de-résolution-dun-conflit)
- [Commandes utiles au quotidien](#commandes-utiles-au-quotidien)

## Règles de collaboration de NovaWeb

Afin d'assurer une collaboration efficace et fluide au sein de l'équipe, voici les bonnes pratiques à respecter rigoureusement :

### 1. Mettre à jour `main` avant de créer une branche
Assurez-vous d'avoir la dernière version du code avant de commencer votre travail pour éviter de développer sur une base obsolète.
```bash
git switch main
git pull origin main
```

### 2. Utiliser des noms de branches compréhensibles
Privilégiez des noms clairs décrivant la tâche, en utilisant des préfixes standards :
- `feat/` pour une nouvelle fonctionnalité (ex: `feat/page-accueil`)
- `fix/` pour une correction de bug (ex: `fix/bouton-casse`)
- `docs/` pour de la documentation (ex: `docs/bonnes-pratiques`)
- `refactor/` pour de la réécriture de code sans ajout de fonctionnalité

### 3. Faire des commits courts et cohérents
Un commit doit représenter un changement logique et unique. Ne regroupez pas la correction d'un bug et l'ajout d'une nouvelle fonctionnalité dans le même commit. Cela facilite l'historique et le retour en arrière en cas de problème.

### 4. Écrire des messages de commit précis
Soyez descriptifs et utilisez l'impératif ou l'infinitif.
- *Mauvais exemple :* `Modification du fichier` ou `fix`
- *Bon exemple :* `Ajoute les règles de nommage des branches dans la documentation` ou `Corrige le lien cassé vers la page de contact`

### 5. Vérifier les fichiers avant de les ajouter
Ne faites jamais un `git add .` aveuglément. Prenez toujours le temps de vérifier ce que vous vous apprêtez à valider.
```bash
git status          # Voir la liste des fichiers modifiés
git diff            # Voir exactement quelles lignes ont été ajoutées/supprimées
git diff --cached   # Voir les modifications déjà ajoutées à la zone de préparation (staged)
```

### 6. Ne jamais ajouter de mots de passe ou de clés privées
Les informations sensibles (clés d'API, mots de passe de base de données) ne doivent jamais être envoyées sur le dépôt. Utilisez des fichiers d'environnement (`.env`) qui ne sont pas versionnés.

### 7. Utiliser un fichier `.gitignore`
Créez toujours un fichier `.gitignore` à la racine pour exclure :
- Les fichiers générés par le système (ex: `.DS_Store`)
- Les dossiers de dépendances (ex: `node_modules/`, `venv/`)
- Les fichiers de configuration personnels de votre éditeur (ex: `.vscode/`, `.idea/`)

### 8. Relire les pull requests avant leur fusion
Prenez le temps de revoir le travail de vos collègues pour garantir la qualité de notre code et de notre documentation. Posez des questions et proposez des améliorations de manière constructive.

### 9. Communiquer pour éviter les modifications contradictoires
Échangez avec l'équipe (sur Slack/Discord ou lors de réunions) pour ne pas modifier les mêmes fichiers en même temps. La communication est la meilleure prévention contre les conflits.

## Procédure détaillée de résolution d’un conflit

Un conflit survient lorsque Git ne peut pas fusionner deux branches automatiquement (souvent parce que les mêmes lignes d'un fichier ont été modifiées différemment). Voici les étapes pas à pas pour les résoudre sereinement :

1. **Identifier les fichiers en conflit :** 
   Utilisez `git status` pour voir les fichiers marqués en "Unmerged paths" ou "Fichiers non fusionnés". Git les signalera en rouge.
   ```bash
   git status
   ```

2. **Comprendre les deux versions avec le collègue concerné :** 
   Ne supprimez pas le travail de votre collègue sans comprendre. Discutez avec la personne responsable de l'autre modification pour décider de la meilleure version à garder ou comment combiner les deux idées.

3. **Modifier le fichier et supprimer les marqueurs de conflit :** 
   Ouvrez le fichier en conflit avec votre éditeur de texte ou votre IDE. Git a ajouté des balises visuelles pour délimiter les deux versions :
   ```text
   <<<<<<< HEAD
   Ceci est votre modification (version actuelle sur votre branche).
   =======
   Ceci est la modification venant de l'autre branche que vous essayez de fusionner.
   >>>>>>> nom-de-la-branche-entrante
   ```
   Vous devez :
   - Choisir la version à conserver (ou créer un mix des deux).
   - Supprimer **absolument** les lignes de balises (`<<<<<<<`, `=======`, `>>>>>>>`).

4. **Vérifier le résultat :** 
   Relisez votre fichier pour vous assurer que le code ou le texte a bien le sens voulu après vos modifications. Si c'est du code, essayez de le lancer pour vérifier qu'il n'y a pas d'erreur de syntaxe.

5. **Ajouter le fichier corrigé et terminer la fusion :** 
   Une fois tous les conflits résolus dans le fichier, dites à Git que c'est bon en l'ajoutant à la zone de préparation.
   ```bash
   git add <nom-du-fichier>
   ```
   Répétez l'opération pour chaque fichier en conflit. Une fois `git status` tout au vert, terminez la fusion :
   ```bash
   git commit
   ```
   *Note :* Git proposera souvent un message de commit automatique pour la fusion, que vous pouvez simplement valider.

## Commandes utiles au quotidien

Voici quelques commandes supplémentaires pour vous aider à respecter ces bonnes pratiques :

- `git log --oneline --graph` : Affiche l'historique des commits de manière compacte et visuelle pour bien comprendre la structure des branches.
- `git restore <fichier>` : Annule les modifications non commitées d'un fichier (pratique si vous vous êtes trompé).
- `git stash` : Met vos modifications actuelles de côté temporairement (utile si vous devez changer de branche d'urgence pour corriger un bug sur `main`). Vous pourrez les récupérer plus tard avec `git stash pop`.

Pour voir comment utiliser ces commandes dans des situations réelles au sein de NovaWeb, consultez notre document : **[Exemples concrets](exemples/exemples-concrets.md)**.

---
*Ce document a été généré par une intelligence artificielle pour faciliter l'apprentissage de l'équipe.*
