# Utiliser des données OpenData <br>géographiques conjointement avec Github

par <a href="https://twitter.com/ThomasG77">@ThomasG77</a>, WebGeoDataVore

!SLIDE shout

# MapTime Nantes

## Utiliser des données OpenData<br> géographiques conjointement <br>avec Github par <a href="https://twitter.com/ThomasG77">@ThomasG77</a> (23 Juillet 2015)

!SLIDE

<br>

# Qui je suis?

Consultant SIG, OpenData et visualisation de données faisant du conseil, de la formation et du développement.

Auteur d'un livre sur [OpenLayers 3](https://www.packtpub.com/web-development/openlayers-3-beginner%E2%80%99s-guide) (en anglais), un bibliothèque JavaScript pour afficher des cartes en ligne

Spécialiste JavaScript et Python.

!SLIDE

<br>
# Posez des questions plutôt que d'être perdu

Comme le niveau peut être hétérogène, nous préférons être interrompu. Même si nous n'allons pas au bout de la présentation ou devons passer rapidement dessus, le support reste accessible.

!SLIDE

<br>

# Plan

1. Les données OpenData
2. Les données géographiques
3. Les projections et systèmes de coordonnées: <br> le minimum incontournable
4. Convertir les formats et les projections des fichiers pour Github
5. Github, quezako?

!SLIDE shout

# L'OpenData

!SLIDE

# Rappel

<center><iframe width="800" height="450" src="https://www.youtube.com/embed/aHxv_2BMJfw" frameborder="0" allowfullscreen></iframe></center>

!SLIDE

# [Data.gouv.fr](https://www.data.gouv.fr)

<center><a href="https://www.data.gouv.fr" target="_blank"><img src="images/data-gouv-fr.png" height="400px"/></a></center>

!SLIDE

# Portails locaux: [Inventaire avec OpenData Map](http://www.opendata-map.org/map)

<center><a href="http://www.opendata-map.org/map" target="_blank"><img src="images/open-data-map.png" height="400px"/></a></center>

!SLIDE

# Portails locaux du territoire

<center><a href="http://data.paysdelaloire.fr" target="_blank"><img src="images/opendata-region-pays-de-la-loire.png"/></a></center>

<center><a href="http://data.loire-atlantique.fr" target="_blank"><img src="images/opendata-departement-loire-atlantique.png"/></a></center>

<center><a href="http://data.nantes.fr" target="_blank"><img src="images/opendata-ville-nantes.png"/></a></center>

!SLIDE

# Données de référence échelle mondiale: [Natural Earth Data](http://www.naturalearthdata.com)

<center><a href="http://www.naturalearthdata.com" target="_blank"><img src="images/natural-earth-data.png" height="400px"/></a></center>

!SLIDE

# Données de référence échelle mondiale: OpenStreetMap

["OpenStreetMap ce n'est pas (qu') une carte"](http://geotribu.net/node/769)

[Exemple de données avec OverPass Turbo](http://overpass-turbo.eu/s/axU) (interroger les données d'OpenStreetMap)

[Metro extract](https://mapzen.com/data/metro-extracts) (Extraction de données par grandes villes dont Nantes)

[Extraction OpenStreetMap de GeoFabrik](http://download.geofabrik.de/europe/france.html) (par exemple la région Pays de La Loire)

!SLIDE

# De nombreuses autres sources de données

<br>

Mais ce n'est pas l'objet de cette présentation!

!SLIDE shout

# Les données géographiques

!SLIDE

# But: identifier ou filtrer les résultats en fonction des données géographiques

<img src="images/filtre-type-fichiers-open-data-loire-atlantique.png" height="300px" />
<img src="images/filtre-type-fichiers-data-gouv-fr.png" height="300px" />

!SLIDE

<br>

# Deux grands types de <br>données géographiques

* Raster
* Vecteur

!SLIDE

# Raster

<br>
<center><img src="images/raster.png"/></center>

!SLIDE

# Formats associés

Généralement, il s'agit de:

* TIF(F)(GeoTIFF) (extension `tif`)
* JPEG2000 (extension `jp2`)

Sinon, on accède à des services web comme le WMS comme [VueDuCiel.loire-atlantique.fr](http://vuduciel.loire-atlantique.fr/) pour cela.

!SLIDE

# Vecteur

<br>
<center><img src="images/vector_types.png" width="800px" /></center>

!SLIDE

<br>
# Les formats de données principaux

* SHP (lié historiquement au logiciel ArcView), inadapté pour le web
* MIF/MID ou TAB (lié au logiciel MapInfo), idem à SHP
* GeoJSON/TopoJSON, bon pour le web, à utiliser par défaut, (code EPSG 4326 recommandé)
* KML, bon pour le web mais avant tout pour les produits Google

Voir [MapSchool, section "Les formats vecteur"](http://mapschool.io/index.fr.html)

!SLIDE

# L'exception du format tabulaire

* CSV

<center><img src="images/illustration-csv-lat-long.png" width="600px"/></center>

!SLIDE shout

# Projections et systèmes de coordonnées

!SLIDE

# Pourquoi?

Parce que des exemples comme ci-dessous sont incompréhensibles pour un utilisateur final non spécialiste:

* L93 (Lambert 93),
* CC47 (Conique Conforme 47),
* WGS84 ou EPSG 4326
* EPSG:3857
* LAEA ETRS89

!SLIDE

# La forme de la Terre

<center><img src="images/earth-shapes.jpg" width="800" /></center>

!SLIDE

# Principes des projections

Déformation quand on passe de 3 dimensions à 2 dimensions

<center><img src="images/orangepeel.jpg"/></center>

<small>Crédits: http://krygier.owu.edu/krygier_html/geog_222/geog_222_lo/geog_222_lo13.html</small>

!SLIDE

<br>
# Types de projections:

* Conforme: conservation des angles (formes) <br> mais pas des distances ou des surfaces
* Equivalent: conservation des surfaces

!SLIDE

# Curiosités liées aux projections (1/2)

Nord pas forcément "en haut"

<center><img src="images/mcarthursmap.jpg" height="350" /></center>

<small>Crédits: [http://odt.org](http://www.odt.org/NewMaps.htm)</small>

!SLIDE

# Curiosités liées aux projections (2/2)

Centre de la carte du monde différent (non centré sur l'Atlantique)

<center><img src="images/Mercator-Projection-Japan-Centered.gif" /></center>

Voir [cet article](http://derrierelescartes.over-blog.com/article-13788300.html)

!SLIDE

# Les projections, l'éternel débat

<center><a href="http://sig974.free.fr/?p=733"><img src="images/projection.jpg" height="600" /></a></center>

<small>Crédits: [XKCD](https://xkcd.com/977/), traduit par Thierry JOLIVEAU et retouché par Bertrand BOUTEILLES</small>

!SLIDE

# Les codes EPSG

_**L'EPSG** – European Petroleum Survey Group –, un groupe créé en 1985 par Jean-Patrick Girbig alors avec ELF, a défini une liste des systèmes de coordonnées géoréférencées et leur a associés des codes pour les identifier._ (Wikipédia)

Il faut connaitre les codes EPSG pour pouvoir effectuer des conversions entre projections

!SLIDE

# Les projections les plus communes en France

* Projections Lambert
* Le RGF 93 et les coniques conformes
* Le WGS84
* Le Spherical Mercator

!SLIDE

# Projections "Lambert zone"

Projection historique. Une "globale", le "Lambert Zone II / Lambert 2 étendu" (EPSG:27572). Sinon, 4 zones pour plus de précision

<center><img src="images/Lambert_4Zones.png" height="300" /></center>

<small>Voir [cette application](http://dogeo.fr/_apps/projection/) et les [fiches du CERTU](http://www.certu-catalogue.fr/catalog/product/view/id/1614/?___SID=U&link=2141)</small>

!SLIDE

# Le RGF 93 et les coniques conformes

* RGF 93 pour couvrir la France métropolitaine (EPSG:2154)
* 9 coniques conformes (voir [page Wikipedia](https://fr.wikipedia.org/wiki/Projection_conique_conforme_de_Lambert) pour les codes EPSG)

<center><img src="images/France_9_Zones_de_Lambert_CC.png" height="300" /></center>

!SLIDE

# Le WGS84

* En simplifié, le système de votre GPS
* Il parle longitude/latitude

<center><img src="images/latlon.png" height="350" /></center>

!SLIDE

# Le Spherical Mercator

* Inventé par Google en assimilant la Terre <br> à une sphère (EPSG:900913 ou EPSG:3857)
* Déformation importante

<center><img src="images/deformation-spherical-mercator.png" height="300" /></center>

!SLIDE shout

# Convertir les formats et les projections des fichiers

!SLIDE

<br><br>
# But: transformer les données que nous récupérons en GeoJSON pour les utiliser dans Github

!SLIDE

<br>
# Quelques outils

* [GDAL/OGR](http://gdal.gloobe.org/install.html): outil pour changer formats et projections, en ligne de commande
* [OGRE](http://ogre.adc4gis.com): OGR via le Net
* [QGIS](http://qgis.org): outil bureautique assimilable à un "logiciel de traitement de texte" de la cartographie. Utilise aussi GDAL/OGR via une interface graphique
* [MapShaper](http://mapshaper.org): outil pour simplifier les données (moins long à charger)

!SLIDE

<br>
# Mise en pratique de QGIS avec un SHP

* Ouvrir un fichier shp
* Utiliser un fond de référence ([GEOFLA](http://professionnels.ign.fr/geofla))
* Activer la projection à la volée dans votre projet
* Ouvrir votre fichier à tester
* Vérifier la superposition
* Exporter en GeoJSON en WGS84 (EPSG:4326)

!SLIDE

# Mise en pratique de QGIS avec un fichier tabulaire

* Ouvrir un fichier csv avec X/Y ([RGC](http://professionnels.ign.fr/rgc) par exemple)
* Utiliser un fond de référence ([GEOFLA](http://professionnels.ign.fr/geofla))
* Activer la projection à la volée dans votre projet
* Ouvrir votre fichier à tester en "texte délimité"
* Choisir le système de projection
* Vérifier la superposition
* Exporter en GeoJSON en WGS84 (EPSG:4326)

!SLIDE

<br>
# Mise en pratique de Mapshaper pour la simplification de fichiers

* Prendre le fichier GeoJSON créé précédemment
* Charger ce fichier dans l'interface de [MapShaper](http://mapshaper.org)
* Tester la simplification
* Convertir en TopoJSON

!SLIDE shout

# Github, quezako?

!SLIDE

# Github:

* est un service basé sur Git
* stocke des fichiers
* permet de visualiser des données géographiques
* permet de publier des sites web sans avoir son propre hébergement
* est augmenté par un suivi des évolutions grâce à un système commentaires

!SLIDE

# Git, un gestionnaire de version décentralisé

Il permet de suivre l'évolution des fichiers textuels dans le temps.
Ce texte peut être du code, de la documentation ou de la donnée.
Similaire au "suivi des modifications" mais chaque modification est suivie séparément
<center><img src="images/Sw-comments-nested-rtf.png" height="300px"/></center>

!SLIDE

# Git en pratique

Il existe de nombreux tutoriels. <br>L'un des plus simples est [Try Git](https://try.github.io) (anglais)

Vous pouvez aussi allez voir:
* le livre en ligne [Pro Git](https://git-scm.com/book/fr/v2)
* le tutoriel [Gitimmersion.fr](http://gitimmersion.fr) (je suis le traducteur) 

!SLIDE

# Le processus quand on débute:

* On ajoute son nom utilisateur et son mail
* On initialise le dépôt sur sa machine
* On crée des fichiers
* On les ajoute comme devant faire partie des fichiers à gérer dans Git 
* On fait un "commit" pour indiquer qu'on veut garder une trace des ajouts
* On synchronise (optionel) avec un dépôt distant (Github dans ce cas) avec `push/pull`

!SLIDE

# Mise en pratique côté donnée (1/2)

* Créer un compte Github (gratuit)
* Pas d'usage de Git directement (à voir selon le niveau)
* Créer un dépôt appelé `github-maptime-nantes` en cochant `Initialize this repository with a README`

<center><img src="images/creation-nouveau-depot-github.png" height="300px"/></center>

!SLIDE

<br>
# Mise en pratique côté donnée (2/2)

* Allez sur la page avec [ce fichier](https://gist.github.com/ThomasG77/019eb4d29d1d9742ef41)
* Créer un nouveau fichier dans votre dépôt avec le même nom que le fichier vu précédemment
* Copier le contenu du [fichier "brut" (ou "raw")](https://gist.githubusercontent.com/ThomasG77/019eb4d29d1d9742ef41/raw/b50031969252bd27c1ca8ccb4b7d9b9c52feb6e7/villes-arrondissements-sup-100000habs-france.geojson)

**Qu'avez vous vu, constaté?**

!SLIDE

# Faire évoluer la donnée

* Allez sur le site en ligne http://geojson.io puis autoriser cette application à utiliser Github en allant sur `login` (texte cliquable en haut à droite)
* Allez sur `Open` puis `Github` puis choisir le dépôt créé pour accéder au fichier
* Changez la population de Nantes à 291604 puis sauvez (Ctrl + S quand vous avez le focus dans le bloc droit)
* Ajoutez la ville de la Roche sur Yon (-1.428653, 46.669352), changez ces attributs et sauvez

!SLIDE

<br>
# Voir les différences

* En théorie, il est possible de voir [les différences](https://github.com/blog/1772-diffable-more-customizable-maps) de manière visuelle
* En pratique, on utilise plutôt l'aperçu textuel quand on a compris la syntaxe du GeoJSON

!SLIDE

<br>
# Visualiser les données

Partiellement vu mais il faut noter la possibilité
* de [styler](https://help.github.com/articles/mapping-geojson-files-on-github/)
* de [grouper les points (clustering)](https://github.com/blog/1541-geojson-rendering-improvements)

!SLIDE

<br>
# Mise en pratique des styles

* Reprenez les exemples
* Amusez-vous soit à mettre à jour les fichiers existants, soit à créer de nouveaux fichiers en ajoutant des styles

!SLIDE

# Recommandations/limitations:

Taille des données < 10MB pour édition et aperçu

Données plus importantes (10MB - 100MB): Editer sur votre machine et synchroniser avec l'application Github ([pour mac](https://mac.github.com/) & [ou windows](https://windows.github.com/))

Données > 100MB: Pas vraiment adaptée pour être ici mais peuvent être stockés ainsi

!SLIDE

<br>
# L'hébergement de fichiers

En fait, si on utilise Github, on héberge sans coût des fichiers tant qu'on est prêt à les partager car Open Source. Ils sont bruts: un fichier HTML n'est pas interprété.

!SLIDE

<br>
# Publication de sites web

* via les [pages Github](https://pages.github.com)
* via des services tiers

!SLIDE

<br>
# Publications de site web

* [Données législatives](https://github.com/etalab/codes-juridiques-francais)
* [Détournement des données du Métro à Paris](https://github.com/vbarbaresi/MetroGit)
* [Portails SIG OpenData simple](https://cambridgegis.github.io/gisdata.html)
* Site web classique comme [MapTime Nantes](http://github.com/maptime/nantes)

!SLIDE

# Règles

* Pour un utilisateur, il y a un dépôt spécial avec le nom `<user>.github.io` qui devient `http://<user>.github.io` (branche master)
* Pour un dépôt `http://github.com/<user>/<depot>` devient `http://<user>.github.com/<depot>/` (branche gh-pages)
* Possibilité d'associer son propre domaine au lieu d'utiliser celui de Github 

!SLIDE

# Mise en pratique (1/2)

**Iframe pour encapsuler le code d'un site tiers comme UMap <br>si vous voulez une adresse "propre"**

    <html>
    <body>
    <iframe src="http://umap.openstreetmap.fr/fr/map/les-espaces-naturels-sensibles-en-ille-et-vilaine_25379#9/48.1835/-1.6232" width="800" height="500" frameborder="0">
      <p>Your browser does not support iframes.</p>
    </iframe>
    </body>
    </html>

!SLIDE

<br>
# Mise en pratique (2/2)

**Héberger son exemple sur les pages Github**

* Créez un fichier index.html comme pour [ce cas](https://gist.github.com/ThomasG77/c38e6b0ecfd014342aad)
* Changez la référence vers votre fichier GeoJSON 

!SLIDE

<br>
# Via des services tiers

* On peut utiliser des GIST qui sont comme des dépôts Github simples pour partager des "snippets" (bout de code) et on travaille conjointement avec [Bl.ocks.org](http://bl.ocks.org) pour l'aperçu
* On peut utiliser des sites tiers qui interprète les pages HTML, le CSS et le JavaScript en dehors des pages Github. C'est le cas de [RawGit](http://rawgit.org) ou [HtmlPreview](http://htmlpreview.github.io)

!SLIDE

<br>
# Commentaires pour discuter des changements

Fonctionnalité clairement non géographique néanmoins son intérêt est:

* de permettre de discuter la mise à jour de données,
* demander de nouveaux jeux de données: cela peut éviter d'avoir un forum.
* gérer des états d'avancement et des mots clés pour trier, définir les priorités de travail,...

!SLIDE

# Conclusion

Github amorce des changements pour <br>les utilisateurs comme les organisations

* Renversement des processus: de "top-down" à "bottom-up"
* Renforcement et facilitation de la collaboration
* Influence des méthodes agiles: classique "budget puis travail" devient "travail puis budget"

**Caractère disruptif**

L'aspect géo n'échappe pas à cette tendance

!SLIDE shout

# Questions

!SLIDE

# Crédits

Nous tenons spécialement à remercier [Tom MacWright](http://www.macwright.org) pour (Mapschool.io](http://mapschool.io/index.fr.html) et [Jérémy Garniaux](Jérémy Garniaux) pour la traduction (nous avons été le relecteur)