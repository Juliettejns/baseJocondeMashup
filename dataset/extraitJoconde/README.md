# Nettoyage de l'extrait de la base Joconde
<div align="justify">
Ce dossier contient l'[extrait de la Base Joconde](https://github.com/Juliettejns/baseJocondeMashup/blob/main/dataset/extraitJoconde/base-joconde-extrait.tar.xz) qui nous a servi de document de travail originel, le [fichier final] découlant directement du premier, ainsi que la documentation associée.

## Récupération de données
Il nous a été possible de récupérer les données de la Base Joconde par le biais du site [data.gouv.fr](https://www.data.gouv.fr/fr/datasets/collections-des-musees-de-france-extrait-de-la-base-joconde/), d'où il est possible d'extraire une part des données de la base complète. Cette dernière contient plus de 650 000 notices. 

Dans Dataiku, nous avons eu la possibilité de choisir quel type de cette part nous allions pouvoir utiliser : nous avons sélectionné un panel de 50 % aléatoire.

## Nettoyage des données
Nous avons tout d'abord réduit le très grand nombre de colonnes originel en en retirant quelques-unes qui ne nous paraissaient pas assez pertinentes pour une visualisation, telles que "Date de mise à jour" ou "Période de l'original copié". L'autre critère de ces suppressions était de garder ce qui nous apparaissait le plus intéressant à visualiser. 

Sur les colonnes restantes, nous les avons avant tout renommées afin de les rendre toutes compréhensibles. Puis il a fallu nettoyer les données plus directement. Nous avons commencé par ajuster les types des colonnes. Puis nous avons travaillé sur les différentes dates en présence. Afin de faciliter toute visualisation par la suite et étant donné que ces dates sont très disparates, nous avons retiré toute mention de mois ou de jour. En ce qui concerne les mesures des oeuvres de la base, hauteurs et longueurs se trouvaient dans la même colonne : nous les avons donc séparées dans deux colonnes différentes.

Nous avons dû travailler de la même manière pour de nombreuses colonnes de textes dans lesquelles avaient été aglomérées des informations qui étaient redondantes ou qui n'étaient pas égales selon les lignes. Cela a été le cas pour des colonnes comme "Domaine" ou "Statut juridique". Par exemple, cette denière comprenait aléatoirement le nom de l'institution qui conserve l'oeuvre, la ville et/ou la région de l'institution, le statut juridique, ainsi que la manière dont l'oeuvre avait été acquise. Pour ce qui était des deux premières informations, elles existaient par ailleurs dans d'autres colonnes beaucoup plus propres. Nous avons ensuite nettoyé ce qui restait (remplaçant ce qui n'existait pas par la mention "None") et spérare cela en deux colonnes distinctes.

Dans l'idée de rendre plus aisée toute lecture de nos visualisations, nous nous sommes exclusivement penchées sur des oeuvres qui étaient créées par une seule personne : nous avons donc retiré toute oeuvre créée à plusieurs. Nous avons par la suite nettoyé la colonne "Auteurs" en retirant tout ce qui n'était pas le nom et le prénom de ces derniers.

Il a également fallu normaliser ce qui se trouvait dans la colonne "Nationalité" et dans la colonne "Ecole-Pays", afin que cela soit le plus aisément lisible dans une visualisation. Pour cette raison, nous avons aussi dédoublé sciemment certaines colonnes afin de créer des colonnes au contenu simplifié. Par exemple, cela a été le cas pour la colonne "Mode d'acquisition", où nous avons de nombreuses choses différentes, ce qui, nous le savions, rendrait la lisibilité de toute graphe difficile. C'est pour cette raison qu enous avons une colonne "Mode d'acquisition" et "Mode d'acquisition simplifiée", où pour la première nous avons une entrée "dation" qu'on retrouvera sous "don" dans la seconde.

Afin de faciliter la jointure avec les deux autres datasets, nous avons pris le parti de supprimer  en amont toutes les lignes dont le domaine n'était pas la peinture, suite au constat de leur plus grande représentativité dans les images récupérées sur Wikidata. Dans la même lancée, nous avons également retiré en amont plusieurs colonnes dont nous savions que les données n'étaient pas aussi complètes et/ou propres que celles récupérées dans Wikidata, comme pour les matériaux et les techniques.
</div>
