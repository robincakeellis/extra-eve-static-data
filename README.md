# extra-eve-static-data

## WHAT?

CCP issues static data roughly once per month. One dataset not in there - despite being very static indeed - is the list of planets for each system. There are also moons and asteroid belts and these are also not present in the static data dump.

The data is in the CCP Swagger interface [here](https://esi.evetech.net/ui/?version=latest#) which is fine I guess for a casual frontend making the odd call for some data. It is total arse for serious work with planets and requires thousands of calls to get (known) K-space and even more calls to get J-space for wormholes, not to mention the irrelevant dev/test-only systems that are not necessary for the regular player.

So, given it is likely CCP have de-prioritised their efforts to provide full static data, I decided to hit that Swagger API like a boss so you do not have to it. It took a while from my slow Asia connection (big up Anajak Khmai).


## Systems not included

* Any system id >= 31000001 including Wormhole J-Space

* Any where constellation id >= 21000001

* Any where constellation id in range 20000047 to 20000062 inclusive (for region `UUA-F4`)


## planets.csv

Planet data in CSV format using **tab separator** that imports fine in OpenOffice or similar modern spreadsheet. Tabs make column splitting easy for coders.

First few lines look like this (massaged for this readme):

```
solarSystemID	planetID	planetName	planetTypeID	typeName		typeIconID
30000001	40000002	Tanoo I		11		Temperate	10136
30000001	40000005	Tanoo II	11		Temperate	10136
30000001	40000007	Tanoo III	2016		Barren		10135
```


## mapPlanets.sql

Planet data in MySQL format. May work fine in other SQL databases. Inserts are bulked by system and there are over 5000 of them.