# STANDART

## Tu as besoin d'aide pour résoudre ton problème




## Versionning

Demander l'autorisation pour merge sur une branche protegé
- Dans gitlab : Merge Request (MR) 
- Dans github : Pull Requests (PR) 

### Workflow Git

Un workflow Git est une recette ou une recommandation expliquant comment utiliser Git pour accomplir une tâche de façon cohérente et productive. Les workflows Git encouragent les développeurs et les équipes DevOps à exploiter Git de façon efficace et cohérente.

### Pourquoi Gitflow

Gitflow permet un développement en équipe tout en limitant les conflits. Chacun a la possibilité de travailler dans son coin pour développer des features et de les merger à n’importe quel moment dans le projet. C’est la manière d’organiser Git la plus utilisée, grâce à ses branches qui sont très efficaces, mais aussi à sa manière de gérer l’historique du code.

#### Initialiation de git flow

```bash 
git flow init
```

```bash 
Initialized empty Git repository in C:/Users/rapha/project/.git/ 
No branches exist yet. Base branches must be created now.
Branch name for production releases: [master] # Cliquer sur entrée
Branch name for "next release" development: [develop] # Cliquer sur entrée

How to name your supporting branch prefixes?
Feature branches? [feature/] # Cliquer sur entrée
Bugfix branches? [bugfix/] # Cliquer sur entrée
Release branches? [release/] # Cliquer sur entrée
Hotfix branches? [hotfix/] # Cliquer sur entrée
Support branches? [support/] # Cliquer sur entrée
Version tag prefix? [] # Cliquer sur entrée
Hooks and filters directory? [C:/Users/rapha/project/.git/hooks] # Cliquer sur entrée
```

### Les différentes branches 

![Branches git flow](../../asset/media/gitflow.svg)

- Je commence une nouvelle fonctionnalité -> Je créer une branche feature basé sur develop
- J'ai finis ma fonctionalité -> Merge (voir development standart) ma banche de feature dans develop
- Je veux mettre en production mon code -> Je fait une branche release basé sur develop
- La branche release est conforme -> Je merge release dans master et develop
- Je doit effectuer des correction sur master -> Je créer une branche hotfix basé sur master
- La branche hotfix est conforme -> Je merge hotfix dans master et develop

#### Nomenclature des branches

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

**Ref** numéro de ticket definissant à la fonctionnalitée correspondante

```<code pojet = ST ><id ticket> (ex: ST0000)```

**short description** déscription


### Les commits 

#### Pourquoi commit ?

##### Tu travail seul sur ta branche

1. Tu a finis t'as fonctionnaitées pour faire une merge request dans develop 
2. Tu veux integrer d'autres braches (local ou distante)
3. Tu veux mettre a jours ta branche distante pour assurer une backup de ton code
4. Tu veux changer de branche sans perdre tes modifications et tu sais pas utiliser git stash

Le reste du temps ton code est enregistré sur ton ordinateur, sauf si tu brûle ton PC il lui arrivera rien. 
Plus tu as de commits, plus tu te ferra chier lorsqu'il faudra rebase tes conflits. 

##### Tu travail à plusieurs sur ta branche

1. Pull / Push réguliérement
2. Communique avec les autres développeurs pour que vous soyez en phase 
3. Fuit 

#### Nomenclature des commits 

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

### Feature 

#### Création d'une branche de fonctionnalité

```bash 
git flow feature start <feature_branch>
```

#### Publier une fonctionnalité

```bash 
git flow feature publish <feature_branch>
```


## Git pull

/ ! \ Avant de commencer une fonctionnalité pull l'ensemble du code 
```bash 
git pull
```

## Git push

/ ! \  Ne Jamais push directement sur develop, passer par un pull request via github
```bash 
git push <remote> <branch>
```~