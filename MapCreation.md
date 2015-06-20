# Introduction #

There are four major sources for Ozi maps:
  * online map services like Google Maps or Open Street Maps
  * vector maps
  * scanned paper maps and map atlases
  * hand drawn plans, photographed recreation plans or other self-created maps

We will go into detail with first two situations.

# Online maps #

Online maps almost always consist of small pieces called tiles which are placed together by map rendering software to produce a full map. Currently the most powerful and easy to use program is [Mobile Atlas Creator](http://trekbuddyatlasc.sourceforge.net/). It can create .png image Ozi map that can be afterwards converted to mobile format by [Img2ozf](http://www.oziexplorer3.com/img2ozf/img2ozf.html) utility.

There are some other programs that can generate Ozi maps:
  * [GoogleOzi](http://www.zubak.sk/GoogleOzi/) - generates Ozi maps from Google Maps
  * [OSM-map](http://sites.google.com/site/alpohassinen/osm-map) - generates Ozi maps from Open Street Maps
  * [OSMtiledownloader](http://wiki.openstreetmap.org/wiki/OSMtiledownloader) - generates image files from Open Street Maps which can be calibrated and converted to Ozi maps
  * [MGmaps](http://www.mgmaps.com/stored/) - too sophisticated for average user.

# Vector maps #

Vector maps can be converted to Ozi maps with [GPSMapEdit](http://www.geopainting.com/en/) program.

# Scanned paper maps #

  1. Scan the paper map in parts that fit on the scanner. Make sure they are straight oriented.
  1. If you have produced several image files you can use [Map Merge](http://www.oziexplorer3.com/mapmerge/mapmerge.html) - it will produce one big image.
  1. Run OziExplorer and select "Load and Calibrate Map Image" from menu.
  1. You can look for coordinates of calibration points in less detailed ozi maps or online sources (like Google Maps). Some maps contain coordinate grid that you can use. Four calibration points near image corners would be almost always sufficient.
  1. Calibrate and save a map, this will produce a .map file.
  1. If your map is not rectangular that you can optionally use [Mapborder](http://members.optusnet.com.au/~johntserkezis/mapborder.html) OziExplorer addon to add corner markers to a map.
  1. Use [Img2ozf](http://www.oziexplorer3.com/img2ozf/img2ozf.html) to convert image format to ozfx3 format.