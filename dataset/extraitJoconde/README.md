# Nettoyage de l'extrait de la base Joconde
Ce dossier contient l'extrait de la base Joconde, récupérée sur le site culture.data.gouv.fr, sa version préparée et nettoyée en sortie de Dataiku et la documentation correspondante.

La base Joconde, dans sa globalité, est composée de 650 000 notices et décrit les oeuvres des musées de France. Elle est liée à la base Muséofile, qui décrit les musées de France. L'extrait sur lequel nous avons travaillé est d'environ 60 000 oeuvres, soit un peu moins de 10% du set total. Ainsi, le corpus de travail n'est pas du tout représentatif de la globalité de la base. 

## Suppression des colonnes non utiles
Sur les 34 colonnes de base, nous avons choisi de supprimer toutes les colonnes ayant moins d'un tiers de données et qui nous semblaient non indispensables, soit 11 colonnes. Détaille des colonnes supprimées.

## Normalisation des valeurs  
### Normalisation des Dates
=>Date d'acquisition, Date d'import, Millésime, nettoyage période dans l'optique d'une visualisation plus lisible de la répartition des oeuvres dans le temps
### Normalisation des termes
ex ville, région
### Simplification des termes
Réduction des valeurs pouvant être prise dans une même colonne dans le but d'obtenir une visualisation plus lisible (dans la plupart des colonnes)
## Colonnes à multiples informations
Division des colonnes statut juridique, matériaux, mesure, géolocalisation
Problème: Matériaux, Statut juridique:> plusieurs informations à rentrer dans la cellule donc pas toujours dans le même ordre. 
Résolution: pour les matériaux, récupération plus standardisée via Wikidata, avec les techniques à gauche et les supports à droite


## Résultat

IMAGE DES DIFFÉRENTES COLONNES RÉCUPEREES
