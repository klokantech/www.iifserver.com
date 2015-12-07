---
layout: how-to
title: How-to
keywords: installation
description: instalation of IIIFServer.
---

#Installation

##Debian
1) [Download](/download) the .deb package for your distribution 

2) Double-click and press the "Install package" button

3) Open "Applications" -> "Accessories" -> "Terminal" and type there:


{% highlight html %}
sudo apt-get install lighttpd

sudo ln -s /etc/iipimage/iipimage-lighttpd.conf /etc/lighttpd/conf-available/99-iipimage.conf
sudo lighty-enable-mod iipimage
sudo /etc/init.d/lighttpd force-reload

sudo ln -s /usr/share/iipimage/www /var/www/iip
{% endhighlight %}

4) Open in your browser the demo image: http://localhost/iip/ or http://address.to.your.server/iip/

Finished! You should see the zoomable image.
Now you can experiment with the viewers, customize the look&feel, add your own .jp2 or .tiff images, etc.

## Installation with Docker