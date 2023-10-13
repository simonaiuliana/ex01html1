# Création d'un dépôt GIT

## Création d'un dépôt GIT en local

Dans la console, initialisation du dépôt:

```bash
git init
```

Ceci crée un dossier caché nommé `.git` qui contient tout l'historique du projet

## Visualisation de l'état de GIT

```bash
git status
```

### Pour voir les fichiers et dossiers Unix

le -a permet d'afficher les fichiers cachés

```bash
ls -a
```

## Pour ajouter un fichier à la future sauvegarde

```bash
git add README.md
```

## Pour effectuer la sauvegarde

Les fichiers en attente de sauvegarde sont en vert, **new file** ou **modified**

Les fichiers non suivi sont en rouge.

Seul les fichiers en **staging** seront sauvegardés

```bash
git commit -m"Message du commit"
```

Un commit est une sauvegarde, on peut y accèder 
avec un `git log` (affichage des identifiants des sauvegardes)
et `git show` (sans paramètre, affichage du dernier commit)

## Pour ajouter tous les fichiers en staging

```bash
git add .
```

## Pour retirer un fichier du staging

```bash
git restore --staged README.md
```

Le fichier est sorti du `staging` et sera affiché en rouge avec `git status`

## Ajout d'un serveur 

Nous allons utiliser un dépôt que l'on va créer sur github.com,
après connexion. Comme c'est un travail personnel, son URL sera
 de ce type : https://github.com/VOTRE_USERNAME/leNomDuProjet

Nous créons un new Repository, puis nous copions la clefs SSH :

git@github.com:WebDevCF2m/exe01html.git


Nous retounons dans notre console :

```bash
git remote add origin git@github.com:WebDevCF2m/exe01html.git
```

Pour voir si ça a fonctionné :

```bash
git remote -v
```

## Envois du projet

```bash
git push origin main
```

## Récupération du projet

Si on souhaite récupérer que le `.git` (donc l'historique sans les fichiers)

```bash
git fetch origin main
```

Si on souhaite récupérer toute la branche `main`

```bash
git pull origin main
```

Si on a effectué des modifications en local non voulues ne permettant pas 
la récupération des fichiers (`merge error`).

On peut utiliser un `git stash` pour faire une pseudo sauvegarde et revenir au dernier commit
avant de refaire un `git pull`