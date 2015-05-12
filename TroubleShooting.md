If you encounter a problem with GPIcSync or have a feature request thanks to let me know at this email (include "gpicsync" in the subject): ![http://francois.schnell.free.fr/fschnellgmail.png](http://francois.schnell.free.fr/fschnellgmail.png)
(If possible join a GPX and one or two pictures so that I can reproduce an eventual problem.)

The "old" issues page can be found here [here](http://code.google.com/p/gpicsync/issues/list)


**0) GPicSync stops?**

Verify that your paths/names to the  pictures and gpx files are ASCII (English characters) as Unicode support is not complete. Alternatively you may try [version 1.28](http://sourceforge.net/projects/gpicsync/files/GPicSync/GPicSync1-28/). More technical infos [here (comment 5)](http://code.google.com/p/gpicsync/issues/detail?id=117#c5)

**1)If you have an error MSVCP71.dll and/or MSVCR71.dll was not found (or another dll file).**

This dll(s) should be installed by default on Windows XP. You can Google their name and download them on specialized site like "dll-files.com".

Basically, you can put them in the GPicSync installation folder or better in the system directory (on Windows XP it is C:\Windows\System32\)

It seems that MSVCP71.dll and MSVCR71.dll work together so if you have a missing message for one be sure you also have the other one.

If it's still doesn't work please contact me.

If after that you still have a  problem try to install the Microsoft .Net framework.

**2)If GPicSync says geocoding went fine (and Google Earth file is OK) but the position wasn't written in the picture metadata**

Another software you've used may have altered or "corrupted" the picture metadata in a way that EXIFtool (library used by GPicSync) can't deal with anymore.

Few tips to workaround this (whatever the software you used):
http://groups.google.com/group/gpicsync/browse_thread/thread/1258406a030ff7c6


**3) If no indications of localization appears check first your .gpx file:**

A .gpx file is a "XML" file. You can open it and modify it easily in a text editor: it has plenty of tags (

&lt;tag&gt;

 .... 

&lt;/tag&gt;

)

Gpx files have one or more 

&lt;trkseg&gt;

 ... 

&lt;/trkseg&gt;

  which contain plenty of trackpoints 

&lt;trkpt&gt;

...

&lt;/trkpt&gt;

 which says at which location you were at a precise time.

```
...
<trkseg>
... 
<trkpt lat="48.50517319" lon="7.13916969">
<ele>700.46</ele>
<time>2007-03-04T12:05:16Z</time>
</trkpt>
<trkpt lat="48.50517286" lon="7.13916759">
<ele>704.30</ele>
<time>2007-03-04T12:05:18Z</time>
</trkpt>
<trkpt lat="48.50517294" lon="7.13916550">
<ele>708.15</ele>
<time>2007-03-04T12:05:20Z</time>
</trkpt
 ... ... 
</trkseg>
...
```

Use "Tools"->"GPX Inspector" to quickly see the data GPicSync finds in it.
If your gpx file seems fine use "Tools"->"EXIF Reader" and check if your photos contain a 'Date/Time Original' field like (Date/Time Original : 2007:04:06 14:41:02). Some image processing software erase metadata (Picassa for example keeps the metadata).

**4) Geonames don't work**

Please check geonames page (individual geonames account).
https://code.google.com/p/gpicsync/wiki/GeonamesMetadata