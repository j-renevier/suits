# Gestion des versions 

Version Majeur :
- Rétrocompatibilité du non code assuré
- Ajout de nouvelles fonctionnalités majeur

Version Mineure :
- Rétrocompatibilité du code assuré
- Ajout de nouvelles fonctionnalités
- Corrections de bugs

Correctif :
- Résolution rapide de problème critiques
- Rétrocompatibilité du code assuré
- Pas d'ajout de nouvelles fonctionnalités

## Nomenclature

| Instance     | Numéro  | Version majeur     | Version mineur      | Correctif  | 
| ---          | ---     | --                 | ---                 | ---        | 
| Production   | 0.1.2-3 | Version majeur : 0 | Version mineur: 1.2 | hotfix: 3  | 
| Recette      | 0.1.2-3 | Version majeur : 0 | Version mineur: 1.2 | release: 3 | 
| Developement | 0.1.2-3 | Version majeur : 0 | Version mineur: 1.2 | null       | 

## Mise à jour du numéro de version

- Sur quel branche ? Sur la branche de développment
- Dans quel fichier ? Dans le fichier .env et dans le fichier package.json du service
- Quand ? Lors de la création d'un branche de recette 

## Mise à jour du numéro de correction

- Sur quel branche ? Sur la branche à corriger
- Dans quel fichier ? Dans le fichier .env et dans le fichier package.json du service
- Quand ? Avant de commencer les modification 