========================================
Experimental Leaflet.js based DZI viewer
========================================

Background
----------

We have a large number of images using the `Deep Zoom Image
<http://en.wikipedia.org/wiki/Deep_Zoom>`_ format. Unfortunately, the `opensource release by
Microsoft <http://openseadragon.codeplex.com/>`_ has not been significantly maintained and the
brunt of the modernization has been performed by a single colleague (see
https://github.com/thatcher/openseadragon)

This repository is an experiment using `Leaflet.js <http://www.leafletjs.com>`_ to load the
existing DZI image tiles as part of a possible migration strategy to a project with more momentum
and which I'm currently evaluating for related mapping projects as well.

Status
------

* Experiment: http://acdha.github.com/leaflet-dzi-experiment
* Comparison: http://www.wdl.org/en/item/4032/zoom/

Issues & Oddities
-----------------

* Leaflet currently lacks a way to set boundaries for TileLayers, which causes 404s for all parts of
  the viewport outside of the image extents (see https://github.com/CloudMade/Leaflet/pull/401)
* Until https://github.com/CloudMade/Leaflet/issues/210 and
  https://github.com/CloudMade/Leaflet/pull/676 are closed we have some boilerplate creating a
  straight coordinate system which doesn't attempt to treat our source image as geography with the
  associated coordinate transforms.
* Leaflet assumes that image tiles are all 256x256. The tiles around the edge of the master image in
  our DZI stacks are not constant size and so we have to override the CSS setting the image
  dimensions. It's not clear whether this has a significant performance impact on any particular
  clients.

License
-------

Public domain

Warranty
--------

None