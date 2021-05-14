# Données Wikidata

Ce dossier contient les csv, sur les oeuvres de la Base Joconde et sur les auteurs d'oeuvres de la Base Joconde, récupérés sur Wikidata, ainsi que leur version nettoyées sur Dataiku et la documentation associée.

## Récupération de données
### Base Joconde et Wikidata
ici mettre le schéma RDF et détailler ce que l'on peut récupérer grâce à wikidata. Indiquer nos choix de récupération. 
### Requêtes SPARQL
Requête pour récupérer les données concernant les oeuvres de la base Joconde présentent sur Wikidata:
```
PREFIX wd: <http://www.wikidata.org/entity/>
PREFIX p: <http://www.wikidata.org/prop/>
PREFIX wdt: <http://www.wikidata.org/prop/direct/>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>

SELECT ?identifiant 
(SAMPLE(?titre) AS ? titre)
(SAMPLE(?nomcreateur)AS?nomcreateur) 
(SAMPLE(?datecreation) AS ?datecreation) 
(SAMPLE(?largeur) AS ?largeur)
(SAMPLE(?hauteur) AS ?hauteur)
(SAMPLE(?typeLabel) AS ?type)
(GROUP_CONCAT(DISTINCT ?materielLabel;SEPARATOR=",") AS ?materiel)
(SAMPLE(?genreLabel) AS ?genre)
(SAMPLE(?image) AS ?image)
WHERE {?oeuvre wdt:P347 ?identifiant.
               OPTIONAL{?oeuvre rdfs:label ?titre.
                                FILTER (lang(?titre)='fr')}
               OPTIONAL{?oeuvre wdt:P2049 ?largeur;
                                wdt:P2048 ?hauteur.}
               OPTIONAL{?oeuvre wdt:P571 ?datecreation.}
               OPTIONAL{?oeuvre wdt:P170 ?createur.
                        ?createur wdt:P1559 ?nomcreateur.}
               OPTIONAL{?oeuvre wdt:P31 ?type.
                       ?type rdfs:label ?typeLabel.
                       FILTER (lang(?typeLabel)='fr')}
                OPTIONAL{?oeuvre wdt:P186 ?materiel.
                       ?materiel rdfs:label ?materielLabel.
                       FILTER (lang(?materielLabel)='fr')}
               OPTIONAL{?oeuvre wdt:P186 ?materiel.
                       ?materiel rdfs:label ?materielLabel.
                       FILTER (lang(?materielLabel)='fr')}
               OPTIONAL{?oeuvre wdt:P136 ?genre.
                       ?genre rdfs:label ?genreLabel.
                       FILTER (lang(?genreLabel)='fr')}
               OPTIONAL{?oeuvre wdt:P18 ?image.}
               }
GROUP BY ?identifiant
```
Requête pour récupérer les données concernant les auteurs des oeuvres de la Base Joconde présentes dans Wikidata:
```
PREFIX wd: <http://www.wikidata.org/entity/>
PREFIX p: <http://www.wikidata.org/prop/>
PREFIX wdt: <http://www.wikidata.org/prop/direct/>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>

SELECT DISTINCT
?nomcreateur 
(SAMPLE(?datenaissance) AS ?datenaissance) 
(SAMPLE(?datemort) AS ?datemort)
(GROUP_CONCAT(DISTINCT ?nationalitéLabel;SEPARATOR=',') AS ?nationalité)
(SAMPLE(?lieunaissanceLabel) AS ?lieunaissance)
(SAMPLE(?lieumortLabel) AS ?lieumort)
(SAMPLE(?mouvementLabel) AS ?mouvement)
WHERE {
  ?oeuvre wdt:P347 ?identifiant;
    wdt:P170 ?createur.
  ?createur wdt:P1559 ?nomcreateur; 
            wdt:P27 ?nationalité.
  ?nationalité rdfs:label ?nationalitéLabel.
  FILTER(lang(?nationalitéLabel)='fr')
  OPTIONAL {
    ?createur wdt:P569 ?datenaissance;
              wdt:P570 ?datemort;
              wdt:P19 ?lieunaissance;
              wdt:P20 ?lieumort.
    ?lieunaissance rdfs:label ?lieunaissanceLabel.
    ?lieumort rdfs:label ?lieumortLabel.
    FILTER(lang(?lieunaissanceLabel)='fr')
    FILTER(lang(?lieumortLabel)='fr')
  }
  OPTIONAL{
    ?createur wdt:P135 ?mouvement.
    ?mouvement rdfs:label ?mouvementLabel.
    FILTER (lang(?mouvementLabel)='fr')} 
              }

GROUP BY ?identifiant ?nomcreateur 
```


## Nettoyage de données
### Pour la requête oeuvre
### Pour la requête auteur
détail des choix de nettoyage faits + informations chiffrés sur le nbre d'éléments obtenus
