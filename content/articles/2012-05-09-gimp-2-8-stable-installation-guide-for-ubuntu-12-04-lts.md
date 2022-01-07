---
title: Installation of Gimp 2.8 on Ubuntu 12.04 LTS
author: oweissbarth
date: 2012-05-09T13:06:02+00:00

---
Hi guys,  
Gimp 2.8 stable was officially released. To install it on a Ubuntu 12.04 you will need to install the same packages as for the RC.  
If you already used the release canidate of 2.8 installing will be as easy as downloading the source from <a title="ftp://ftp.gimp.org/pub/gimp/v2.8/" href="ftp://ftp.gimp.org/pub/gimp/v2.8/" target="_blank">ftp://ftp.gimp.org/pub/gimp/v2.8/</a> and running:

{{< highlight bash>}}./configure
make
sudo make install
{{< /highlight >}}

If you did not install the release canidate before you will need to install some additional packages.  
The following will be mostly copied from my guideline to install Gimp 2.7.5. I just corrected some things and added additional information.  

When i write &#8220;configure, make and install <package>&#8221; i mean to navigate to the source location and run the following commands:

{{< highlight bash>}}
./autogen.sh /*if existing*/
./configure
make
sudo make install
{{< /highlight >}}

If you got a multi-core-processor you can use multiple core when making:

{{< highlight bash>}}
make -j3 /*if you got a dual-core*/
make -j5 /*if you got a quad-core*
{{< /highlight >}}

You can download the archives by using:  
{{< highlight bash>}}
wget &lt;archive&gt;&lt;
{{< /highlight >}} 
To extract the archives using commands use these ones:  
For .tar.bz2: {{< highlight bash>}} tar -jxvf .tar.bz2 {{< /highlight >}}

For .tar.gz: {{< highlight bash>}}tar -zxvf .tar.gz {{< /highlight >}}

For .tar.xz: {{< highlight bash>}}
unxz .tar.xz 
tar xfv .tar {{< /highlight >}}


&#8211; Download Gimp 2.8 Source from <a title="ftp://ftp.gimp.org/pub/gimp/v2.8/" href="ftp://ftp.gimp.org/pub/gimp/v2.8/" target="_blank">ftp://ftp.gimp.org/pub/gimp/v2.8/</a> and extract to directory  
&#8211; open terminal and navigate to your temporary folder  
&#8211; update intltool by running:

{{< highlight bash>}}
sudo apt-get install intltool
{{< /highlight >}}


update gtk+ by running:

{{< highlight bash>}}sudo apt-get install libgtk2.0-dev{{< /highlight >}}

install gtk-doc by runnning:

{{< highlight bash>}}sudo apt-get install gtk-doc-tools {{< /highlight >}}
install zlib by running:  
{{< highlight bash>}}sudo apt-get install libghc-zlib-dev {{< /highlight >}}
install vapigen by running:  
{{< highlight bash>}}sudo apt-get install valac {{< /highlight >}}
install python headers by running:

{{< highlight bash>}}sudo apt-get install python-dev{{< /highlight >}}

install pygobject by running:
{{< highlight bash>}}sudo apt-get install python-gobject-dev{{< /highlight >}}

 install python-gtk2-dev by running:
{{< highlight bash>}}sudo apt-get install python-gtk2-dev {{< /highlight >}}


download an extract babl from <a title="ftp://ftp.gtk.org/pub/babl/0.1/babl-0.1.10.tar.bz2" href="ftp://ftp.gtk.org/pub/babl/0.1/babl-0.1.10.tar.bz2">ftp://ftp.gtk.org/pub/babl/0.1/babl-0.1.10.tar.bz2</a>


- configure, make and install babl  
- download and extract glib from <a href="ftp://ftp.gtk.org/pub/glib/2.32/glib-2.32.0.tar.xz" target="_blank">ftp://ftp.gtk.org/pub/glib/2.32/glib-2.32.0.tar.xz</a>  
- configure, make and install glib  
- download and extract gegl from [ftp://ftp.gtk.org/pub/gegl/0.2/gegl-0.2.0.tar.bz2][1]  
- configure, make and install gegl  
- if gegl doesn't find your new glib try running:

{{< highlight bash>}}sudo ldconfig{{< /highlight >}}

download and extract pygtk from <a href="http://ftp.gnome.org/pub/GNOME/sources/pygtk/2.24/pygtk-2.24.0.tar.gz" target="_blank">http://ftp.gnome.org/pub/GNOME/sources/pygtk/2.24/pygtk-2.24.0.tar.gz</a>

- configure, make and install pygtk  
- navigate to gimp folder  
- configure, make and install gimp  

You are ready!

 [1]: ftp://ftp.gtk.org/pub/gegl/0.2/gegl-0.2.0.tar.bz2 "ftp://ftp.gtk.org/pub/gegl/0.2/gegl-0.2.0.tar.bz2"