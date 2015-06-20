**This article is applicable both for Androzic and OziMapper.**

_Notice: this feature is available for donators only._

# Enabling custom online maps #

Custom online maps can be added through special text file. The file has to be named `providers.dat` and be placed in the Application folder (configured in Settings).

# File format #

`providers.dat` is a text file, each line describes single provider. Each provider is described by a set of fields separated by commas. All fields are required, order is strict, no space allowed. If field is undefined for specific provider it must be empty.

**List and order of fields:**
  1. title - map title
  1. code - unique code, only letters and digits allowed, is used as a tile cache directory name
  1. minzoom - minimum zoom, allowed by map
  1. maxzoom - maximum zoom, allowed by map
  1. tilesize - avarage tile size in bytes, can be left empty for default
  1. url - tile provider url containing special placeholders (see bellow)
  1. server1 - server substring, can be empty if not applicable
  1. server2 - server substring, can be empty if not applicable
  1. server3 - server substring, can be empty if not applicable
  1. server4 - server substring, can be empty if not applicable
  1. params - extra parameters: yinverse - inverse Y tile number, ellipsoid - use ellipsoid Mercator projection (default is spherical)

**URL placeholders:**
  * {$s} - server substring (cycles through variants)
  * {$l} - locale
  * {$z} - zoom
  * {$x} - X tile number
  * {$y} - Y tile number
  * {$q} - quad tree
  * {comma} - replaced by comma, should be used if url contains comma

# Examples #

Fully functional example file can be found in Downloads section. Following examples are already included in application:

`OpenStreetMap Mapnik,osm,0,18,22000,http://{$s}.tile.openstreetmap.org/{$z}/{$x}/{$y}.png,a,b,c`

`MapQuest,mq,0,18,,http://otile{$s}.mqcdn.com/tiles/1.0.0/osm/{$z}/{$x}/{$y}.png,0,1,2,3`

`Charts VFR (US),aeromaps,5,12,,http://www.aeromaps.us/Z{$z}/{$y}/{$x}.png`

`Chartbundle US Area Charts,cbenra,4,13,,http://wms.chartbundle.com/tms/1.0.0/enra/{$z}/{$x}/{$y}.png,,,,,yinverse`

# Special cases #

  * If you are not a donator but still want some online map to be included you can share its full description and it will be included in Androzic if it meets two criteria:
    1. Map license permits it's usage in third-party applications.
    1. Map is valuable for significant amount of users (country wide, community wide, etc).
  * If you want to add a provider but tile URL has unsupported format please send as much facts as you know about it so that support can be added in next Androzic updates.