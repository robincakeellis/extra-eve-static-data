# extra-eve-static-data

EVE ONLINE STATIC DATA FOR **PLANETS PER SYSTEM**.

## WHAT?

CCP issues static data roughly once per month. One dataset not in there - despite being very static indeed - is the list of planets for each system. There are also moons and asteroid belts per system and these are also not included in the static data dump.

Planet data can be found through the CCP Swagger interface [here](https://esi.evetech.net/ui/?version=latest#) which is fine I guess for a casual frontend making the odd call for some data. It is total arse for serious work with planets and requires thousands of calls to get regular K-space and even more calls to get wormhole J-space, not to mention the irrelevant dev/test-only systems that are not necessary for the regular player.

So, given it is likely CCP have de-prioritised their efforts to provide full static data, I decided to hit that Swagger API like a boss. It took a while from my slow Asian connection (big up Anajak Khmer). I hope to integrate this data as system trivia on [EVEMissioneer](https://EVEMissioneer.com).

Approximate number of calls that made to the Swagger API: 53,677. (List of systems; each system; each planet for valid K-space system; and the nine types of planet).

# Disclaimer

This data is sourced from CCP (their copyright notice below). I make no claims to the data. I present this data for you to use as you wish on the understanding that I offer no warranties of any kind. None. Zero. Do with this data as you wish subject to CCP terms and conditions.

# Data as CSV or SQL

## First: systems not included

* Any system id >= 31000001 including wormhole J-Space

* Any system where constellation id >= 21000001

* Any system where constellation id in range 20000047 to 20000062 inclusive (to exclude region `UUA-F4`)

Some planet data might have crept in before I got the filtering 100% but quality meets my definition of "ok".

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

# Stats

## Systems

Systems 8435
J-space 2603
DevTest 401
UUA-F4  107
K-space 5324

## Planets in K-space

No planets 0
1 planet 8
2 planets 15
3 planets 25
4 planets 78
5 planets 207
6 planets 463
7 planets 806
8 planets 1095
9 planets 1062
10 planets 738
11 planets 457
12 planets 239
13 planets 91
14 planets 30
15 planets 6
16 planets 3
17 planets 0
18 planets 1
