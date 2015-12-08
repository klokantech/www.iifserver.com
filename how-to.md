---
layout: how-to
title: How to
keywords: Jpeg2000, TIFF
description:
---

#How to

<i>Note: This section is under construction - based on our original page <a href="http://help.oldmapsonline.org/jpeg2000">http://help.oldmapsonline.org/jpeg2000</a>.</i>

IIIFServer is a light-weight client-server system for fast and efficient online 
viewing and zooming of ultra high-resolution JPEG2000 and TIFF images. It is 
designed to be bandwidth and memory efficient and usable over a slow Internet 
connection even on gigapixel size images. The IIPImage server is compatible with 
a large number of client-side viewers. You can use either pure web viewers 
(written only in HTML/JavaScript) or plugin-based viewers using Adobe Flash, 
Silverlight or Java. Even applications such as Seadragon for Apple iPhone or 
Google Earth for Mac/Linux/Windows can display your image distributed with 
IIPimage software.

**Anybody who wants stunning online presentations of scanned documents, paintings, 
maps, books, newspapers or other high-resolution images can use the free IIIFServer 
software to publish the images to the web directly from JPEG2000 or TIFF files.**

We recommend installing the IIIFServer software on a Linux (or other UNIX) server. 
We have prepared a easy to install binary package for Debian and Ubuntu with 
step-by-step instructions for installation.

IIIFServer streams images to the user through either the IIP protocol (Internet 
Imaging Protocol) to one of the native clients or also in the latest releases 
via the Zoomify or Deep Zoom tile protocol. Any Zoomify or Deep Zoom compatible 
viewer can, therefore, be used for easy online panning and zooming of the 
published images. Recently Klokan Technologies GmbH has implemented also 
support for [IIIF protocol](http://iiif.io/).

**Neither the distribution nor the use of this application should be 
for financial return!**

IIPImage is available for free, under an open source license (GNU GPL). It is 
FastCGI-based and can be embedded in most web servers. JPEG2000 support has 
been enabled via the Kakadu JPEG2000 library, which provides one of the fastest 
implementations of the JPEG2000 ISO standard and is redistributable **for 
non-commercial use only**.


##How to convert my images into JPEG2000?

There are many tools able to convert existing images into .JP2 format. 
We recommend for batch processing using the freely available tools distributed 
with the Kakadu JPEG2000 Library: for encoding (kdu_compress), transcoding 
(kdu_transcode), viewing with metadata and file structure display (kdu_show):

You can download them for free for Windows, Mac and Linux at: 
[http://www.kakadusoftware.com/](http://www.kakadusoftware.com/)
Please read the documentation attached to these tools.

##Encoding parameters for JPEG2000 <a href="#encoding-parameters" id="encoding-parameters" class="link-hash">#</a>

[JPEG2000 as a Preservation and Access Format for the Wellcome Trust Digital 
Library](https://docs.google.com/viewer?url=http%3A%2F%2Fsites.google.com%2Fa%2Foldmapsonline.org%2Foldmapsonline%2Fjpeg2000%2F19885793-JPEG2000-Recommendations-for-the-Wellcome-Trust.pdf%3Fattredirects%3D0) 
([view a local copy](http://docs.google.com/a/oldmapsonline.org/viewer?a=v&pid=sites&srcid=b2xkbWFwc29ubGluZS5vcmd8b2xkbWFwc29ubGluZXxneDozMWE3YWM0Y2ZjMjAzOWRm)) 
by Robert Buckley from the Xerox Corporation 
gives a great introduction into the JPEG2000 encoding parameters.

Another interesting article with best-practice is: [JPEG2000 Implementation 
at Library and Archives Canada](http://www.archimuse.com/mw2007/papers/desrochers/desrochers.html).

In case you are encoding news papers, then you can read the recommendations 
in the article: [JPEG 2000 Profile for the National Digital Newspaper Program](https://docs.google.com/viewer?url=http%3A%2F%2Fwww.loc.gov%2Fndnp%2Fpdf%2FNDNP_JP2HistNewsProfile.pdf) 
(local copy attached) and the Technical specification at 
[http://www.loc.gov/ndnp/](http://www.loc.gov/ndnp/). You find in those documents direct 
commands for using kdu_compress.

To understand the JPEG2000 internals you should study the [original JPEG2000 
documentation](http://www.jpeg.org/jpeg2000/index.html), and the [JPEG2000 book](http://www.wkap.nl/prod/b/0-7923-7519-X)
and articles from the author of Kakadu library like:<br>
[http://www.ee.unsw.edu.au/~taubman/publications_files/remote-browsing-icip02.pdf](http://www.ee.unsw.edu.au/~taubman/publications_files/remote-browsing-icip02.pdf)

##JPEG2000 lossless masters for both archiving and online distribution, 
(replacement for TIFF masters)

It is possible to prepare a lossless JPEG2000 files with kdu_compress. For 
correct parameters please read the documentation on this page and in linked 
articles.

When migrating to JPEG2000 as your archival master format for scanned images 
be sure to correctly convert all technical metadata embedded in the original 
(probably TIFF), including ICC color profiles. Details: 
[Data Dictionary – Technical Metadata for Digital Still Images](http://www.niso.org/kst/reports/standards?step=2&gid=None&project_key=b897b0cf3e2ee526252d9f830207b3cc9f3b6c2c)
(local copy attached)

JPEG2000 Migration project:
http://public.migrator2000.org/

Very useful is also the article: 
[A format for Digital Preservation of Images by Buonora P., Liberati F.](http://www.dlib.org/dlib/july08/buonora/07buonora.html)

##Alternatives to this project

####OpenSource projects:

There is Adore Djatoka image server which is Java-based. Info at: 
[http://www.dlib.org/dlib/september08/chute/09chute.html](http://www.dlib.org/dlib/september08/chute/09chute.html)
Another alternative is the Zoomify-compatible J2K Tiler Renderer: 
[http://dltj.org/article/introducing-j2ktilerenderer/"](http://dltj.org/article/introducing-j2ktilerenderer/). 
Both are using Kakadu library. 

It is a matter of taste what project you choose. 
We think that our C++/FastCGI IIPImage application is simple, fast and easy to 
install and deploy. IIPImage supports several different web viewers for the 
presentation, and you get the Zoomify and DeepZoom tile compatibility directly.

####Commercial products:

For example: LizardTech Express Server, Aware JPEG2000 Image Server, LuraWave 
JP2 Image Content Server, Centrica XLImage Server, ... or modules bundled into 
the complex systems like ContentDM or DigiTool.

###Why proprietary Kakadu JPEG2000 library as the base for GPL IIPimage instead of the existing free implementations of the JPEG2000?

We did performance tests of available existing open-source libraries such 
as [OpenJPEG](http://www.openjpeg.org/) and [JasPer](http://www.ece.uvic.ca/~frodo/jasper/). 
Unfortunately those did not provide the requisite 
decoding speed and gigapixel image support necessary for real-time distribution,
so for now we have chosen the Kakadu library. The OpenJPEG library, however, 
looks promising for the future.

This choice, however, imposes a limit on the use of IIPImage when used with 
Kakadu: even though we are releasing our project as open-source software, 
the decoding functionality for the JPEG2000 format **can be used only for 
non-commercial purposes due to the Kakadu library license.**
We are the Licensee of Kakadu library according the Kakadu Non-Commercial 
License and we distribute the Application to you (the Third party). The relevant
paragraph from the license agreement is: "The Licensee shall have the right to
Deployment of the KAKADU Software, provided that such Deployment does not 
result in any direct or indirect financial return to the Licensee or any other 
Third Party which further supplies or otherwise uses such Applications.".

**BINARIES WITHOUT THESE RESTRICTIONS CAN BE ACQUIRED ON REQUEST FROM KLOKAN 
TECHNOLOGIES GMBH, WHO PURCHASED A SEPARATE COMMERCIAL KAKADU LICENSE ALLOWING 
UNLIMITED BINARY REDISTRIBUTION.**

IIPImage itself is fully open source with source code available under the GPL 
license. The Kakadu licensing restrictions only apply when IIPImage has been 
built with the Kakadu library. To compile the source code of IIPimage yourself 
with support for JPEG2000 images you will need to buy a license for the Kakadu 
library. If, however, you are happy with our binaries then this will not be 
necessary and you can just download and use the package we provide.

Once the OpenJPEG library is more stable it can be linked with IIPImage to 
replace the Kakadu library - and we will be able to remove this 'only for 
non-commercial use' condition and provide unlimited JPEG2000 decoding 
functionality to IIPImage.

If you are an institution who has a grant or project where you wish to use 
JPEG2000, please consider supporting the development of open-source and free 
software projects such as OpenJPEG and IIPImage as we have done.

Update: initial implementation for OpenJPEG2 has been done. Without additional 
optimisations of OpenJPEG2 the speed on larger images is still about 1000x 
faster with Kakadu library.

##Copy & paste commands for JPEG2000 encoding <a href="#commands" id="commands" class="link-hash">#</a>
Here we provide a simple example commands for encoding from .tif to .jp2 for 
testing IIPImage. For the production encoding on your side you should read the 
mentioned documentation and the best practice articles and design the encoding 
parameters directly for your use case. The parameters important for use in 
IIPImage JPEG2000 are: **QualityLayers**, **ResolutionLevels**, and 
**Precincts/Tiles**.

Encoding only for IIPImage distribution (fast but lossy compression, only one 
quality layer, seven levels):

```
kdu_compress -i input.tif -o output.jp2 -rate 0.5 Clayers=1 Clevels=7 
"Cprecincts={256,256},{256,256},{256,256},{128,128},{128,128},{64,64},{64,64},
{32,32},{16,16}" "Corder=RPCL" "ORGgen_plt=yes" "ORGtparts=R" "Cblk={64,64}" Cuse_sop=yes
```

Example of a lossless image with fast display in IIPImage (only the lossy part 
is decoded for online displaying - by default just the first half of quality 
layers is decoded to speed-up the rendering):

```
kdu_compress -i input.tif -o output.jp2 -rate -,0.5 Clayers=2 Creversible=yes 
Clevels=8 "Cprecincts={256,256},{256,256},{128,128}" Corder="RPCL" ORGgen_plt="yes" 
ORGtparts="R" Cblk="{64,64}"
```

##Documents <a href="#documents" id="documents" class="link-hash">#</a>
- [19885793-JPEG2000-Recommendations-for-the-Wellcome-Trust.pdf (665k)](/doc/19885793-JPEG2000-Recommendations-for-the-Wellcome-Trust.pdf)
- [BritishLibraryJPEG2000Profile.pdf (252kB)](/doc/BritishLibraryJPEG2000Profile.pdf)
- [NDNP_JP2HistNewsProfile.pdf (1818kB)](NDNP_JP2HistNewsProfile.pdf)
- [NationalLibraryOfTheCzechRepublicJPEG2000Profile.pdf (4683kB)](/doc/NationalLibraryOfTheCzechRepublicJPEG2000Profile.pdf)
- [Z39-87-2006.pdf (415k)](/doc/Z39-87-2006.pdf)
- [remote-browsing-icip02.pdf (238kB)](remote-browsing-icip02.pdf (298k))
