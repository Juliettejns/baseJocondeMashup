# Visualisations
=> ici on décrit de façon nos choix de visualisation

## Tableau Public

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
