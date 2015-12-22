---
layout: how-to
title: How-to
keywords: installation
description: instalation of IIIFServer.
---

#Installation

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

##Setup of IIIFServer

###Image directory

Default folder `/data/` is created during installation with sample image `demo.jp2`.
Change value for `FILESYSTEM_PREFIX` in configure script of your webserver (see above).

###Image extension

Change value for `FILENAME_EXTENSION` in configure script of your webserver (see above).
Default value created during installation is `.jp2`.

## Installation with Docker

Download a ready-to-use docker image proving IIIF service via IIIFServer powered by IIPImage, Kakadu JPEG2000, nginx and memcached.
JPEG2000 images in "/data" are made available via IIIF Image API 2.0.
The container automatically encodes TIFF and JPEG files in "/dropzone" volume into .jp2 format. 
Whole IIIF service can be started with one command:

{% highlight html %}
docker run -ti --rm -p 80:80 klokantech/iiifserver-iipimage-jpeg2000
{% endhighlight %}

And check demo file on url:

{% highlight html %}
http://127.0.0.1/demo/info.json
http://127.0.0.1/demo
{% endhighlight %}

To include you own data you can mount your existing directory with .jp2 files to /data or a directory with .tif or .jpg files to /dropzone. The argument `-v` can be used for this mapping of directories, for example: `-v /my/tifs:/dropzone`.
