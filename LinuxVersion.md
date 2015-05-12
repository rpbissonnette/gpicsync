**GPicSync RPM packages:**

[Marc Christensen](http://blog.mecworks.com/) have created RPM packages for many Linux distributions. More [informations here](RpmPackages.md).

**GPicSync for Ubuntu and Debian based Linux distributions:**

Thanks to [Tobias Domhan](http://devnull.tdomhan.de/):

> "
> just add the following two lines to /etc/apt/sources.list(alternatively
> you can use GUI tools like synaptic):

> deb http://ppa.launchpad.net/tdomhan/ppa/ubuntu jaunty main

> deb-src http://ppa.launchpad.net/tdomhan/ppa/ubuntu jaunty main

> afterward run "sudo  apt-get update && sudo apt-get install gpicsync"

> you might get warnings because the packages can't be authenticated
> in order to do so you have to import the OpenPGP key the repository is
> signed with, which can be found here:

> https://launchpad.net/~tdomhan/+archive/ppa

> a video how to import the key can be found here:

> http://www.youtube.com/watch?v=UUZOQsNo_ws
> after that rerun the above stated command
> "

**GPicSync from Source:**

You can have the latest development version by doing a SVN checkout in a shell:

`svn checkout http://gpicsync.googlecode.com/svn/trunk/ gpicsync`

Then read the README file to check for dependencies.