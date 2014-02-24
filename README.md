#Objectifs
*Tracer une ligne entre deux points situés sur une carte.
*Ce travail se base sur [le travail d'Emilien sur la géolocalisation](https://github.com/simplonco/rails-geoloc)

#Methodo
Geocoder fourni les coordonnées (Latitude Longitude) d'un point.
Nous allons récupérer les coordonnées de plusieurs points au travers d'un script.

L'outils principal ici est la [librairie javascript Leaflet](http://leafletjs.com/reference.html), qui contient notament ces outils :
* Path
* Polyline
* Multipolyline

#Pas à pas

Ecrire un script qui va recherhcer les données brutes (`raw`) des points (appelées locations dans le model).

```<script>
  var locations = <%= raw @itinerary.locations.to_json %>
</script>



