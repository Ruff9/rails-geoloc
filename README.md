#Objectifs
* Tracer une ligne entre deux points situés sur une carte.
* Ce travail se base sur [le travail d'Emilien sur la géolocalisation](https://github.com/simplonco/rails-geoloc)

#Methodo
Geocoder fourni les coordonnées (Latitude Longitude) d'un point.
Nous allons récupérer les coordonnées de plusieurs points au travers d'un script.

L'outil principal ici est la [librairie javascript Leaflet](http://leafletjs.com/reference.html), qui contient notament ces outils :
* Path
* Polyline
* Multipolyline

#Pas à pas
 * Tracer une ligne entre 2 points
Leaflet donne dans sa documentatin l'exemple suivant : 
`Usage example

// create a red polyline from an arrays of LatLng points
var polyline = L.polyline(latlngs, {color: 'red'}).addTo(map);`

Il s'agit ici d'inclure les coordonnées renseignées dans le formulaire dans cette ligne de code. 
Dans l'application rails-geoloc, le partial _maps_script.html.erb compile les coordonnées des points dans une variable nommée `bounds`.
Le script devient donc
`var polyline = L.polyline(bounds, {color: 'red'}).addTo(map);`

Par soucis de formalisme, mettre cela dans un partial nommé ici `_line_script.html.erb`


TODO

Ecrire un script qui va rechercher les données brutes (`raw`) des points (appelées locations dans le model).

``` <script>
  var locations = <%= raw @itinerary.locations.to_json %>
</script>

* Tracer 2 lignes entre 3 points

* Modifier l'ordre d'affichage des points et tracer selon l'affichage
