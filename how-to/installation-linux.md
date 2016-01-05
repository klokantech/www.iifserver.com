---
layout: how-to
id: installation-linux
title: How-to
keywords: installation
description: instalation of IIIFServer.
---

#Installation

##Linux

1. Install webserver (Apache2, Lighttpd, Nginx)
2. [Download](/download) and install the DEB or RPM package for your distribution 
3. Open browser at `http://localhost/iiif/demo` (or `http://localhost/iiif/` for activation)

###Debian and Ubuntu

####Apache2

Configure script: */etc/apache2/mods-available/iiifserver.conf*
{% highlight html %}
sudo apt-get install apache2 libapache2-mod-fcgid
sudo a2enmod rewrite
{% endhighlight %}

####Lighttpd

Configure script: */etc/lighttpd/conf-available/20-iiifserver.conf*
{% highlight html %}
sudo apt-get install lighttpd
{% endhighlight %}

####Nginx

Configure script: */etc/nginx/sites-available/iiifserver.conf*
{% highlight html %}
sudo apt-get install nginx
{% endhighlight %}

###CentOS and Fedora

####Apache2 (httpd)

Configure script: */etc/httpd/conf.d/iiifserver.conf*
{% highlight html %}
sudo yum install httpd mod_fcgid
{% endhighlight %}

####Lighttpd

Configure script: */etc/lighttpd/conf.d/20-iiifserver.conf*
{% highlight html %}
sudo yum install lighttpd lighttpd-fastcgi
{% endhighlight %}

####Nginx

Configure script: */etc/nginx/sites-available/iiifserver.conf*
{% highlight html %}
sudo yum install nginx
{% endhighlight %}
