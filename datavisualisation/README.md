# Visualisations
<div align="justify">
Avec cette base de données, nous avons de nombreuses idées de visualisations. La première et la plus évidente était la présentation d'images des oeuvres, même si au début l'idée de ne travailler que sur des peintures n'était pas encore toute tracée. Deux autres axes sont apparus : l'étude de l'oeuvre et celle de l'artiste selon les données récoltées. 
  
En ce qui concerne les oeuvres, nous avions pour objectif de travailler avec les dates de manière importante afin de pouvoir analyser les évolutions au cours du temps. A côté de cela, il nous paraissait important d'étuder les types de ces oeuvres, c'est-à-dire leur genre, le mouvement dans lequel elles s'inscrivent, leur support, la technique utilisée pour leur création... Dans la même lignée, il nous semblait important de mettre l'accent également sur leurs dimensions.

Pour les artistes, il nous paraissait important de les décrire. Nous avions idée d'utiliser les dates de naissance et de mort. Nous souhaitions également étudier leur migration géographique en comparant les lieux de mort et les lieux de naissance. Il nous fallait ainsi également étudier les nationalités, ainsi que les influences qu'ils avaient subi.

Nous savions ce que nous avions envie de montrer, mais lorsqu'il a fallu réaliser la visualisation, les questions de forme, mais aussi de la donnée et ses posssibilités de rendu sont devenues prégnantes. Certaines des visualisations auxquelles nous avions pensé ne fonctionnaient pas faute de données suffisantes ou de visualisation assez claire. A l'inverse, le nettoyage nous a donné de nouvelles idées. Nous avons pu les mettre en oeuvre dans différents cadres : Tableau Public et Palladio.

## Tableau Public
[Tableau Public](https://public.tableau.com/s/)


## Palladio
Ayant à traiter des oeuvres picturales, il était important de pouvoir rendre compte de celles-ci visuellement en passant par des représentations. Cela n'étant pas possible dans Tableau, il a fallu passer par [Palladio](http://hdlab.stanford.edu/palladio/) afin de réaliser une visualisation. Etant donné qu'il n'est pas possible de récupérer la visualisation créée, nous avons téléchargé le fichier json lorsque celle-ci a été terminée. Il se trouve également dans ce dossier. Nous voulions également pouvoir rendre compte de ce que nous avions effectivement fait dans Palladio. Ci-dessous se trouvent quelques images qui rendent compte de la visualisation.

<p align="center">
  <img src="../images/Palladio1" width="1000"/>
</p>

Comme on peut le voir sur cette première image, nous avons pu lier les images, ainsi que leur titre, leur sujet et leur artiste. Cela crée de cette manière des cartels assez intéressants et plutôt lisibles.

<p align="center">
  <img src="../images/Palladio2" width="1000"/>
</p>

Cela correspond à quatre colonnes dans la base de données. Ces données ont été choisies dans l'optique de rappeler ce que l'on trouve dans les musées, bien que l'on soit limité en quantité. Comme on peut le voir dans cet encart en haut à droite de cette image, il n'y a pas beaucoup de champs disponibles. Il n'en reste pas moins que s'il on avait eu la possibilité d'ajouter plus d'informations, cela aurait pu rendre une visualisation déjà lourde, encore plus conséquente et difficile à charger. La visualisation par année de création donne une vision de l'évolution de la peinture dans le temps, en ce qui concerne les sujets, les genres, les couleurs...

<p align="center">
  <img src="../images/Palladio3" width="1000"/>
</p>

En outre, n'ayant pas des images pour toutes les oeuvres, nous avons décidé de filtrer toute oeuvre qui n'aurait pas le lien vers une image. Cela a été possible grâce à la colonne de type boleen créée en amont selon ce critère. Ce filtre a pu être mis en place grâce à l'encart qui se trouve en bas de la page de visualisation de Palladio, comme montré sur cette image.
</div>
