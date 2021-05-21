# Base Joconde Mashup
<div align="justify">
  
Ce dépôt contient un projet de mashup de données autour d'un extrait de la Base Joconde, répertoriant les oeuvres d'art des musées français et accessible sur
[data.culture.gouv.fr](https://data.culture.gouv.fr/explore/dataset/base-joconde-extrait/information/). Ce travail est réalisé dans le cadre du cours de Science de la donnée du [Master 2](http://www.chartes.psl.eu/fr/cursus/master-technologies-numeriques-appliquees-histoire) Technologies numériques appliquées à l'Histoire de l'École nationale des Chartes.

## Réalisation du Mashup
<p align="center">
  <img src="images/pipeline_mashup.png" width="400"/>
</p>

Pour une description détaillée du travail réalisé : [ici](https://github.com/Juliettejns/baseJocondeMashup/blob/documentation_nettoye/dataset/README.md)

## Visualisation
Nous avons réalisé trois tableaux de bord sur Tableau Public, ainsi qu'une visualisation sur Palladio (pour plus d'informations sur ces visualisation, cliquer [ici](https://github.com/Juliettejns/baseJocondeMashup/tree/main/datavisualisation)).

## Conclusion
- Ce que ça nous apprend sur les datas en prenant des pincettes

Outre toutes les informations que cela peut nous apprendre sur les données récoltées, nous avons également beaucoup appris sur la création d'un mashup de données et sa transformation en datavisualisation. En effet, les données peuvent être très longues à nettoyer afin de s'assurer un rendu et une étude intéressante. De plus, l'ajout de données en provenance d'autres bases n'est pas toujours le plus aisé et peut parfois réduire drastiquement la quantité de celles-ci. A l'inverse, si cette réduction de données peut surprendre, l'amélioration de la qualité des données a été largement appréciable. Concernant la datavisualisation, même si tout n'a pas pu être fait dans le même cadre, nous avons pu voir voir avec intérêt toutes les possibilités que nous donnaient des données propres.

</div>

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
├── extraitJoconde
|    ├── ...
|    └── README.md
|
├── imgs
|
└── README.md
```
## Crédits
Ce dépôt est développé par [Mathilde Liteau](http://github.com/mathildeliteau), [Claire Jahan](http://github.com/Heresta) et [Juliette Janes](http://github.com/Juliettejns), étudiantes de la promotion 2021 du Master 2 Technologies numériques appliquées à l'Histoire de l'École nationale des Chartes.

## Licence
Ce dépôt est CC-BY.</br>
![68747470733a2f2f692e6372656174697665636f6d6d6f6e732e6f72672f6c2f62792f322e302f38387833312e706e67](https://user-images.githubusercontent.com/56683417/115525743-a78d2400-a28f-11eb-8e45-4b6e3265a527.png)

## Contacts
Pour toute question: juliette.janes@chartes.psl.eu 
