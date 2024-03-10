# extra-eve-static-data

EVE ONLINE STATIC DATA FOR **PLANETS PER SYSTEM**.

## WHAT?

Planet data extracted from SDE as at 2024-Mar.

# Disclaimer

This data is sourced from CCP (their copyright notice below). I make no claims to the data. I present this data for you to use as you wish on the understanding that I offer no warranties of any kind. None. Zero. Do with this data as you wish subject to CCP terms and conditions.

# Data as CSV or SQL

## planets.csv

Planet data in CSV format using **tab separator**. Imports fine in OpenOffice or similar modern spreadsheet. Tabs make column splitting easy for coders.

First few lines look like this (massaged for this readme):

```
solarSystemID	planetID	planetName	planetTypeID	typeName	typeIconID
30000001	40000002	Tanoo I		11		Temperate	10136
30000001	40000005	Tanoo II	11		Temperate	10136
30000001	40000007	Tanoo III	2016		Barren		10135
```

## planets.sql

Planet data in MySQL format. May work fine in other SQL databases. Uses bulk inserts 500 planets at a time.

# CCP hf. Copyright Notice

EVE Online, the EVE logo, EVE and all associated logos and designs are the intellectual property of CCP hf. All artwork, screenshots, characters, vehicles, storylines, world facts or other recognizable features of the intellectual property relating to these trademarks are likewise the intellectual property of CCP hf. EVE Online and the EVE logo are the registered trademarks of CCP hf. All rights are reserved worldwide. All other trademarks are the property of their respective owners. CCP hf. has granted permission to Robin Ellis to use EVE Online and all associated logos and designs for promotional and information purposes on its website but does not endorse, and is not in any way affiliated with, Robin Ellis. CCP is in no way responsible for the content on or functioning of this data, nor can it be liable for any damage arising from the use of this data.

# Icons

Icons taken from the offical CCP image dump have been provided with sane names and optimised with [ImageOptim](https://imageoptim.com/mac).
