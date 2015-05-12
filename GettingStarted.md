# Getting started with GPicSync #

  * 1) Set your GPS receiver and your camera
  * 2) Go outside and shoot
  * 3) Come back home and sync
  * 4) Enjoy your geolocalized pictures
  * 5) Configuration file and optional tools

### 1) Set your GPSr and camera ###

Two possibilities here.

**a) Universal way**

If you didn't change its setting, your GPSr records the track log with the GMT time (Greenwich Meridian Time) also know as UTC (Universal Time Co-ordinated).

Set the time of your camera to GMT. You can see the actual GMT time at the bottom of this webpage (be precise at the second level):

http://wwp.greenwichmeantime.com/

Setting your camera to GMT is practical since you won't have problems for summer/winter time or when you travel through time zones. Also set the camera date if necessary.

**b) Local way**

Set the local time of the camera precisely to the same local time indicated by the GPSr. Also set the camera date if necessary.

### 2) Go outside and shoot ###
Take your GPSr with you and make sure that it is recording a track log. Keep your GPSr ON during all the time you take pictures.

### 3) Come back home and sync ###

Put the  pictures you want to geolocalize in a folder.
With the software of your choice (for example [EasyGPS](http://www.easygps.com/) on Windows) retrieve the track log as a .gpx file (a [list of GPX capable software](http://www.topografix.com/gpx_resources.asp)). Put the .gpx file preferably in the folder containing the pictures. You can also use a NMEA track (give a .txt extension) instead of the GPX file.

Install [GPicSync from Sourceforge](http://sourceforge.net/project/showfiles.php?group_id=191804):
  * download the .exe installer on Windows.
  * download the tar.gz file on Linux if available (or directly make a SVN checkouk and read the readme.txt)

Launch GPicSync, then:
  * select the pictures folder
  * select the .gpx or NMEA file
  * depending of the way you've set your camera and GPSr indicate the UTC Offset:
    * +1 in France, 0 in the UK, -8 for PST, -5 for EST,etc, You may need to add an hour for summer local time depending of your country policy
    * 0 if your camera is at GMT time
  * if you want to add geonames and geotags metada check "add geonames and geotags" but be  sure to have an internet connection
  * hit the  "synchronize !" button

You should now see a line per picture with the file name found and the localization that has been written in the EXIF part of the picture (each geolocalization takes 1 to 3 seconds to process).

There's also an indication of the time difference between the nearest trackpoint and the picture (you should see a few seconds difference). If this difference is important (above a hundred seconds) there's probably something wrong in your time setting. In particular check that you've indicated the right UTC offset (and maybe add an hour if you are in a summer daylight saving zone).

By default GPicSync doesn't Geocode photos if the time difference is above 300 seconds but you can adjust this threshold in the interface ("Geocode only if time difference is less than (seconds)="). This could be useful on some GPS if you make a pause and the GPS stops recording because you don't move anymore.

You can directly verify your photos in Google Earth (just click the "View in Google Eath" button at the end of the process).

By default a backup of you pictures is made in your pictures folder.

If there's no location showing:
  * use "Tools"->"GPX Inspector" to quickly see the data GPicSync finds in it.
  * use "Tools"->"EXIF Reader" and check if your photos contain a Date/Time Original   field like (Date/Time Original : 2007:04:06 14:41:02). Some image processing software erase metadata (Picasa for example keeps the metadata)

If you forgot to set the local time for your camera you can take this into account in "Options" -> "Locale time correction".


### 4) Use your geolocalized pictures ###

You can directly view your pictures and track log in Google Earth by clicking on "View in Google Earth" button at the end of synchronization. A doc.kml file has been created in your pictures folder so you can also directly launch Google Earth by double clicking on it.

You may want to export your geolocalized pictures in a single kmz file for sharing or to put on a server ("Tools"->"KMZ Generator").

You can also use your pictures with any software or website which can read the latitude/longitude informations. For example:

#### a) Flickr ####

In the setting of your account you must first authorize the use of this information ("Your Account">"Privacy & Permissions">"Import EXIF location data: Yes").

When you upload your pictures you will see a "map" link near each picture to open Yahoo Maps which will point to the location.

If you've checked "add geonames and geotags" your pictures will also have the following keywords metadata:

  * geonames: country, region, nearest place with distance (in Km)
  * goetags: "geotagged", "geo:lat=48.167358", "geo:lon=7.294641"...

When you upload your pictures to Flickr the tags will appear in the tags section of the photo.

You mustn't allow Flickr Uloadr tool to resize your pictures before uploading (your geonames/geotags won't be kept, If needed you could resize them before with Picasa for example).

By default there is also an HTML summarize which is written in the IPTC caption of the picture. The summarize shows the latitude/longitude and the nearest Geoname and country with a link to the Geonames map. Flickr will show the summarize in the description of your picture. If you don't want this use change the geonames options in the interface.

If you prefer to see your Flickr pictures on google maps you can use this neat [geocoding bookmarklet](http://www.flickr.com/groups/geotagging/discuss/72157594165549916/) which will point to the location in [loc.alize.us webiste](http://loc.alize.us/) which uses google maps.

#### b) Picasa / Google Earth ####

If you select your pictures with picasa you can ask to show them on Google Earth (in Picasa : something like "Tools">"Geolocalize">"Display in Google Earth").

#### c) Google Maps ####

To create your own Google Maps check [this tutorial](http://code.google.com/p/gpicsync/wiki/GoogleMapsExport).

#### d) Audio and Video localization ####

You can also automatically associate audio or video files to geolocalized pictures in Google Earth and Google Maps (a link will appear below the picture).

For this you must put your audio or video file in your pictures directory and give them the same name as the picture.

### 5) Configuration file and optional tools ###

A configuration file is available to set main preferences as default (like the UTCOffset, Google Map base URL, Geonames, etc). You can edit it and save it from "Options" -> "Configuration file". The "Quit and save settings" button of GPicSync will also write in this file.

A certain number of tools are available in "Tools" -> "Options".

WARNING:
GPicSync is beta software. Please report any bug or problem and remember there's no guarantee : don't use it for critical missions and always check on maps if the results are correct.