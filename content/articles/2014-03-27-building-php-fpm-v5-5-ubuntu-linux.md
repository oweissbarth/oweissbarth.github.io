---
title: Build php5.5 with fpm on ubuntu linux
author: oweissbarth
date: 2014-03-27T15:45:40+00:00
url: /building-php-fpm-v5-5-ubuntu-linux/
featured_image: /images/articles/php5/php5-feature.png
categories:
  - 'Tips&amp;Tricks'
  - Tutorials

---
In this article I&#8217;m gonna give a quick guide on building and installing php5.5 with FastCGI Process Manager on Linux. I did test it on Ubuntu 12.04 but it should work on nearly any Linux distribution out there.  
&nbsp;

  1.  Get the source-code  
     {{< highlight bash >}}wget http://de2.php.net/distributions/php-5.5.10.tar.bz2 {{< /highlight >}}
  2. Extract and remove the archive  
    {{< highlight bash >}}tar xvjf php-5.5.10.tar.bz2<br> rm php-5.5.10.tar.bz2<br> cd php-5.5.10` {{< /highlight >}}
  3. Configure and create the Makefile  
    {{< highlight bash >}}./configure --enable-fpm --with-fpm-user=www-data --with-fpm-group=www-data --with-mysqli --with-mysql --with-openssl --with-curl --with-zlib  {{< /highlight >}}
  4. Compile the source-code  
    {{< highlight bash >}}make {{< /highlight >}}
  5. Enable the default fpm configuration  
    {{< highlight bash >}}sudo mv /usr/local/etc/php-fpm.conf.default /usr/local/etc/php-fpm.conf {{< /highlight >}}
  6. Copy the php-fpm executable into /etc/init.d/ and set permissions  
    {{< highlight bash >}}sudo cp sapi/fpm/init.d.php-fpm /etc/init.d/php-fpm<br> sudo chmod 755 /etc/init.d/php-fpm {{< /highlight >}}
  7.  Add php-fpm as a service and start it  
    {{< highlight bash >}}sudo update-rc.d php-fpm defaults<br> sudo service php5-fpm restart  {{< /highlight >}}
    

  
If you have any problems getting this to work or any further questions please leave a comment or mail me.