GPicSync can automatically retrieve "geonames" from [www.geonames.org](http://www.geonames.org) and add them to the EXIF metadata and a customized summary to the IPTC section.

Many software will read those metadata and  Flickr will use them to automatically  to generate tags or description from the picture (IPTC summary).

To use the default Geonames settings check "add geonames and geotagged" in the interface and select either "Geonames in EXIF keywords + HTML sumarize in IPTC caption" or "Geonames in Keywords".

For better Geonames disponibility it is highly recommended to get your own free username account at http://www.geonames.org.

Your username can then be set in Menu option > configuration file > geonames\_username=YourUserName. Save in Notepad, then 'quit' gpicsync (not 'quit and save settings') and reload.

You can then test if geonames works for you by trying this URL and changing "demo" by the name of your login:
http://api.geonames.org/postalCodeSearch?postalcode=9011&maxRows=10&username=demo

More informations for the Geonames webservice can be find at http://www.geonames.org/export/"


**Customizing the geonames via the configuration file**

You can further customize the geonames by editing and saving your configuration file:

- in GPicSync, "Options"->"Configuration file"

- edit, save your modification and quit your text editor

- click on the "quit" button of GPicSync

- reload GPicSync for the modification to take effect

This is the relevant section in the configuration file:

```
#Add geonames and geotagged in EXIF by default (True or False) and select the ones you want
geonamestags=True
geoname_nearbyplace=True
geoname_region=True
geoname_country=True
geoname_summary=True
geoname_userdefine=

#Add summary in IPTC with the following variables (if you use quotes escape them: \"  ):
#{LATITUDE} {LONGITUDE} {DISTANCETO} {NEARBYPLACE} {REGION} {COUNTRY}
geoname_caption=True
geoname_IPTCsummary=Taken at Latitude/Longitude:{LATITUDE}/{LONGITUDE} Near {NEARBYPLACE} {REGION} {COUNTRY} <a href=\"http://www.geonames.org/maps/google_{LATITUDE}_{LONGITUDE}.html\"> (Map link)</a>
```