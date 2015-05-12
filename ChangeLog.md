### Version 1.32 (January 30th 2014) ###

  * Fixing in non-english version, if logfile option was checked the app may stopped.
  * "create a logfile" option is now unchecked by default

### Version 1.31 (January 26th 2014) ###
  * Addressing Geonames webservice access issue by using a username for the app
  * Added option for users to use their own Geonames username in the configuration file (highly recommended): https://code.google.com/p/gpicsync/wiki/GeonamesMetadata
  * Added Geonames information message if the user don't use its username
  * Upgraded embedded Exiftool to version 9.48
  * switched development code to Github https://github.com/notfrancois/GPicSync
  * windows exe now compiled with python 2.7 and latest libs

### Version 1.30 (August 6th 2012) ###
  * Windows [issue 117](https://code.google.com/p/gpicsync/issues/detail?id=117): if you selected Geonames option, geocoding could stop for non-ascii characters. Geonames are now unicode within GPicSync but are now translated to nearest ascii translation when Exiftool is called (see [issue 117](https://code.google.com/p/gpicsync/issues/detail?id=117) for raison why; waiting for two Python2 libs to update to Python3 for a full unicode command)
  * Windows [issue 116](https://code.google.com/p/gpicsync/issues/detail?id=116): moved the configuration file to %ALLUSERSPROFILE% location (typically ProgrammData folder on Win7) so non-admin multi-users  install can find the configuration (a pop-up appears now if it's not found at launch)
  * Updated Exiftool to version 8.99
  * Linux (from command-line/Source): Vsevolod Shorin contributed support for QR-code for time correction (you will need to install Zbar). Type "python gpicsync.py --help" for usage information.

### Version 1.29 (March 10th 2012) ###
  * added drop down timezone selection menu (thanks to Maciek Dems patch and the pytz lib)
  * upgraded Exiftool to version 8.81
  * added support for raw rw2 files
  * Windows build created now on Win Seven 64b Python 2.6 32b (many libs changes)

### Version 1.28 (April 13th 2009) ###

  * Fixed issue with Google Earth 5 where pictures appeared as blank in the new version of Google Earth
  * Updated third party software Exiftool to version 7.74
  * Included contributions from Tobias Domhan: iso naming of languages folders, fix to KMZ thumbnails, universal access to Google Earth on Linux

### Version 1.27 (febuary 8th 2009) ###

  * Added preliminary support for Geonames in IPTC
  * Will now write in EXIF/IPTC even if a minor warning is encountered by ExifTool
  * kml output files are now unicode
  * support for waypoints in GPX file (treated like trackpoints)

### Version 1.26 (april 4th 2008) ###

  * 1) Fixed a bug in the interpolation mode: in some cases some interpolated pictures wasn't geolocalized accurately (option especially useful if taking pictures while moving in a car or a plane).
  * 2) Improved/fixed GPX reading for certain files with "white spaces" in their latitude or longitude values
  * 3) Added support for negative altitude regions
  * 4) Added a GPicSync icon to the window icon

Thanks to:

  * Xavier Kaiser from Belgium for spotting the interpolation problem and providing detailed data for testing.
  * Peter Asprey for reporting and sending detailed feedback on points 2) and 3)

### Version 1.25 (28th January 2008) ###

- This version is just adding a dll which were missing in the installer (which came from GPSBabel) to use nemea .txt files with GPIcSync

### Version 1.24 (20th January 2008) ###

- Google Earth option: added the possibility to choose the picture's icons in the graphical interface (2 choices for now). By default the icons are now thumbnails of each picture with a slight rollover zoom. The second choice is the generic camera icon.

Big thanks to [Thomas Holz](http://blog.itsth.com/2007/12/20/googleearthtweaker-108/) for showing me this

- The latest version of Exiftool (7.13) from Phil Harvey is updated in the installer (see [history](http://www.sno.phy.queensu.ca/~phil/exiftool/history.html))

- Added RAF (Fujifilm RAW Format) to the [list of RAW formats supported](http://code.google.com/p/gpicsync/wiki/RawFormats)

### Version 1.23 (29th of October 2007) ###

Geonames bug fix (from version 1.22): when "adding geonames and geotadded" with "Geonames in EXIF keywords", the HTML summary was also added in IPTC caption. Also corrected a typo.
(Thanks to Friedrich Huebler for spoting this bug)

### Version 1.22 (27th of October 2007) ###

- Added Russian translation thanks to Evgeny Tyazhev (thanks to him!)

- Added more RAW file formats (see RawFormats)

- Possibility to customize your IPTC sumarize field from  the configuration file with variables LATITUDE, LONGITUDE, NEARBYPLACE, DISTANCETO, REGION, COUNTRY (see GeonamesMetadata)

- Updated EXIFTool to version 7.00 in backend


### Version 1.21 (16th October 2007) ###

Multi-day GPX Bug fix: in some conditions geocoding could take place if the GPX had  trackpoints more than 86400 seconds (24 hours) away from  the picture.

Thanks to Luka Logar for reporting the bug, spotting the faulty line of code + correction.

### Version 1.20 (13th October 2007) ###
Bug fixes release

- Fixed some syncing problems with data crossing UTC=0 (Ninjas in missions all around the globe across UTC=0 should have perfect sync now :) )

- Fixed the reading of some GPX files with particular tags

- Fixed the hang-on when a picture without date/time was provided (a warning information is now shown and GPicSync jumps to the next picture)

- You can now again use decimal value for the UTC Offset (expl "2.4")

Thanks very much to all the people who provided bug reports with their data.

The way the syncing and the GPX reading works has been completely redone. Hopefully the syncing should work now in all situations. In the process I had to remove the option "date must match" option for now (ie your camera should have been set to the correct date, if not use a tool like EXIFTool to change it)

If you experience any problem(s) thanks in advance for sending a report with some test data.


### Version 1.10 (July 22th 07) ###

Bug fix: In recent versions GPicSync stopped if it encountered a picture at a different date than the GPX with "dates must match". Same symptom if the GPX didn't have any trackpoint (now an information message appear).Thanks to Michal Ohrablo for reporting the problem.

### Version 1.09 (July 18th 07) ###

1) Fixed a bug affecting geocoding of some RAW pictures formats in versions 1.07/1.08: geocoding didn't happened or was very slow (Thanks to Michal Ohrablo for reporting the problem and for his DNG data).

2) Updated the German translation (thanks to Konrad Bauckmeier).

### Version 1.08 (July 17th 07) ###

1) Translations updated in Simplified and Traditional Chinese (thanks to Paul lu), Catalan and Spanish (thanks to Oriol Garrote), Portuguese (thanks to Manuel Antunes and Ricardo Silva) and Czech (thanks to "PolNjumen")

2) Particular GPX reading bug fix. If some spaces were present inside the double quotes values for latitude or longitude  (in the GPX ) the EXIF writing didn't work (in the picture). This is now fixed. Thanks to Alex.b for his data on this problem.


### Version 1.07 (July 12th 07) ###

1) Better elevation support for Google Earth KML especially for pictures taken during flight. Different mods can be selected directly form the interface (clamp to the ground, floating track and placemarks, extrude track).

(Thanks to Ricardo Silva for his feature request, suggestions and data.)

2) An image preview for JPGs is now displayed when geocoding or when using the EXIF reader tool. The graphical interface layout has been slightly changed.

3) Possibility to select between two Geonames mods from the interface where you can decide if you want to add the HTML summarize in the IPTC caption (useful for Flickr). Other mods like XMP and IPTC specific fields should come soon.

4) Portuguese is now available in the translations.

(Big thanks to Manuel Antunes and review from Ricardo Silva)

### Version 1.06 (July 2nd 07) ###

1) It is now also possible to manually write elevation (with latitude and longitude) in the EXIF writer tool (thanks "M@O" for the feature request).

2) Fixed the "GPX Inspector" tool which didn't show anymore data since version 1.05 (thanks "M@O" for the feature request).

3) Translation update in Dutch (thanks to Gijs van Elzakker) and French.

### Version 1.05.1 (June 26th 07) ###

1) Translation updates: simplified and traditional Chinese (thanks to Paul lu) and Catalan and Spanish (thanks to Oriol Garrote)

2) Bug fix: If a GPX file has elevation tags but without anything in them the KML "path" is now formed properly (thanks to Nicolas Moyroud for pointing to the problem)

### Version 1.05 (June 23th 07) ###

1) Translations

New Czech translation available thanks to [PolNjumen](http://polnjumen.wz.cz/)

The German version has been updated thanks to Konrad Bauckmeier

2) IPTC caption feature

When you check "add Geonames and geotagged" a summarize will also be written by default in the IPTC caption metadata of the picture. Website like Flickr will automatically add it to the description below the picture (if you allow metadata to be read in your profile).

The summarize looks like this:

```
Latitude/Longitude=(48.444433 , 8.015170 )
Near Geonames: Hinterohlsbach Baden-Württemberg Germany (Map link)

Eventual string (can be HTML) from the geoname_userdefine option in the configuration file.
```

The link "Map Link" will open the geonames wiki/map at the position of the picture.

If you don't want this feature when you use geonames or geotagged go in the configuration file and set geoname\_caption=False

Thanks to Marek for [the feature request](http://groups.google.com/group/gpicsync/browse_thread/thread/7a2b99b9ba82812c).

3) Multiple tracklogs selection

You can now select multiple tracklogs for geocoding (use the "Ctrl" button to select more than one track).

Thanks to Marcus Schmidke and ChristophMaggioni for the feature request.

### Version 1.04 (June 18th) ###

1) EXIF Writer tool

You can now manually insert latitude and longitude in the pictures EXIF with the new "EXIF Writer" tool in the tools menu. You must use the decimal degrees format (whatever the precision you give) and you can apply your coordinates to one or more pictures (use the "Ctrl" button to select more than one picture). For example the statue of Liberty would be latitude=40.6894 and longitude=-74.0447

(Thanks to Konrad Bauckmeier for the feature request)

2) Translations

GPicSync is now available in 10 languages thank to the translation in Dutch from [Gijs van Elzakker](http://www.vanelzakker.nl/). Thanks to him!

Updated translation in Spanish and Catalan (thanks to Oriol Garrote) and French.

### Version 1.03 (June 10th) ###

This is a translation update.

GPicSync is now available in 9 languages thanks to the addition of Polish by ([Dominik Wójcik](http://www.biegacze.pl/)).
Updated also the French translation.

Thanks to him and all the translators!
http://code.google.com/p/gpicsync/wiki/Translations

### Version 1.02 (June 9th) ###

1) New translations

Added Spanish and Catalan by Oriol Garrote ([skimountaineering.org](http://skimountaineering.org/)).Thanks to him!

2) Geonames fine tune

In the configuration file you can now decide of the Geonames you want to search for (nearest place, region, country, summary).
Also you can add a generic message with the geonames (your name and/or copyright for example) with the "geoname\_userdefine" parameter in the configuration file.

(Thanks Blomberg and davidoh69 for the feature request)

3) New configuration file and "Quit and save settings" button

The configuration file is better organized and commented.
When the application start is will search first for this parameters if they exist.
When you close GPicSync you have two choices:
- "Quit" button as usual
- new "Quit and save settings" button

In the latter case the configuration will be rewritten with all the settings of the current session (UTC Offset, etc.).
In particular when you will use next time the "Pictures folder" it will prompt at the latest directory you've been too.

Warning: If you make some changes to the configuration file while GPicSync is running you should quit GPicSync with the "Quit" button (to avoid to overwrite your changes).

(Thanks davidoh69, Terry and probably others for the feature request)

4) Backup folder name

By default a backup of your original pictures was made in an 'originals-backup' folder in your pictures folder.
A suffix is now  added with the name of your pictures folder ('originals-backup-yourpicturesfolder').

This is to provide a unique name and a better search of your pictures in your hard-disk.

(Thanks Terry for the feature request)

5) Fixed the Offset problem for Google Earth for "with timeStamp" option

I've now added the offset information in the time stamps of the placemarks in the kml (so the time you'll see will directly be the time of your pictures).

(Thanks Pawel Nabe for explaining me how this time format worked)


6) Google Earth kml improvements

- Like for the web version the placemarks are now gathered in a "Photos" folder.
- The track is now in one chuck (it is cut in 500 points in the Google Maps version to be sure it will display with Google Maps).

(Thanks Peter and Terry for the feature requests)

### Version 1.01 (June 5th) ###

1) GPSbabel integration and NMEA support

GPicSync integrate now the great GPSbabel tool in his back-end. The first new format to be supported is NMEA. Just select your GPS file and select the NMEA file filter (a gpx file will be created in your picture folder and will be automatically used when you'll launch the geocoding process).

(thanks "bazarophile" and Paul lu for the feature request and data)


2) Configuration file

The configuration file is now in the user home folder (for example in windows: "C:\Documents and Settings\username\gpicsync.conf").
On GPicSync (Windows) you can now access and  modify this file directly from GPicSync: "Options">"Configuration File" will open the file in notepad (if you make some modifications you must save and restart GPicSync for the changes to take effect).

(thanks H-J Fett for making me aware of the problem and the feature request)

3) Windows file modification date

The file modification date is now unchanged by a GPicSync geocoding. The idea is that you can still directly see the date you took the photo in your operating system file browser (without the need to look at the EXIF). I'll probably soon add the possibility to change this as an option in the configuration file.

(thanks Paul lu for the feature request)

4) Backup

If you re-use the backup option it will first check if the picture has been saved a first time (is so it will keep the first backup)

5) EXIF Tool reader

Added the full name and path of the file being inspected as an information in the main text window.

(thanks Terry for the feature request)



### Version 1.00 (3rd of june 2007) ###

1) Google Earth "with TimeStamp" option

There is a new option for the Google Earth file called "with TimeStamp" directly in the interface.

Google Earth will show a time sliders (you can modify the width with your mouse) and pictures will appear only if they are in the time frame.

You can use the play button (to the right of the slider) to see your pictures appearing as time pass and you can change the time settings by clicking on the watch (on the left of the slider).

Warning: If your camera was set to the local time you will have to click on "UTC" in the time setting (otherwise Google Earth will add a second time the offset). I'll see if I can do something about that in the next version.

Thanks mlos100 for this cool feature request.

2) GPicSync is now translated in traditional and [simplified Chinese](http://www.flickr.com/photo_zoom.gne?id=527820388&size=o)  ("options">"language" ).

Huge thanks to Paul lu from [digital.xy.hk](http://digital.xy.hk/) for this great  contribution :)

3) Beginning to correct few typos (thanks marc and terry)

### Version 0.99 (may 25 2007) ###

  * German translation added (see the [translation page](http://code.google.com/p/gpicsync/wiki/Translations))

(Thanks to Michael, alias anwi in the GPicSync group for the main translation and the review and help from Konrad Bauckmeier )

  * [Automatically associate audio or video files to geolocalized pictures in Google Earth and Google Maps](http://code.google.com/p/gpicsync/wiki/AddAudioVideoFiles).

(Thanks to David Veeneman for [his feature request](http://groups.google.com/group/gpicsync/browse_thread/thread/a5a5d08bffa33b97))

If you encounter any problem thanks to report it.

### Version 0.98-2 (may 22 2007) ###

This version address [issue 22](https://code.google.com/p/gpicsync/issues/detail?id=22) "No match found when UTC time crosses 0000 hrs" for negative UTC offset and with "dates must check" checked.It most likely affected US West coast users.

If you are in this case, please upgrade to this version and don't hesitate to give me some feedback if you encounter any problem.

Thanks to davidoh69 for reporting the issue.

### Version 0.98-1 (may 21 2007) ###

Fixed a bug in the KML which wasn't well formed if the GPS file didn't have any elevation data. If you are in this case, please upgrade to this version and don't hesitate to give me some feedback if you encounter any problem.

Thanks to "Mr. Comentand" for bringing some data showing the issue on the [GPicSync Google Group](http://groups.google.com/group/gpicsync).

### Version 0.98 (may 20 2007) ###

- Apart from English and French, GPicSync is now available in Italian (menu "Options">"Language").

(BIG THANKS to bartman from [x50v.it](http://x50v.it/) for this great translation !)

- Fixed a bug when "Interpolation" is checked and when the timestamp of a picture is not in the time interval of the tracklog.

(Thanks to Graham from UK for reporting the problem on the google group!)

- Fixed a problem when retrieving some geonames. If one geoname doesn't exist it is ignored and the others are used now (had a problem for some UK data where the region metadata wasn't available in geonames.org database).

### Version 0.97 (may 17 2007) ###

- For the "backup" option, a directory "originals\_backup" is now
created in the pictures folder (backup pictures keeps their original
names).

- GPicSync remembers now the last picture folder selected inside a session

- A configuration file is now present where you can set main
preferences as default (like the UTCOffset, Google Map base URL, etc).
It's name is "gpicsync.conf" and it is located in the installation
folder (normally "program files/GPicSync" on Windows) .
You can edit it with an editor (like notepad for example) and change
default values here (when GPicSync starts it reads this configuration
file).I'll add a graphical interface from GPicSync in a future
version.

- The local time correction tool remembers now the last correction in
the session and show a status message in the main text window. The
"apply correction" button leave now the window visible, to leave or
hide it, hit the new "quit" button. This can be useful if you have old
data from which you don't know the time difference  and you're trying
find.

Thanks to Blomberg, leszekp, anwi, marc and davidoh69 for feature
requests and feedback.
If you encounter any problem thanks to report it.

### Version 0.96-alpha (may 13 2007) ###

This version address an issue when the option "dates must match" is used with early morning or late evenings photos in regions with an important UTC Offset. (  [1](http://code.google.com/p/gpicsync/issues/detail?id=6) , [2](http://groups.google.com/group/gpicsync/browse_thread/thread/fd7fcd5e57cb1928) ).

It is labeled "alpha" because many changes has been done in the synchronization process and I didn't have time to test it on lots of data. If you encounter any problem thanks to let me know!

Thanks to "peterdcrees" and leszekp for reporting this issue.

### Version 0.95 (may 12 2007) ###

  * Elevation data (altitude)
    * add elevation data in the EXIF header if these informations are present in the gpx file
    * You can check this elevation data with Tools > GPX Inspector and Tools > EXIF reader (all metadata)
  * Fixed a bug when the app wasn't closed with the "Quit" button (the window was reloading)

Thanks to "ChristophMaggioni" and Two Lenses for the altitude feature request.
Thanks to Jaeshin Soh for reporting the closing app problem.

### Version 0.94 (may 8 2007) ###

[New releases must be downloaded on Sourceforge.](http://sourceforge.net/project/showfiles.php?group_id=191804)
The project 100 Mo quota on code.google is reached and I discovered it is forbidden to delete old releases :(

1) Interpolation option

The interface has now an "interpolation" checkbox (unchecked by default).
It gives more accurate results if:

  * you take pictures while moving in a car or a plane
  * you have a GPS setting with an important duration between each GPS trackpoint record

(Thanks to T-Bon3 and harry.gps for the feature requests)

2) Translations

GPicSync is now internationalized and can be easily translated.
Version 0.94 supports English and French and Italian should come soon.


When you launch GPicSync it try to find an existing translation based on the language of your operating system. You can also change the language in the menu "Options">"Language".

If you wish to translate GPicSync in your own language  please let me know so I can guide you :)

Basically it is one file to translate (filling the double quotes) in:
http://gpicsync.googlecode.com/svn/trunk/gpicsync-GUI.pot

3) UTC Offset is now a floating point number (not an integer anymore for our friends of South Australia with special time zones)

(Thanks to harry.gps for the feature request)

4) Fixed an inversion issue in the "Local Time Correction" option.

### Version 0.93 (may 5 2007) ###

Better Google Map export:

  * creates now thumbnails in a "thumbs" folder
  * cut big tracks into smaller parts (500 points maximum each) to be sure it will display well on Google Maps (with a "Track folder" in the doc-web.kml)
  * photos are now in a "Photos folder" in the doc-web.kml

Thanks to "johnlevandowski" for the feature request for thumbnails in the issue section.

### Version 0.92 (may 1st 2007) ###

  * [Google Maps export with clikable photos + track log](GoogleMapsExport.md) (thanks to Marc Nozell for his feature request)
  * geocode RAW photos. Tested with CR2 files but should work with Canon (CRW, CR2), Nikon (NEF), Pentax (PEF), Samsung (PEF), Sony (SR2, ARW), Fuji (RAF)(thanks to chris.nursey,  rb799, bmedicke and holyCow for the feature request and RAW samples)
  * kml: default icon is now a camera instead of a yellow pin (thanks to gpspassion for the suggestion)
  * Windows: new entries in start menu with 'uninstaller', 'GPicSync website' and 'Google Group' (thanks T-Bon3 for the uninstall feature request)
  * Linux: GPicSync GUI doesn't wait anymore that the user shut down Google Earth

Know issues for Google Maps export: if you have lots of pictures and your gpx is big Google Maps may not display the track-log and/or some pictures.


### Version 0.91 (april 24th 2007) ###

Geocoded pictures visualized in Google Earth now keep their initial size ratio (whatever their original width and height). Pictures will appear with a a maximal width of 800 pixels (or 600 pixels for height if the picture was taller than wider).
Other improvements for the KML will come soon in future versions. Thanks to Jerome for mentioning the problem in the GPicSync group.

Fixed a backup bug (when backup was uncheck and geonames was check a backup occurred anyway).

### Version 0.90 (april 19th 2007) ###

You can now decide to automatically add "[geonames](http://www.geonames.org/)" and "geotagged" to the metada of your photos (check "add geonames and geotags"  in the interface before geocoding). GPicSync must have an internet connection to retrieve the geonames.

  * geonames: country, region, nearest place with distance (in Km)
  * goetagged: "geotagged", "geo:lat=48.167358", "geo:lon=7.294641"

When you upload to Flickr the tags will appear in the tags section of the photos (zoom in the [example](http://www.flickr.com/photos/frenchy/465037997/)).

Known problems:
  * you mustn't allow the Flickr Uloadr tool to resize your pictures before uploading (your geonames/geotags won't be kept, If needed you could resize them before with Picasa for example)
  * if you were in places that don't use the English alphabet these characters may not appear well (this should be fixed soon).

Thanks to Jose Oliver for his feature request in the [GPicSync group](http://groups.google.com/group/gpicsync).

### Version 0.85 (april 10th 2007) ###

A bug release to address Issue N°3 and 4 (writing in EXIF header doesn't work properly with pictures taken with certain camera brands, at least SONY Cybershot) and Longitude didn't write for some users.

If you had problems before try this new release. If it still doesn't work for you please send me one original non geocoded picture taken by your camera (whatever it is). See also the Google Group to stay informed:
http://groups.google.com/group/gpicsync

Thanks in advance for your feedback !

### Version 0.84 (april 9th 2007) ###

Minor changes:

  * Fixed a freeze of few seconds (graphical interface) when GPicSync was processing a big GPX file on relatively "slow" computers.
  * Added a message before the track log is added to the kml file (in case its a big GPX file which takes time to process).

### Version 0.83 (april 9th 2007) ###

Added two feature requests:

  * An option to geocode only the photos where the time difference (between picture time and nearest track  point) is below a given time range (by default 120 seconds).
  * An option to decide if you need or not a back-up of your pictures before processing (by default a backup is made).


### Version 0.81.1 (april 5th 2007) ###

  * Fixed a sign problem from version 0.81 when the user unchecks "dates must match" (for western longitudes or southern latitudes)

### Version 0.81 (april 4th 2007) ###

  * Changed the way the  kml file + synchronization is produced (gained around a third of the previous time)
  * Fixed in the doc.kml the tag "name" which appeared twice inside each placemark (thanks Peter)

### Version 0.8 ###

  * Added the tracklog inside the kml file => visible in Google Earth

### Version 0.75 ###
  * relative address in kml + kmz export tool

### Version 0.50 ###

  * can sync now whatever the dates in the gpx files or the pictures folder "dates must match" (is now default option)
  * added a stop and  clear button

### Version 0.43 (March 13th) ###

Version 0.43 reads now all the valid track points and don't search anymore for 

&lt;trackseg&gt;

 in the file. This is useful if you switch off and On your GPS during your trek : all valid points with time will be processed.