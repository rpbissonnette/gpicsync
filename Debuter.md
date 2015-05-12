Pour une version plus complète et la plus à jour du site consulter [la version anglaise](http://code.google.com/p/gpicsync/).

La fiche de description du logiciel en français est [disponible ici](FrenchPresentation.md).

# Débuter avec GPicSync #

  * 1) Initialiser votre GPS
  * 2) Initialiser votre APN (Appareil Photo Numérique)
  * 3) Faites votre ballade et prenez des photos !
  * 4) De retour, synchronisez le tout avec GPicSync
  * 5) Visualisez et partagez vos photos géolocaliseés
  * 6) Utilisation avancée (fichier de configuration et outils optionnels)


![![](http://farm2.static.flickr.com/1266/840388084_f8c9c29586.jpg)](http://farm2.static.flickr.com/1266/840388084_877191980b_o.jpg)

### 1) Initialisez votre GPS ###
Si ce n'est pas déjà le cas mettez votre GPS à l'heure locale du pays.

### 2)  Initialisez votre APN ###
Rentrez la même heure dans votre APN que celle indiquée par votre GPS (à la seconde près). N'oubliez pas de régler la date si nécessaire.

### 3) Faites votre ballade et prenez des photos ! ###
Prenez votre GPS avec vous et assurez vous qu'il enregistre bien votre parcours ("track log" ON). Laissez le GPS allumé durant toute la ballade et prenez vos photos comme d'habitude.

### 4) De retour, synchronisez le tout avec GPicSync ###

Mettez les photos que vous voulez géolocaliser dans un dossier.
Avec un logiciel de votre choix (par exemple le freeware [EasyGPS](http://www.easygps.com/)) récupérez le "track log" et enregistrez le sous la forme d'un fichier ".gpx". Mettez ce fichier .gpx dans le dossier contenant les photos par exemple. Vous pouvez à la place utiliser un parcours NMEA (extension .txt).

Téléchargez GPicSync [depuis Sourceforge](http://sourceforge.net/project/showfiles.php?group_id=191804):
  * Windows: télécharger le .exe
  * Linux: Faites directement un [SVN Checkout](http://code.google.com/p/gpicsync/source)et lisez le fichier readme.txt
  * pour une utilisation en français allez dans "options">"langages" (sélectionnez "français" et relancer le logiciel)
  * sélectionnez le dossier contenant vos photos
  * sélectionnez votre [fichier .gpx](AideGpx.md) ou NMEA
  * indiquez l'UTC Offset, c'est à dire le fuseau horaire (+1 in France heure d'hivers et +2 heure d'été)
  * lancez la synchronisation

Si tout se passe bien vous verrez une ligne d'information (par photo trouvée) avec la localisation géographique qui vient d'être inscrite dans l'entête de la photo.

L'écart temporel entre votre photo et le point du "track log" le plus proche est indiqué. Au delà d'une centaine de seconde il y a probablement une erreur dans votre timing. En particulier vérifiez que vous indiquez bien le bon "UTC Offset"(fuseau horaire = 1 pour la France et 2 à l'heure d'été).

Par défaut GPicSync ne geocode pas les photos dont la différence de temps est supérieure à 300 secondes. Vous pouvez ajuster cette limite directement dans l'interface ("Géocode seulement si l'écart au point le plus proche est inférieur à(seconds)="); Ceci est utile pour certains GPS qui n'enregistrent plus de points si vous ne bougez plus pendant une certaine durée.

Vous pouvez directement en fin de synchronisation vérifier  vos photos et votre parcours dans Google Earth (en cliquant sur le bouton "Voir dans Google Eath" à l'invite).

Vous avez aussi la possibilité de créer un rapport des opérations effectuées dans le dossier des photos en cochant "créer un fichier de log". A noter que pour éviter tout problème éventuel une copie de chaque photo est réalisée par défaut.

Si vous souhaitez ajoutez des métadonnées supplémentaires (pays, région, endroit le plus poche, données "geotagged", etc) cochez "ajout geonames et geotagged" avant de lancer la geolocalisation (il vous faudra une connexion internet pour que le logiciel puisse récupérer ces informations sur le site geonames.org). Plusieurs modes Geonames sont disponibles directement depuis l'interface.

Si les informations de localisation n'apparaissent pas vérifiez:
  * votre fichier GPX (utilisez "Tools"->"GPX Inspector" pour voir les données que voit GPicSync dans le fichier)
  * les métadonnées de vos photos (utilisez "Tools"->"EXIF Reader" et vérifez que 'Date/Time Original est bien présent. Exemple: "Date/Time Original : 2007:04:06 14:41:02")

Si vous avez oublié de régler l'heure locale de vos appareils vous pourrez indiquer les informations nécessaires dans le menu "option" > "local time correction".

Si la date de votre appareil photo était fausse décochez "vérifier le dates" avant de synchroniser.

### 5) Utiliser vos photos géolocaliseés ###

Vous pouvez maintenant utiliser vos photos avec n'importe quel logiciel ou site web capable de lire les méta-données de géolocalisation.

Vous pouvez directement visualiser le résultat dans Google Earth en cliquant sur "Voir dans Google Earth (un fichier doc.kml a été créer dans votre dossier photo sur lequel vous pouvez aussi double-cliquer pour lancer la visualisation).

Vous pouvez exporter vos photos et le parcours sous la forme d'une archive unique KMZ à diffuser : "Outils" > "Générateur KMZ"


#### a) Flickr ####

Dans les options de votre compte vous devez autoriser Flickr à lire les informations de géolocalisation ("Your Account">"Privacy & Permissions">"Import EXIF location data: Yes").

Quand vous uploadez vos photos vous verrez ensuite un lien "map" près de chaque photo qui montre la photo sur les cartes Yahoo Maps.

Si vous avez coché l'option "geonames et geotagged" vos photos auront des métadonnées supplémentaires (pays, région, endroit le plus proche, etc) qui apparaîtront directement comme des tags dans Flickr.

Par défaut un résumé est également inscrit dans la photo (IPTC caption) et apparaîtra dans la description de la photo en ligne.

Si vous téléchargez vos photos avec l'oultil Uloadr de Flickr attention à ne pas lui permettre de redimensionner les photos pour ne pas perdre ces métadonnées.

Si vous préférez Google maps (plus précises en France que Yahoo maps) vous pouvez utilisez ce [geocoding bookmarklet](http://www.flickr.com/groups/geotagging/discuss/72157594165549916/) qui utilise le site [loc.alize.us](http://loc.alize.us/) lui-même basé sur les cartes Google et les photos Flickr.


#### b) Picassa / Google Earth ####

Si vous visualisez vos photos avec Picasa allez dans le  menu "Outils">"Géolocaliser">"Afficher dans Google Earth".

Voir aussi [ce tutoriel](http://code.google.com/p/gpicsync/wiki/KMZavecPicassaEtGE) pour créer un fichier kmz légé avec le parcours GPS pour le distribuer facilement sur le web ou par mail.

#### c) Google Maps ####

Vous pouvez créer un export Google Maps à placer ensuite sur un serveur. Cochez "Google Maps export" et indiquez l'URL du dossier photo sur le serveur. Transférez ensuite votre dossier photo par FTP.
Un tutoriel en anglais est [disponible ici](GoogleMapsExport.md).

### 6) Utilisation avancée, fichier de configuration et outils optionnels ###

De nombreuses autres possibilités sont disponibles. Par exemple:

  * des modes de visualisation spécifique pour l'aviation (voir boîte option).
  * des modes pour l'exploration spation-temporelle avec Google Earth (cocher "with TimeStamp") et jouez avec la barre de navigation temporelle qui apparaîtra dans Google Earth.
  * un fichier de configuration (menu "Options"->"Fichier de configuration") permet de régler finement certains paramètres comme les geonames et de conserver ses préférences.
  * une collection de petits outils pratiques est disponible dans le menu "Outils"

ATTENTION:

Plus d'informations sont disponibles dans la [version anglaise du site](http://code.google.com/p/gpicsync/).

GPicSync n'offre aucune garantie donc ne l'utilisez pas pour des missions "critiques" en territoire ennemi et vérifiez toujours les résultats avec des cartes récentes.:)