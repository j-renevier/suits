# Git 

## Référence

- [Git](https://git-scm.com/)

## Installation

### Debian / Ubuntu 

```bash
sudo apt install git
```
### Autres  

Voir la documentation 

## Configuration 

```bash
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```

### Ajouter un template de commit

Template par defaut des commit: .gitmessage.txt

```bash
Subject line (try to keep under 50 characters)

Multi-line description of commit,
feel free to be detailed.

[Ticket: X]
# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
# On branch master
# Changes to be committed:
#   (use "git reset HEAD <file>..." to unstage)
#
# modified:   lib/test.rb
#
~
~
".git/COMMIT_EDITMSG" 14L, 297C
```

```bash
# Config message in this repo
git config commit.template <path to file>/.gitmessage.txt

# Config message in all git projects
git config --global commit.template <path to file>/.gitmessage.txt  
```

Si il y a le caractère ^M dans le message utiliser la commande suivante :

```bash
sed -i 's/\r//' .gitmessage.txt
```

## Initialiser un dêpot local

```bash
git init
```

## Dupliquer un dêpot distant

```bash
git clone <link to repo>
```

## Tag 

Correspond à la verion du code, il correspond à l'etat du code lors de la mises en production de la version correspondante au tag 

### Lister les tags

```bash
git tag
```

### Créer un tag

```bash
git tag <tagname>
```

**tagname** version dans lequel le code va être publier (ex: version = 0.0.1 -> tag = 0.0.1) 


### Publier un tag vers un dépôt distant

```bash
git push origin <tagname>
```

### Supprimer un tag

```bash
git tag -d <tagname>
```


## Branche 

### Nomenclature des branches

```bash
<name>/<Ref> - <short description>
```

**name** type de branche correspondant a git flow
- **master**
- **develop**
- **release** 
- **hotfix** 
- **feature** 
- ... 

**Ref** numéro de ticket definissant à la fonctionnalité correspondante

```<code pojet = ST ><id ticket> (ex: ST0000)```

**short description** déscription rapide de la fonctionnalité


### Visualiser les branches 

```bash
git branch
```

### Supprimer une branche

```bash
git branch -d <branch name>
```

## Commits 

### Nomenclature des commits 

```bash
<type>(<portée>): <sujet>

<description>

<footer>
```

- **Type** définit le type de commit
  - **build**: Système de build (example : gulp, webpack, npm)
  - **ci**: Intégration continue (example scopes: Travis, Circle, BrowserStack, SauceLabs)
  - **docs**: Documentation
  - **feat**: Ajout d'une fonctionnalité
  - **fix**: Correction de bogue
  - **perf**: Amélioration des performances
  - **refactor**: Changement du code qui ne change rien au fonctionnement
  - **style**: Changement du style du code (sans changer la logique)
  - **test**: Modification des tests

- **Portée** définit quelle partie de votre librairie / application est affectée par le commit (cette information est optionnelle)

- **Sujet** contient une description succinte des changements
En utilisant l'impératif présent ("change", et non pas "changed" ou "changes")
Sans majuscule au début
Pas de "." à la fin de la description

- **Description** permet de détailler plus en profondeur les motivations derrière le changement. Les règles sont les mêmes que pour la partie Sujet.

- **Footer** contient les changements importants (Breaking Changes) et les références à des issues GitHub / GitLab ou autre.

Exemple: 

```bash 
fix(api): prevent racing of requests

Introduce a request id and a reference to latest request. Dismiss
incoming responses other than from latest request.

Remove timeouts which were used to mitigate the racing issue but are
obsolete now.
```

## Cherry Pick

git-cherry-pick - Applique les modifications introduites par certains commits existants

```bash
git cherry-pick [--edit] [-n] [-m <numéro-de-parent>] [-s] [-x] [--ff] [-S[<id-clé>]] <commit>…​

git cherry-pick (--continue | --skip | --abort | --quit)
```

### Exemple

Passer le dernier commit de <start-branch> à <end-branch>

```bash
git checkout <end-branch>

git cherry-pick <start-branch>
```

## Clean dêpot local

⚠️ Les modifications faites en locales sont a jour sur le dêpot distant, si tu veux pas push ta branche n'utlise pas cette commande sinon bye bye. 

Récupérez toutes les branches et les informations de suivi du dépôt distant

```bash
git fetch --prune
```

Supprimez les branches locales qui ne sont pas présentes sur le dépôt distant

```bash
git branch -vv | grep ': gone]' | awk '{print $1}' | xargs -r git branch -d
```

## Stash

Git stash stocke (ou stashe) temporairement les changements apportés à votre copie de travail pour que vous puissiez effectuer d'autres tâches, puis revenir et les réappliquer par la suite.


### Faire un stash de votre travail

```bash
git stash
```
Ajouter un message au stash

```bash
git stash save "message"
```

### Appliquer les changements stashés

```bash
git stash pop
```

### Afficher tous les stashes enregistrés

```bash
git stash list
```

### Nettoyez votre stash

```bash
git stash drop
```

Supprimer tous les stashes 

```bash
git stash clear
```