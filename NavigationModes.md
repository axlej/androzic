Androzic has two navigation modes:
  1. Navigation to waypoint
  1. Navigation via route
The second one can be considered an extension to the first one.

# Navigation to waypoint #

Navigation to waypoint is initiated by pressing Navigate button in waypoint description or selecting Navigate menu item in waypoint context menu. When navigating to waypoint distance, [bearing](Terms.md) and [turn](Terms.md) are displayed, as well as [VMG and ETE](NavigationVmgEte.md). Line connecting your current location and target waypoint is drawn to ease your navigation. In this mode navigation never stops, you can cancel it through Navigation menu.

# Navigation via route #

Route is simply the sequence of waypoints. Route has at least two waypoints - source and destination. Navigation therefore always begins from the second route waypoint. This gives us a concept of route leg (course). Given a course there comes out another navigation parameter: [XTK](Terms.md) - it is shown only in this mode. Total route distance left is also shown in this mode.

Navigation is proceeded to the next waypoint in two cases:
  1. when you reach proximity distance from the active waypoint
  1. when you reach the [next route leg](NavigationTraverse.md)

Navigation is stopped when you reach proximity distance from the destination (last) waypoint of the route.