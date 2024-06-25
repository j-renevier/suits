# Git flow

## Référence

- [git-flow cheatsheet](https://danielkummer.github.io/git-flow-cheatsheet/index.fr_FR.html)

## Déscription

Gitflow définit un modèle de branches strict conçu autour de la version du projet. Il n'ajoute aucun nouveau concept ni aucune nouvelle commande en dehors de ce qui est exigé pour le workflow de branche de fonctionnalité.

![Git flow](../../asset/media/gitflow-model.png)

### Master 

Branche de production
- Contient la dernière version stable du produit livrable et opérationnel
- Aucune modification

### Hotfix 

Branche de maintenance
- Branche de réalisation d’un correctif
- Permet de corriger un bug en prod sans bloquer le développement
- Créée à partir de master
- Sera fusionnée dans master et dans develop puis détruite

### Release 

Branche de livraison
- Branche de préparation à la livraison d’une nouvelle version
- Permet de stabiliser une livraison sans bloquer le développement
- Créée à partir de develop
- sera fusionnée dans master et dans develop puis détruite

### Develop 

Branche de développement
- Branche principale, véritable colonne vertébrale du dépôt
- Branche d’intégration des développements

### Feature

Branche de fonctionnalité
- Branche de développement d’une fonctionnalité
- Créée à partir de develop
- Branche temporaire


## Installation

### Debian / Ubuntu 

```bash
sudo apt install git-flow
```
### Windows 

```bash
wget -q -O - --no-check-certificate https://raw.github.com/petervanderdoes/gitflow-avh/develop/contrib/gitflow-installer.sh install stable | bash
```

## Initialisation

### Initialiser un dêpot local

```bash
git flow init
```

### Initialiser un dêpot local en utilisant git flow depuis un dêpot distant

```bash
# Clone repository
git clone <Lien vers le repo>

# Init git flow
git flow init
```

## Configurer la structure des branches

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

## Commandes de base

|         |         |         |              |      |
| ---     | ---     | ---     | ---          | ---  |
|         | init    |         |              | -[d] |
|git flow | feature | start   | <branch-name>|      |
|         | release | finish  |              |      |
|         | hotfix  | publish |              |      |
|         |         | pull    |              |      |

### Créer un branch 