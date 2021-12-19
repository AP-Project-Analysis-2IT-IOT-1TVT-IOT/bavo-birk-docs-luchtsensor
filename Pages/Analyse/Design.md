#

# Design

## Functioneel design
- component selectie+:
	- microcontroller: I<sub>max</sub> < 10mA
	- GPS module: low-power I<sub>max</sub> < As-Is 67mA
	- LoRaWAN module: zendbereik hele haven over 12.068 ha = 120.680 km²
	- fijnstof sensor: PM2.5 en PM10 concentratie, meetbereik 0-40 µg/m3
	- temperatuur sensor: meetbereik -20° ~ +42° (<a href="https://www.frankdeboosere.be/vragen/vraag53.php#:~:text=De%20hoogste%20maximumtemperatuur%20werd%20die,%3A%20MIN%2030%2C1%20graden.">kouste en warmste meting in België</a>)<br>
	- luchtvochtigheid sensor: meetbereik 0% ~ 100% (<a href="https://www.eurabo.be/nl/lexicon/relatieve-vochtigheid">relatieve luchtvochtigheid</a>)<br>
	- NO<sub>X</sub> sensor: concentratie, meetbereik 0-40 µg/m3
- behuizing die in openlucht kan geplaatst worden en bestand is tegen het lokale klimaat
- behuizing die voor voldoende koeling zorgt zodat de temperatuur metingen accuraat zijn
- behuizing die voor voldoende lucht toevoer zorgt aan de fijnstof sensor
- schroefdraad in behuizing als bevestigingspunt voor een ophangsysteem
- de sensor moet automatisch om de .. minuten metingen uitvoeren en verzenden (er is geen interactie)
- sensor output als JSON data:
	- locatie: GPS coördinaat van de sensor
	- timestamp: datum en tijd van de meting
	- temperatuur in °C
	- luchtvochtigheid in %
	- fijnstof PM2.5 en PM10 in aantal deeltjes
	- NO<sub>X</sub> stikstofoxiden in µg/m3
- server met MongoDb database om de sensor data in op te slaan

<div style="page-break-after: always"></div>

#

## Technisch design

<div style="page-break-after: always"></div>