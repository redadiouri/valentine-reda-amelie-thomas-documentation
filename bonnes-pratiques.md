# Bonnes pratiques et conflits

## Table des matières

- [Règles de collaboration](#règles-de-collaboration-de-novaweb)
- [Procédure de résolution d’un conflit](#procédure-de-résolution-dun-conflit)


## Règles de collaboration de NovaWeb

Afin d'assurer une collaboration efficace et fluide au sein de l'équipe, voici les bonnes pratiques à respecter :

- **Mettre à jour `main` avant de créer une branche :** Assurez-vous d'avoir la dernière version du code avant de commencer votre travail en faisant un `git pull` sur `main`.
- **Utiliser des noms de branches compréhensibles :** Privilégiez des noms clairs décrivant la tâche (ex: `docs/bonnes-pratiques`, `fix/correction-lien`).
- **Faire des commits courts et cohérents :** Un commit doit représenter un changement logique et unique.
- **Écrire des messages de commit précis :** Soyez descriptifs.
  - *Mauvais exemple :* `Modification du fichier`
  - *Bon exemple :* `Ajout des règles de nommage des branches dans la documentation`
- **Vérifier les fichiers avant de les ajouter :** Utilisez `git status` et `git diff` pour contrôler ce que vous vous apprêtez à commiter.
- **Ne jamais ajouter de mots de passe ou de clés privées :** Les informations sensibles ne doivent jamais être envoyées sur le dépôt.
- **Utiliser un fichier `.gitignore` :** Pour exclure les fichiers générés, personnels ou inutiles au projet.
- **Relire les pull requests avant leur fusion :** Prenez le temps de revoir le travail de vos collègues pour garantir la qualité de notre documentation.
- **Communiquer pour éviter les modifications contradictoires :** Échangez avec l'équipe pour ne pas modifier les mêmes fichiers en même temps.

## Procédure de résolution d’un conflit

Si un conflit survient lors d'une fusion, voici les étapes à suivre :

1. **Identifier les fichiers en conflit :** Utilisez `git status` pour voir les fichiers que Git n'a pas pu fusionner automatiquement.
2. **Comprendre les deux versions avec le collègue concerné :** Discutez avec la personne responsable de l'autre modification pour décider de la meilleure version à garder (ou comment combiner les deux).
3. **Modifier le fichier et supprimer les marqueurs de conflit :** Éditez le fichier manuellement pour garder le code correct, et veillez à bien supprimer les balises de Git (`<<<<<<<`, `=======`, `>>>>>>>`).
4. **Vérifier le résultat :** Relisez votre fichier pour vous assurer que tout est correct.
5. **Ajouter le fichier corrigé et terminer la fusion :** Utilisez `git add <fichier>` pour valider votre résolution, puis créez le commit de fusion avec `git commit`.
