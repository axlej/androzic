You can use any icon set as marker icons if you like. Icons have to meet only two criteria:
  1. they must be uniform (have same size and anchor location)
  1. they must be in PNG format

Create `icons` folder under Androzic application folder (configured in Settings) or empty existing one. Copy your preferred icons in the `icons` folder. Create `icons.dat` text file in `icons` folder. File must contain one line with the following format:

`X,Y,D`

here X stands for horizontal pixel coordinate of an anchor in marker icon, Y stands for vertical pixel coordinate of an anchor, D stands for a waypoint name position relative to marker icon: 0 - top, 1 - right, 2 - bottom, 3 - left (_name position will be supported in future releases_).

Illustration of marker icon anchor:

![http://androzic.googlecode.com/files/markericonanchor.png](http://androzic.googlecode.com/files/markericonanchor.png)