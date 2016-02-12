---
layout: how-to
id: installation-docker
title: How-to
keywords: installation
description: instalation of IIIFServer.
---

#Installation

## Docker

Download a ready-to-use docker image proving IIIF service via IIIFServer 
powered by IIPImage, Kakadu JPEG2000, nginx and memcached.
JPEG2000 images in "/data" are made available via IIIF Image API 2.0.
The container automatically encodes TIFF and JPEG files in "/dropzone" volume 
into .jp2 format. Whole IIIF service can be started with one command:

{% highlight html %}
docker run -ti --rm -p 80:80 klokantech/iiifserver-iipimage-jpeg2000
{% endhighlight %}

And check demo file on url:

{% highlight html %}
http://127.0.0.1/demo/info.json
http://127.0.0.1/demo
{% endhighlight %}

To include you own data you can mount your existing directory with .jp2 files to /data or a directory with .tif or .jpg files to /dropzone. The argument `-v` can be used for this mapping of directories, for example: `-v /my/tifs:/dropzone`.

## Kitematic

<iframe width="420" height="315" src="https://www.youtube.com/embed/nKjI_CvHyHg" frameborder="0" allowfullscreen></iframe>
