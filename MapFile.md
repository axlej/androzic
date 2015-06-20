# Introduction #

This document describes contents of OziExplorer map calibration file. ~~Strikeout~~ is used to mark sections or parameters that are ignored or not yet supported by Androzic.

# Format description #

**Header**

Line 1 : header and ~~version~~ of file

Line 2 : title of map - any text string

Line 3 : link to map image file

Line 4 : ~~map code~~ - only used for special types of maps, cannot be modified by the user but must be there

Line 5 : datum settings
  * Field 1 : map datum
> Note : for normal maps only the datum in the first field is used the ~~rest of the parameters~~ are for datum shifts and there is normally no need for these to be modified by the user.

Line 6 : reserved for future use

Line 7 : reserved for future use

Line 8 : ~~magnetic Variation entry~~
  * Field 2 : degrees
  * Field 3 : minutes
  * Field 4 : hemisphere

Line 9 : map projection, parameters are specified after their names:
  * Map Projection : must match the projection name used in OziExplorer
  * ~~PolyCal~~ : `Yes` - Polynomial calibration is used, `No` - not
  * ~~AutoCalOnly~~ : `Yes` - calibration cannot be adjusted by the user, `No` - it can
  * ~~BSBUseWPX~~ : For BSB images only, `Yes` - the calibration equations contained in the BSB file are used.

**Calibration points**

Generally there are always 30 of them, but empty points can be safely removed.
  * Field 1 : ~~point number~~
  * Field 3 : x coordinate
  * Field 4 : y coordinate
  * Field 5 : in - used, ex - ignored
  * Field 7 : latitude degree (integral number)
  * Field 8 : latitude minute (fractional number)
  * Field 9 : latitude hemisphere (`N` or `S`)
  * Field 10 : longitude degree (integral number)
  * Field 11 : longitude minute (fractional number)
  * Field 12 : longitude hemisphere (`E` or `W`)
  * Field 14 : UTM grid number
  * Field 15 : easting
  * Field 16 : northing
  * Field 17 : hemisphere (`N` or `S`)

**Projection setup**

  * Field 1 : `Projection Setup`
  * Field 2 : latitude origin
  * Field 3 : longitude origin
  * Field 4 : K factor
  * Field 5 : false easting
  * Field 6 : false northing
  * Field 7 : latitude 1
  * Field 8 : latitude 2
  * Field 9 : ~~height~~ - used in the Vertical Near-Sided Perspective Projection
  * Field 10 : ~~sat~~ - not used
  * Field 11 : ~~path~~ - not used

**~~Marker line~~**

Marker line contains no information but is used as a file marker, must be there

**~~Map features~~**

Each map feature consists of three lines:

Line 1 :

  * Field 1 : `MF`
  * Field 2 : number
  * Field 3 : name
  * Field 4 : latitude
  * Field 5 : longitude
  * Field 6 : show format - not used
  * Field 7 : foreground color
  * Field 8 : background color
  * Field 9 : symbol name
  * Field 10 : create waypoint
  * Field 11 : waypoint name
  * Field 12 : format type - internal use

Line 2 : the link to the picture, if there is no picture a blank line must be there
Line 3 : the description of the feature, if no description the blank line must be there

**~~Map comments~~**

Each map comment consists of two lines:

Line 1 :
  * Field 1 : `MC`
  * Field 2 : number
  * Field 3 : latitude
  * Field 4 : longitude
  * Field 5 : show format - not used
  * Field 6 : foreground color
  * Field 7 : background color
  * Field 8 : width
  * Field 9 : height
  * Field 10 : font size
  * Field 11 : font style

Line 2 : The text for the comment

**~~Attached file~~**

Each line describes one attach, .plt, .wpt, .evt, .pnt files can be attached.

Line 1 : ~~track file section marker~~
Lines :
  * Field 1 : `TF`
  * Field 2 : path to file

**Moving map**

Line 1 : ~~moving map section marker~~

Line : ~~MM0~~ - use in moving map, if parameter is set to `No` then the map will be excluded when looking for a new map to change to when using moving map mode. It does not affect other map find functions.

Line : MMPNUM - number of map border points (corner markers)

Lines : corner marker pixel location, one line per corner marker
  * Field 1 : `MMPXY`
  * Field 2 : marker number
  * Field 3 : x coordinate
  * Field 4 : y coordinate

Lines : corner marker geodetic location, one line per corner marker
  * Field 1 : `MMPLL`
  * Field 2 : marker number
  * Field 3 : longitude
  * Field 4 : latitude

Line : map scale (meters/pixel), it is calculated in the left to right image direction
  * Field 1 : `MM1B`
  * Field 2 : pixel scale (fractional number)

**Lat/lon grid setup**

Line 1 : ~~`LL Grid Setup`~~

Line 2 :
  * Field 1 : `LLGRID`
  * Field 2 : grid on - `Yes` = display grid
  * Field 3 : grid spacing - number and unit (`Deg`,`Min`,`Sec`)
  * Field 4 : ~~autoscale - `Yes` = autoscale on~~
  * Field 5 : degree line color
  * Field 6 : minute line color
  * Field 7 : second line color
  * Field 8 : ~~label spacing - number and unit (`Deg`,`Min`,`Sec`)~~
  * Field 9 : ~~label foreground color~~
  * Field 10 : ~~label background color~~
  * Field 11 : ~~label size~~
  * Field 12 : ~~label - show on all screens~~
  * Field 13 : ~~clip to neat line~~
  * Field 14 : ~~x - ??~~

**Other grid setup**

Line 1 : ~~`Other Grid Setup`~~

Line 2 :
  * Field 1 : `GRGRID`
  * Field 2 : grid on - `Yes` = display grid
  * Field 3 : grid spacing - number and unit (`Km`,`M`)
  * Field 4 : ~~autoscale - `Yes` = autoscale on~~
  * Field 5 : km line color
  * Field 6 : meter line color
  * Field 7 : ~~label spacing - number and unit (`Km`,`M`)~~
  * Field 8 : ~~label foreground color~~
  * Field 9 : ~~label background color~~
  * Field 10 : ~~label size~~
  * Field 11 : ~~label - show on all screens~~
  * Field 12 : ~~clip to neat line~~
  * Field 13 : ~~no meters shown in label - ??~~
  * Field 14 : ~~show last 3 digits in label - ??~~
  * Field 15 : ~~x - ??~~

**~~Map Open Position~~**

The position the map will be centered on when it is opened.

  * Field 1 : `MOP`
  * Field 2 : `Map Open Position`
  * Field 3 : x coordinate
  * Field 4 : y coordinate

**Map Image Width/Height**

The map image width and height - not used in OziExplorer but is required for Androzic for a time being.

  * Field 1 : `IWH`
  * Field 2 : `Map Image Width/Height`
  * Field 3 : image width
  * Field 4 : image height

# Androzic specific issues #

  1. Androzic always operates in WGS84 datum, map datum is converted to WGS84 at load time.
  1. Androzic does not guess image file name - it must have correct name and extension (unix paths are honored, windows paths are ignored, relative paths not supported, file names without path are supported).
  1. If map file does not contain corner markers then they are automatically calculated based on image corners.
  1. Androzic does not depend on line order except to things: projection definition must precede projection setup and number of map corner markers must precede corner marker coordinates.