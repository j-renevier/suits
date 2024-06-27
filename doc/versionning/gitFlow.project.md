# Git flow 

## Introduction 

### Objctifs 

Comprendre le worflow gitflow
Se familiarsiser avec les commandes de git flow

### Prerequis

Être à l'aise avec le fonctionnement général de git

### Avant de partir 

Créer un dépôt distant vide
Renommer la branche main en master

## Simuler un gitflow

Faire un faux projet contenent **un seul fichier** index.html (html et css au même endroit)
Il est interdit de modifier les balise html et le style dans la même banche de feature (sinon ça va pas être très fun)

1. Clonner le dêpot distant 
2. Initialiser le dêpot avec git flow
3. Reproduire le graphique si dessous


## 

```bash

# 1. Créer un dêpot distant sur github

# 2. Créer un dossier local contenant le projet
mkdir gitflow

# 3. Ce déplacer dans le dossier du projet (et oui une fois sur deux cette étape est oublié)
cd gitflow/  

# 4. Initier le projet avec git flow 
git flow init

# 5. Configurer la structure des branches du projet
Initialized empty Git repository in C:/Users/rapha/project/003-Suits/gitflow/.git/
No branches exist yet. Base branches must be created now.
Branch name for production releases: [master]
Branch name for "next release" development: [develop]

How to name your supporting branch prefixes?
Feature branches? [feature/]
Bugfix branches? [bugfix/]
Release branches? [release/]
Hotfix branches? [hotfix/]
Support branches? [support/]
Version tag prefix? []
Hooks and filters directory? [C:/Users/rapha/project/003-Suits/gitflow/.git/hooks]

# --- Etat du projet --- #
git log --oneline --graph --decorate --all 
* 5a405e0 (HEAD -> develop, master) Initial commit
# ---------------------- #

# 6. Lier le projet local avec le dêpot distant 
git remote add origin git@github.com:j-renevier/gitflow.git

# 7. Publier les branches de départ
git push -u origin master
git push -u origin develop

# Si il y a déjà une branche main (=master) sur ton dêpot 
# tu l'efface, master devient la branche principale
# ou tu renomme main en master (normalement tu devrais pas avoir de problème, non je rigole j'en sais rien démerde toi)

# 8. Créer un tag 
git tag 0.0.1

# 9. publier un tag
git push origin 0.0.1  




```