![![](http://farm1.static.flickr.com/171/478403489_9d9dfb435d.jpg)](http://farm1.static.flickr.com/171/478403489_7621c88dd2_o.jpg)

### Goals ###

Create a Google Map with clickable pictures and track (enlarge the screenshot to better understand the main steps) .

Example:

[Bike ride in the black forest, germany, 19th of may 07](http://local.google.com/maps?f=q&hl=en&q=http%3A%2F%2Ffrancois.schnell.free.fr%2Fgeo%2F19mai07%2Fdoc-web.kml&ie=UTF8&ll=48.43649,8.051605&spn=0.089061,0.233459&t=h&z=12&om=1)

[29th of april bike ride](http://maps.google.com/maps?f=q&hl=en&q=http%3A%2F%2Ffrancois.schnell.free.fr%2Fgeo%2F29Apr07%2Fdoc-web.kml&ie=UTF8&ll=48.520925,8.146706&spn=0.102329,0.233459&t=h&z=12&om=1)

[Stroll around a water fall in Germany,6 may 07](http://maps.google.com/maps?f=q&hl=en&q=http%3A%2F%2Ffrancois.schnell.free.fr%2Fgeo%2F6may07%2Fdoc-web.kml&ie=UTF8&ll=48.533629,8.192282&spn=0.011282,0.029182&t=h&z=15&om=1)

[Around Mummelsee lac in Black Forest](http://local.google.com/maps?f=q&hl=en&q=http%3A%2F%2Ffrancois.schnell.free.fr%2Fgeo%2F13mai07%2Fdoc-web.kml&ie=UTF8&ll=48.598522,8.201551&spn=0.006301,0.014591&t=h&z=16&om=1)

[Cycling near "the Donon" in Alsace, France](http://maps.google.com/maps?f=q&hl=en&q=http%3A%2F%2Ffrancois.schnell.free.fr%2Fgeo%2F04mar07%2Fdoc-web.kml&ie=UTF8&ll=48.460173,7.053223&spn=0.101086,0.233459&t=h&z=12&om=1)
### Steps ###

Before geocoding in GPicSync:

  * check ` "Google Maps export, folder URL=" `
  * fill the field with the URL of the picture folder you want:
    * don't forget the `http://` and the final "/" (ie `http://pathToThePicturesFolder/`)
  * at the end of the geocoding there is a doc-web.kml file in the picture folder
  * with a FTP client upload the picture folder on your webserver (with the URL you've given)

To view your pictures and track in Google Maps:

  * go to the Google Maps website
  * in the search box enter the URL of the doc-web.kml (`http://pathToThePicturesFolder/doc-web.kml`)
  * center the map and chose the viewing mode you like (map,hybrid,satellite)
  * click on "Link to this map" to have a URL you can use on your webpages

When you click on a camera icon you'll see a thumbnail of the picture. If you click on it the full size version will appear in your browser. A good idea is to click with the middle button of your mouse so it will appear in a separate tab in Firefox or IE7 (you won't have to reload your Google Map each time).

Warning, if you have more than 50 pictures it looks like Google Maps website won't show all of them.