Androzic can open waypoint files in KML format. But it is not so obvious how to save points from Google My Maps to KML file.

**First approach:** right click 'View in Google Earth' link and copy the link to the clipboard, paste this into the address bar but change the `output=nl` to `output=kml` in the copied link, press Go (`Enter` or whatever will open this link). You will be prompted to save a file.

**Second approach:** The 'View in Google Earth' rightly produces a KML file, which when opened in Google Earth displays your map, but this KML file does not contain your points, it's just a link to another KML file. This is done so that if you update the map on Google Maps, Google Earth can actully refetch the content so that changes are visible. If you open the file with a plain text editor (like Notepad) it looks something like this:

```
<?xml version="1.0" encoding="UTF-8"?>
<kml xmlns="http://earth.google.com/kml/2.2">
<Document>
  <name>My Map</name>
  <description><![CDATA[]]></description>
  <NetworkLink>
    <name>My Map</name>
    <Link>
      <href>http://maps.google.com/maps/ms?ie=UTF8&amp;hl=en&amp;vps=1
&amp;jsv=308a&amp;oe=UTF8&amp;msa=0&amp;msid=211780268319784512310
.0004882e3063f1f9b2026&amp;output=kml</href>
    </Link>
  </NetworkLink>
</Document>
</kml>
```

There you can see the link (included in `<href></href>`) which contains `output=kml` that gets the actual data. But pay attention to `&amp;`'s in the URL - the file is actully in XML format so `&` in the url need to be replaced with `&amp;`. So before copy/pasting the link in the browser you need to replace them back (use Edit|Replace in editor not to make mistakes). So the above link actually becomes:
`http://maps.google.com/maps/ms?ie=UTF8&amp;hl=en&amp;vps=1&jsv=308a&oe=UTF8&msa=0&msid=211780268319784512310.0004882e3063f1f9b2026&output=kml`