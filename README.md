# extra-eve-static-data

EVE ONLINE STATIC DATA FOR PLANETS PER SYSTEM.

## WHAT?

CCP issues static data roughly once per month. One dataset not in there - despite being very static indeed - is the list of planets for each system. There are also moons and asteroid belts per system and these are also not included in the static data dump. Lazy? Possibly.

Planet data can be found though the CCP Swagger interface [here](https://esi.evetech.net/ui/?version=latest#) which is fine I guess for a casual frontend making the odd call for some data. It is total arse for serious work with planets and requires thousands of calls to get (known) K-space and even more calls to get J-space for wormholes, not to mention the irrelevant dev/test-only systems that are not necessary for the regular player.

Approximate number of calls made to the Swagger API: 58,905. List of systems; each system; each planet; each type noted by a planet.

So, given it is likely CCP have de-prioritised their efforts to provide full static data, I decided to hit that Swagger API like a boss. It took a while from my slow Asia connection (big up Anajak Khmai). I hope to integrate this data as system trivia on [EVEMissioneer](https://EVEMissioneer.com).

# Disclaimer

This data is sourced from CCP (their copyright notice below). I make no claims to this data. I present this data for you to use as you wish on the understand that I offer no warranties of any kind. None. Zero. Do with this data as you wish subject to CCP terms.

# Data as CSV or SQL

## First: systems not included

* Any system id >= 31000001 including wormhole J-Space

* Any system where constellation id >= 21000001

* Any system where constellation id in range 20000047 to 20000062 inclusive (to exclude region `UUA-F4`)

Some planet data might have crept in before I got the filtering 100% but it meets my definition of "ok".

## planets.csv

Planet data in CSV format using **tab separator**. Imports fine in OpenOffice or similar modern spreadsheet. Tabs make column splitting easy for coders.

First few lines look like this (massaged for this readme):

```
solarSystemID	planetID	planetName	planetTypeID	typeName	typeIconID
30000001	40000002	Tanoo I		11		Temperate	10136
30000001	40000005	Tanoo II	11		Temperate	10136
30000001	40000007	Tanoo III	2016		Barren		10135
```

## mapPlanets.sql

Planet data in MySQL format. May work fine in other SQL databases. Inserts are bulked by system and there are over 5000 of them.

# CCP hf. Copyright Notice

EVE Online, the EVE logo, EVE and all associated logos and designs are the intellectual property of CCP hf. All artwork, screenshots, characters, vehicles, storylines, world facts or other recognizable features of the intellectual property relating to these trademarks are likewise the intellectual property of CCP hf. EVE Online and the EVE logo are the registered trademarks of CCP hf. All rights are reserved worldwide. All other trademarks are the property of their respective owners. CCP hf. has granted permission to Robin Ellis to use EVE Online and all associated logos and designs for promotional and information purposes on its website but does not endorse, and is not in any way affiliated with, Robin Ellis. CCP is in no way responsible for the content on or functioning of this data, nor can it be liable for any damage arising from the use of this data.
