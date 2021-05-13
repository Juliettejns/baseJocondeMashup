# Base Joconde Mashup

Ce dépôt contient un projet de mashup de données autour d'un extrait de la Base Joconde, répertoriant les oeuvres d'art des musées français et accessible sur
[data.culture.gouv.fr](https://data.culture.gouv.fr/explore/dataset/base-joconde-extrait/information/). Ce travail est réalisé dans le cadre du cours de Science de la donnée du [Master 2](http://www.chartes.psl.eu/fr/cursus/master-technologies-numeriques-appliquees-histoire) Technologies numériques appliquées à l'Histoire de l'École nationale des Chartes.

## Justification du dataset 
### 1 Constat
- comment est notre dataset Joconde (gros, difficile à traiter sur les ordi et très mal organisé car rempli à la main) => on a voulu récupérer des infos plus propres venant de WD
- sur WD on a trouvé des infos plus propres sur les auteurs/oeuvres dont les images => comme la plupart des images sont des images de peinture, on a décidé de partir sur une focalisation sur la peinture
### 2. Nettoyage
#### a Nettoyage Joconde 
-> voir le README correspondant
#### b Nettoyage WD
-> voir le README correspondant
### 3. Résultat du join
Test avec un left-join : très peu d'infos correspondant à notre DS dans WD (à peine une 100aine)
Finalement avec un inner-join on passe de 17000 à 700 dans le DS final.

### Conclusion
les 3 DS ne coincidaient pas du tout, mais on a continué car c'était intéressat de voir ce que pouvaient donner ce genre de jointures en visualisation

## Visualisation
### Visualisation 1
balbal
### Visualisation 2
balbal
...

## Repository
```
├── dataset
│     ├── extraitJoconde
|     |    ├── baseJoconde_extrait.tar.xz
│     │    ├── baseJoconde_prepared.csv 
|     |    └── README.md
|     |
│     ├── wikiDataSPARQL
|     |    ├── query_auteurs.csv
|     |    ├── query_oeuvre.csv
|     |    ├── query_auteurs_prepared.csv
│     │    ├── query_oeuvre_prepared.csv
|     |    └── README.md
|     |
|     ├── base_joconde_oeuvres.csv
|     ├── base_joconde_oeuvres_auteurs.csv
|     └── README.md
|
├── imgs
└── README.md
```
## Crédits
Ce dépôt est développé par [Mathilde Liteau](http://github.com/mathildeliteau), [Claire Jahan](http://github.com/Heresta) et [Juliette Janes](http://github.com/Juliettejns), étudiantes de la promotion 2021 du Master 2 Technologies numériques appliquées à l'Histoire de l'École nationale des Chartes.

## Licence
Ce dépôt est CC-BY.</br>
![68747470733a2f2f692e6372656174697665636f6d6d6f6e732e6f72672f6c2f62792f322e302f38387833312e706e67](https://user-images.githubusercontent.com/56683417/115525743-a78d2400-a28f-11eb-8e45-4b6e3265a527.png)

## Contacts
Pour toute question: juliette.janes@chartes.psl.eu 
