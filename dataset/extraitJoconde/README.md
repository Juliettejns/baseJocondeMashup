<div align="justify">

# Nettoyage de l'extrait de la base Joconde
Ce dossier contient l'[extrait de la Base Joconde](https://github.com/Juliettejns/baseJocondeMashup/blob/main/dataset/extraitJoconde/base-joconde-extrait.tar.xz), récupérée sur le site [data.gouv.fr](https://www.data.gouv.fr/fr/datasets/collections-des-musees-de-france-extrait-de-la-base-joconde/), sa version préparée et nettoyée en sortie de Dataiku et la documentation correspondante.

La base Joconde, dans sa globalité, est composée de 650 000 notices et décrit les oeuvres des institutions de conservation de France. Elle est liée à la base Muséofile, qui décrit les musées de France. L'extrait sur lequel nous avons travaillé est d'environ 60 000 oeuvres, soit un peu moins de 10 % du set total. Nous avions conscience dès le début que  le corpus de travail n'est pas du tout représentatif de la globalité de la base. Dans Dataiku, nous avons eu la possibilité de choisir quelle part de ce set nous allions pouvoir utiliser : nous avons sélectionné un panel de 50 % aléatoire.

Les csv manipulés étant trop importants pour GitHub, nous avons utilisé une extension appelée [GitHub LFS](https://git-lfs.github.com/) pour nous permettre de les ajouter au dépôt. 

## Nettoyage des données
### Suppression des colonnes inutiles
Sur les 34 colonnes de base, nous avons choisi de supprimer toutes celles ayant moins d'un tiers de données et qui nous semblaient facultatives, soit 11 colonnes. Nous n'avons donc pas conservé par exemple ``Date de mise à jour`` ou ``Période de l'original copié``. 

### Normalisation des valeurs  
Sur les colonnes restantes, nous les avons avant tout renommées afin de les rendre toutes compréhensibles. Puis il a fallu nettoyer les données plus directement.
#### Normalisation des _Integer_
Afin de faciliter toute visualisation par la suite et étant donné que ces dates sont très disparates, nous avons retiré toute mention de mois ou de jour. Cela a été le cas par exemple sur ``Date d'acquisition``. En ce qui concerne les mesures des oeuvres de la base, hauteurs et longueurs se trouvaient dans la même colonne : nous les avons donc séparées dans deux différentes. 
#### Normalisation des termes
Nous avons également dû travailler sur la normalisation des terminologies, notamment en ce qui concerne les colonnes ``Ville`` et ``Région``. Cela est passé par une mise en majuscule de toutes les premières lettres de tous les termes, ainsi que leur uniformisation.
### Colonnes à multiples informations
Nous avons dû travailler à réduire les données sur de nombreuses colonnes de texte dans lesquelles avaient été aglomérées des informations qui étaient redondantes ou qui n'étaient pas équivalentes selon les lignes. Cela a été le cas pour des colonnes comme ``géolocalisation``, ``Domaine`` ou ``Statut juridique``. Par exemple, cette denière comprenait aléatoirement le nom de l'institution qui conserve l'oeuvre, la ville et/ou la région de l'institution, le statut juridique, ainsi que la manière dont l'oeuvre avait été acquise. Pour ce qui était des deux premières informations, elles existaient par ailleurs dans d'autres colonnes beaucoup plus propres. Nous avons ensuite nettoyé ce qui restait (remplaçant ce qui n'existait pas par la mention "None") et séparé cela en deux colonnes distinctes. Ce qui a été vraiment problématique dans les colonnes de ce type était que les informations n'étaient jamais dans le même ordre, même lorsque cela concernait des oeuvres provenant de la même institution de conservation.

Dans l'idée de rendre plus aisée toute lecture de nos visualisations, nous nous sommes exclusivement penché sur des oeuvres qui avaient été créées par une seule personne : nous avons donc retiré toute oeuvre liée à plusieurs artistes. Nous avons par la suite nettoyé la colonne ``Auteurs`` en retirant tout ce qui n'était pas le nom et le prénom de ces derniers.

### Dédoublement de colonnes
Toujours pour des raisons de visualisation finale, nous avons dédoublé sciemment certaines colonnes afin de créer des colonnes au contenu simplifié. Par exemple, cela a été le cas pour la colonne ``Mode d'acquisition``, où nous avons de nombreuses choses différentes, ce qui, nous le savions, rendrait la lisibilité de tout graphe difficile. C'est pour cette raison que nous avons une colonne ``Mode d'acquisition`` et ``Mode d'acquisition simplifiée``, où pour la première nous avons une entrée "dation" qu'on retrouvera sous "don" dans la seconde.

### Dernières étapes avant la jointure
Ces dernières modifications du dataset ont eu lieu lorsque toutes les précédentes avaient été réalisées et que les fichiers csv provenant des requêtes SPARQL avaient été également nettoyés. En effet, afin de faciliter la jointure avec les deux autres datasets, nous avons pris le parti de supprimer en amont toutes les lignes dont le domaine n'était pas la peinture, suite au constat de leur plus grande représentativité dans les images récupérées sur Wikidata. Dans la même lancée, nous avons également retiré plusieurs colonnes dont nous savions que les données n'étaient pas aussi complètes et/ou propres que celles récupérées dans Wikidata, comme pour les matériaux et les techniques.

## Résultat
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
            <td align="left">Ancien dépôt</td>
            <td align="left">Auteur</td>
            <td align="left">Date_acquisition</td>
            <td align="left">Référence</td>
        </tr>
        <tr>
            <td align="left">Appellation</td>
            <td align="left">Domaine</td>
            <td align="left">Mode_acquisition_simplifié</td>
            <td align="left">Auteurs</td>
        </tr>
        <tr>
            <td align="left">Date d’acquisition</td>
            <td align="left">Ecole</td>
            <td align="left">Mode_acquisition</td>
            <td align="left">Date_acquisition</td>
        </tr>
        <tr>
            <td align="left">Date de dépôt</td>
            <td align="left">Géographie historique</td>
            <td align="left">Latitude</td>
            <td align="left">Dénomination</td>
        </tr
        <tr>
            <td align="left">Découverte / Collecte</td>
            <td align="left">Numéro musée de France</td>
            <td align="left">Longitude</td>
            <td align="left">Entrée_base</td>
        </tr
        <tr>
            <td align="left">Utilisation</td>
            <td align="left">Lieu de création / utilisation</td>
            <td align="left"></td>
            <td align="left">Domaine</td>
        </tr
        <tr>
            <td align="left">Dépôt</td>
            <td align="left">Lieu de conservation</td>
            <td align="left"></td>
            <td align="left">Ecole_pays</td>
        </tr
        <tr>
            <td align="left">Mesures</td>
            <td align="left">Identiant base Museofile</td>
            <td align="left"></td>
            <td align="left">Date_création</td>
        </tr
        <tr>
            <td align="left">Date de mise à jour</td>
            <td align="left">Référence</td>
            <td align="left"></td>
            <td align="left">Identifiant_Museofile</td>
        </tr
        <tr>
            <td align="left">Titre</td>
            <td align="left">Sujet</td>
            <td align="left"></td>
            <td align="left">Nom_officiel_musée</td>
        </tr
        <tr>
            <td align="left">Epoque / style / mouvement</td>
            <td align="left">Source de la représentation</td>
            <td align="left"></td>
            <td align="left">Sujet_représenté</td>
        </tr
            <tr>
            <td align="left">Millésime</td>
            <td align="left">Statut juridique</td>
            <td align="left"></td>
            <td align="left">Statut_juridique</td>
        </tr
        <tr>
            <td align="left">Millésime d’utilisation</td>
            <td align="left">Dénomination</td>
            <td align="left"></td>
            <td align="left">Mode_acquisition_simplifié</td>
        </tr
        <tr>
            <td align="left">Onomastique</td>
            <td align="left">Date d'import</td>
            <td align="left"></td>
            <td align="left">Mode_acquisition</td>
        </tr
        <tr>
            <td align="left">Précisions sur l'auteur</td>
            <td align="left"></td>
            <td align="left"></td>
            <td align="left">Ville</td>
        </tr
        <tr>
            <td align="left">Période de l’original copié</td>
            <td align="left"></td>
            <td align="left"></td>
            <td align="left">Région</td>
        </tr
        <tr>
            <td align="left">Période</td>
            <td align="left"></td>
            <td align="left"></td>
            <td align="left">Latitude</td>
        </tr
        <tr>
            <td align="left">Période d’utilisation</td>
            <td align="left"></td>
            <td align="left"></td>
            <td align="left">Longitude</td>
        </tr
        <tr>
            <td align="left">Matériaux et techniques</td>
            <td align="left"></td>
            <td align="left"></td>
            <td align="left"></td>
        </tr>
    </tbody>
</table>

</div>
