Androzic supports OziExplorer datums.dat file. This file has to be placed in the Application folder (configured in Preferences). Example file can be found in Downloads section. Following is the reprint of original OziExplorer help article (with the difference that Androzic supports any number of custom datums):

# Adding User Datums #

OziExplorer can use up to 10 user defined datums.

To add User Datums to OziExplorer you need to do the following.

If it doesn't already exist Create a text file called datums.dat in the OziExplorer directory. OziExplorer will read this file the next time it is run, the user datums will always be added to the bottom of the list.

Within this file add the following line or lines (if more than 1 datum is to be added).

The format of the line is as follows :

`Datum name , Ellipsoid number , dx , dy , dz`

_Datum name_ - Any name you want to enter

_Ellipsoid number_ - All datums have a reference ellipsoid, choose the number from the list below. If the ellipsoid is not in this list then you cannot add the datum, you need to contact the author of OziExplorer and have the ellipsoid added into the code.

_dx,dy,dz_ - these must be known for the particular datum you are entering.

A comma must be used between all the fields.

Example - A line in the file may look something like this

NAD 27 User, 4, -8, 160, 176

# Ellipsoid List #

  1. : 'Airy 1830'; a : 6377563.396; invf : 299.3249646
  1. : 'Modified Airy'; a : 6377340.189; invf:299.3249646
  1. : 'Australian National'; a : 6378160.0; invf: 298.25
  1. : 'Bessel 1841'; a : 6377397.155; invf:299.1528128
  1. : 'Clarke 1866'; a : 6378206.4; invf: 294.9786982
  1. : 'Clarke 1880'; a : 6378249.145; invf:293.465
  1. : 'Everest (India 1830)'; a : 6377276.345; invf:300.8017
  1. : 'Everest (1948)'; a : 6377304.063; invf:300.8017
  1. : 'Modified Fischer 1960'; a : 6378155.0; invf: 298.3
  1. : 'Everest (Pakistan)'; a : 6377309.613; invf:300.8017
  1. : 'Indonesian 1974'; a : 6378160.0; invf: 298.247
  1. : 'GRS 80'; a : 6378137.0; invf: 298.257222101
  1. : 'Helmert 1906'; a : 6378200.0; invf: 298.3
  1. : 'Hough 1960'; a : 6378270.0; invf: 297.0
  1. : 'International 1924'; a : 6378388.0; invf: 297.0
  1. : 'Krassovsky 1940'; a : 6378245.0; invf: 298.3
  1. : 'South American 1969'; a : 6378160.0; invf: 298.25
  1. : 'Everest (Malaysia 1969)'; a : 6377295.664; invf:300.8017
  1. : 'Everest (Sabah Sarawak)'; a : 6377298.556; invf:300.8017
  1. : 'WGS 72'; a : 6378135.0; invf: 298.26
  1. : 'WGS 84'; a : 6378137.0; invf: 298.257223563
  1. : 'Bessel 1841 (Namibia)'; a : 6377483.865; invf:299.1528128
  1. : 'Everest (India 1956)'; a : 6377301.243; invf:300.8017
  1. : 'Clarke 1880 Palestine'; a: 6378300.789; invf:293.466
  1. : 'Clarke 1880 IGN'; a: 6378249.2; invf:293.466021
  1. : 'Hayford 1909'; a: 6378388.0; invf:296.959263
  1. : 'Clarke 1858';a:6378350.87;invf:294.26
  1. : 'Bessel 1841 (Norway)' ; a:6377492.0176;invf:299.1528
  1. : 'Plessis 1817 (France)'; a: 6376523.0 ; invf:308.6409971
  1. : 'Hayford 1924'; a : 6378388.0; invf: 297.0