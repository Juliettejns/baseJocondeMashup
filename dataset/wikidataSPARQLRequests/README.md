# Données Wikidata

<div align="justify">
  
Ce dossier contient les fichiers csv, sur les oeuvres de la Base Joconde et sur les auteurs d'oeuvres de la Base Joconde, récupérés sur Wikidata, ainsi que leur version nettoyée sur Dataiku et la documentation associée.

## Récupération de données
<p align="center" class="float">

  <img src="/images/structurationRDFWikidata.png" width="450"/>

  </p>
  
Ce schéma donne une vision globale des différents éléments qu'il est possible de récupếrer sur Wikidata à propos de la Base Joconde. Réalisé par nos soins, il nous a notamment permis de bien comprendre la structure des triplets RDF et donc d'élaborer plus facilement des requêtes SPARQL fonctionnelles afin d'obtenir les différents éléments évoqués. </br>
Dans un premier temps, on a ainsi pu récupérer des données qui n'étaient pas dans l'extrait de la base, à l'instar des images des oeuvres et de leur genre artistique ainsi que des données sur les auteurs des oeuvres, telles que les dates et lieux de naissance et de morts et les mouvements caractéristiques de ceux-ci. </br>
Dans un second temps, face aux différentes données peu manipulables dans l'extrait de la base Joconde à nettoyer, dû à leur importance et la variété de structure des cellules, nous avons décidé de récupérer certaines données qui, grâce aux requêtes SPARQL, se sont avérées plus normalisées, donc mieux structurées et plus faciles à normaliser. C'est le cas des mesures, hauteur et largeur des oeuvres, qui ont toutes été récupérées séparemment et en centimètres, des matériaux, qui ont pû être divisés entre techniques utilisées et support ou encore les types.</br>
Dans un dernier temps, nous avons récupéré des données contenues dans l'extrait de la base Joconde, telles que les titres, dans un souci de certitude de ces informations. En effet, un certain nombre de titres était manquant, voire ne coïncidait pas.</br>
## Nettoyage des données
### Pour la requête concernant les oeuvres
Le fichier csv contenant les oeuvres de la base Joconde accessibles sur Wikidata est composé d'un peu plus de 15 000 lignes et de 10 colonnes, présentées ci-dessus:</br>
<table>
    <thead>
        <tr>
            <th align="left">Élément supprimé</th>
            <th align="left">Élément conservé</th>
            <th align="left">Élément ajouté</th>
            <th align="left">Liste finale</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td align="left"></td>
            <td align="left">nomcreateur</td>
            <td align="left">anneenaissance</td>
            <td align="left">nomcreateur</td>
        </tr
         <tr>
            <td align="left"></td>
            <td align="left">datenaissance</td>
            <td align="left"></td>
            <td align="left">datenaissance</td>
         </tr>
         <tr>
            <td align="left"></td>
            <td align="left">datemort</td>
            <td align="left"></td>
            <td align="left">datemort</td>
         </tr>
         <tr>
            <td align="left"></td>
            <td align="left">nationalité</td>
            <td align="left"></td>
            <td align="left">anneenaissance</td>
        </tr>
         <tr>
            <td align="left"></td>
            <td align="left">lieunaissance</td>
            <td align="left"></td>
            <td align="left">lieunaissance</td>
         </tr>
         <tr>
            <td align="left"></td>
            <td align="left">mouvement</td>
            <td align="left"></td>
            <td align="left">mouvement</td>
         </tr> 
         <tr>
            <td align="left"></td>
            <td align="left">lieumort</td>
            <td align="left"></td>
            <td align="left">lieumort</td>
         </tr>
           <tr>
            <td align="left"></td>
            <td align="left"></td>
            <td align="left"></td>
            <td align="left">nationalité</td>
         </tr>
    </tbody>
</table>
Si ce résultat reste particulièrement propre, il a tout de même fallu le nettoyer un peu. Nous n'avons d'abord conservé que ce qui ressemble à des peintures, ce qui a été fait en filtrant avec la colonne `type` C'est notamment le cas des ``dates``, qu'il a fallu nettoyer pour ne garder que l'année, dans l'idée de réaliser une visualisation à partir de cela, ou encore, de la colonne `matériel`. Celle-ci a été un peu plus longue à restructurer, puisqu'il a fallu la diviser en deux colonnes, une première contenant les `techniques de peinture` et une seconde les `supports`. Les `genres` ont été nettoyés pour normaliser les différents termes et une colonne `genre simplifié` a été créée.

### Pour la requête concernant les auteurs
Le fichier csv contenant les auteurs ayant réalisé des oeuvres de la base Joconde accessibles sur Wikidata est composé de 500 lignes et de 6 colonnes, présentées ci-dessus:</br>
<table>
    <thead>
        <tr>
            <th align="left">Élément supprimé</th>
            <th align="left">Élément conservé</th>
            <th align="left">Élément ajouté</th>
            <th align="left">Liste finale</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td align="left"></td>
            <td align="left">identifiant</td>
            <td align="left"></td>
            <td align="left">identifiant</td>
        </tr
         <tr>
            <td align="left"></td>
            <td align="left">titre</td>
            <td align="left"></td>
            <td align="left">titre</td>
         </tr>
         <tr>
            <td align="left"></td>
            <td align="left">nomcreateur</td>
            <td align="left"></td>
            <td align="left">nomcreateur</td>
         </tr>
         <tr>
            <td align="left"></td>
            <td align="left">datecreation</td>
            <td align="left"></td>
            <td align="left">anneecreation</td>
        </tr>
         <tr>
            <td align="left"></td>
            <td align="left">largeur</td>
            <td align="left"></td>
            <td align="left">largeur (cm)</td>
         </tr>
         <tr>
            <td align="left"></td>
            <td align="left">hauteur</td>
            <td align="left"></td>
            <td align="left">hauteur (cm)</td>
         </tr> 
         <tr>
            <td align="left"></td>
            <td align="left">type</td>
            <td align="left"></td>
            <td align="left">type</td>
         </tr>
         <tr>
            <td align="left"></td>
            <td align="left">materiel</td>
            <td align="left"></td>
            <td align="left">techniques</td>
         </tr>
         <tr>
            <td align="left"></td>
            <td align="left"></td>
            <td align="left"></td>
            <td align="left">support</td>
         </tr>
         <tr>
            <td align="left"></td>
            <td align="left">genre</td>
            <td align="left"></td>
            <td align="left">genre</td>
         </tr>
         <tr>
            <td align="left"></td>
            <td align="left">image</td>
            <td align="left"></td>
            <td align="left">image</td>
         </tr>
    </tbody>
</table>
Là aussi, le fait d'avoir réquêté assez précisemment dans Wikidata a permis d'obtenir des données assez propres et ne nécessitant pas trop de travail de nettoyage. Les `dates de naissance et de mort` ont été nettoyé pour ne garder également que l'année. Les `lieux de naissance et de mort` ont été nettoyés dans le but de garder uniquement les noms de villes et non plus les quartiers. Les `mouvements` ont été normalisés.

</div>
