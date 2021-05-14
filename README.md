# Base Joconde Mashup
<div align="justify">
Ce dépôt contient un projet de mashup de données autour d'un extrait de la Base Joconde, répertoriant les oeuvres d'art des musées français et accessible sur
[data.culture.gouv.fr](https://data.culture.gouv.fr/explore/dataset/base-joconde-extrait/information/). Ce travail est réalisé dans le cadre du cours de Science de la donnée du [Master 2](http://www.chartes.psl.eu/fr/cursus/master-technologies-numeriques-appliquees-histoire) Technologies numériques appliquées à l'Histoire de l'École nationale des Chartes.

## Réalisation du mashup
### 1. Présentation des données
Le dataset de travail, [extrait de la base Joconde](https://github.com/Juliettejns/baseJocondeMashup/tree/main/dataset/extraitJoconde/base-joconde-extrait.tar.xz), est composé de 60 000 lignes et 34 colonnes. Cette imposante taille a rendu le travail de nettoyage a réaliser particulièrement compliqué, notamment pour nos ordinateurs. La base a été remplie à la main, par chacun des musées, et, les colonnes pouvant contenir plusieurs informations différentes, les cellules ne sont pas du tout normalisées. Ainsi, face à la quantité d'informations difficiles à réorganiser et dans l'idée de réduire une étape chronophage, nous avons voulu récupérer des informations plus propres sur wikidata. </br>
Nous avons donc obtenu deux csv. Le premier, sur les oeuvres de la Base Joconde contenues dans Wikidata, soit 15759 éléments, présente à la fois des colonnes qui nous semblaient très compliquées à nettoyer et des colonnes d'informations non contenues dans l'extrait de la Base, à l'instar des images des oeuvres. Le second, sur les auteurs des oeuvres de la base Joconde contenues dans Wikidata, de  est essentiellement composé d'élément qui n'était dans la Base. La plupart des images récupérées dans Wikidata étant des images de peinture, nous avons décidé de nous focaliser sur les peintures dans la base Joconde, dans l'idée de réaliser une visualisation mettant l'accent sur une gallerie d'images. </br>
Il aurait été également intéressant d'associer notre extrait de la Base Joconde, à la base Muséofile, qui repertorie les musées de France. Cette idée est d'autant plus intéressante que le set de données possède une colonne comprenant les identifiants muséofiles des musées, ce qui permettraient de lier les deux csv facilement. Cependant, la base Muséofile est directement lié à la Base Joconde et les informations étaient donc déjà présentes.
### 2. Nettoyage des données
Pour une description détaillée du nettoyage de la base Joconde: ici.</br>
Pour une description détaillée des sets de données récupérés sur Wikidata: ici.</br>
### 3. Association des données
Une fois les trois sets de données nettoyés, il a fallu les associer. Pour ce faire, nous avions tout d'abord projeté de réaliser un left join. Cela permet de garder toutes les données de l'extrait de la Base Joconde correspondant aux peintures, et de leur associer, quand cela est possible, les informations récupérées sur Wikidata. Nous avons donc joint les données de la base Joconde au csv correspondant aux oeuvres Wikidata grâce à leurs identifiants. Nous avons alors obtenu un csv de 17000 lignes, dont seulement quelques petites centaines d'entre elles correspondaient aux données récupérées sur Wikidata. </br>
Nous avons alors réalisé que les données de l'extrait de la Base Joconde sur lequel nous avions travaillé et les données sur la base disponibles sur Wikidata ne coïncidaient absolument pas, ou alors très peu. Malgré cela, nous avons choisi de continuer à travailler dessus, en préférant faire un inner-join des données, soit uniquement les données présentes à la fois dans notre extrait de la Base Joconde et dans Wikidata, soit un dataset de presque 700 lignes. Cela nous permet de récupérer un set de données dans lequel les données de wikidata ne sont pas à peine visibles, sachant que celles-ci sont des colonnes assez importantes dans nos idées de visualisation. </br>
En dépit de la réduction drastique du dataset, qui n'est donc plus vraiment réprésentatif de la base Joconde, nous avons finalement obtenu un dataset nettoyé qui reste assez important pour réaliser des visualisations. Nous avons donc travaillé à la visualisation d'un dataset précis, correspondant à l'intersection entre un extrait de la base et les données de la base rendues accessible sur Wikidata. 

## Visualisation
=> ici on décrit de façon concise nos visualisations, que l'on peut détailler dans un README dans un dossier visualisation. + conclusion de ce que nous apprennent ces visualisations
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
