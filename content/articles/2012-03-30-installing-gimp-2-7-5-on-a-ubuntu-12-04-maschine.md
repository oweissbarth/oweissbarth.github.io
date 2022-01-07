---
title: Installing Gimp 2.7.5 on a Ubuntu 12.04 maschine
author: oweissbarth
date: 2012-03-30T17:42:37+00:00

---
Some days ago i read about the one-window-mode in the recent Gimp development version. So i spent some time figuring out how to get Gimp 2.7.5 running on my Ubuntu 12.04. After downloading the source code from gimp.org and running the configure-script i realized that this would be more time consuming than i thought. As i am not a Linux-expert it took me some time to find the different packages and get them working. That&#8217;s why i put together a little guide on how to do it for you.  

# Install Gimp 2.7.5 on a Ubuntu 12.04 maschine  

general information:  
When i write &#8220;configure, make and install <package>&#8221; i mean to navigate to the source location and run the following commands:

{{< highlight bash>}}./configure
make
sudo make install{{< /highlight >}}

If you got a multi-core-processor you can use multiple core when making:

{{< highlight bash>}}make -j3 /*if you got a dual-core*/{{< /highlight >}}

{{< highlight bash>}}make -j5 /*if you got a quad-core*/{{< /highlight >}}

&nbsp;  
If there was an &#8220;autogen.sh&#8221;-file i always ran it before running &#8220;configure&#8221;  
-  create a temporary directory  
-  Download Gimp 2.7.5 Source <a href="ftp://ftp.gimp.org/pub/gimp/v2.7/gimp-2.7.5.tar.bz2" target="_blank">ftp://ftp.gimp.org/pub/gimp/v2.7/gimp-2.7.5.tar.bz2</a> and extract to directory  
-  open terminal and navigate to your temporary folder  
-  update intltool by running:

{{< highlight bash>}}sudo apt-get install intltool{{< /highlight >}}

-  update gtk+ by running:

{{< highlight bash>}}sudo apt-get install libgtk2.0-dev{{< /highlight >}}

-  install gtk-doc by runnning:

{{< highlight bash>}}sudo apt-get install gtk-doc-tools{{< /highlight >}}

-  install zlib by running:

{{< highlight bash>}}sudo apt-get install libghc-zlib-dev{{< /highlight >}}

-  install vapigen by running:

{{< highlight bash>}}sudo apt-get install valac{{< /highlight >}}

-  install python headers by running:

{{< highlight bash>}}sudo apt-get install python-dev{{< /highlight >}}

-  install pygobject by running:

{{< highlight bash>}}sudo apt-get install python-gobject-dev{{< /highlight >}}

-  download an extract babl from <a href="ftp://ftp.gtk.org/pub/babl/0.1/babl-0.1.6.tar.bz2" target="_blank">ftp://ftp.gtk.org/pub/babl/0.1/babl-0.1.6.tar.bz2</a>  
-  configure, make and install babl  
-  download and extract glib from <a href="ftp://ftp.gtk.org/pub/glib/2.32/glib-2.32.0.tar.xz" target="_blank">ftp://ftp.gtk.org/pub/glib/2.32/glib-2.32.0.tar.xz</a>  
-  configure, make and install glib  
-  download and extract gegl from <a href="ftp://ftp.gtk.org/pub/gegl/0.1/gegl-0.1.8.tar.bz2" target="_blank">ftp://ftp.gtk.org/pub/gegl/0.1/gegl-0.1.8.tar.bz2</a>  
-  configure, make and install gegl  
-  download and extract pygtk from <a href="http://ftp.gnome.org/pub/GNOME/sources/pygtk/2.24/pygtk-2.24.0.tar.gz" target="_blank">http://ftp.gnome.org/pub/GNOME/sources/pygtk/2.24/pygtk-2.24.0.tar.gz</a>  
-  configure, make and install pygtk  
-  navigate to gimp folder  
-  configure, make and install gimp  
-  type &#8220;gimp-2.7&#8221; press &#8220;enter&#8221; and enjoy it  
&nbsp;  
I hope it works for you.