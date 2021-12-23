#

# Design

## Functioneel design
- Component selectie:
>	- microcontroller: I<sub>max</sub> < 10mA
>	- GPS module: low-power I<sub>max</sub> < As-Is 67mA
>	- LoRaWAN module: zendbereik hele haven over 12.068 ha = 120.680 km²
>	- fijnstofsensor: PM2.5 en PM10 concentratie, meetbereik 0-40 µg/m3
>	- temperatuur sensor: meetbereik -20° ~ +42° (<a href="https://www.frankdeboosere.be/vragen/vraag53.php#:~:text=De%20hoogste%20maximumtemperatuur%20werd%20die,%3A%20MIN%2030%2C1%20graden.">kouste en warmste meting in België</a>)<br>
>	- luchtvochtigheid sensor: meetbereik 0% ~ 100% (<a href="https://www.eurabo.be/nl/lexicon/relatieve-vochtigheid">relatieve luchtvochtigheid</a>)<br>
>	- NO<sub>X</sub> sensor: concentratie, meetbereik 0-40 µg/m3
- Behuizing die in openlucht kan geplaatst worden en bestand is tegen het lokale klimaat.
- Behuizing die voor voldoende koeling zorgt zodat de temperatuur metingen accuraat zijn.
- Behuizing die voor voldoende lucht toevoer zorgt aan de fijnstofsensor.
- Schroefdraad in behuizing als bevestigingspunt voor een ophangsysteem.
- De sensor moet automatisch om de .. minuten metingen uitvoeren en verzenden (er is geen interactie).
- Sensor output als JSON data:
>	- locatie: GPS coördinaat van de sensor
>	- timestamp: datum en tijd van de meting
>	- temperatuur in °C
>	- luchtvochtigheid in %
>	- fijnstof PM2.5 en PM10 in aantal deeltjes
>	- NO<sub>X</sub> stikstofoxiden in µg/m3
- Server met database om de sensor data in op te slaan en van op te vragen.
- Weergave van de sensordata in GUI digital twin van de Port of Antwerp.

<div style="page-break-after: always"></div>

#

## Technisch design

### Technologieën
<table style="width: 100%">
<colgroup>
    <col span="1" style="width: 20%;">
    <col span="1" style="width: 20%;">
    <col span="1" style="width: 60%;">
</colgroup>
<tr>
    <th>Onderdeel</th>
    <th><b>Technologie</b></th>
    <th>Argumentatie</th>
</tr>
<!--<tr>
    <td>Onderdeel</td>
    <td><b>Technologie</b></td>
	<td>Argumentatie</td>
</tr>-->
<tr>
    <td>Backend code</td>
    <td><b>Node-RED</b></td>
    <td>Node-RED is een stroomgebaseerde ontwikkeltool voor visuele programmering. Dit wordt al gebruikt in de As-Is situatie. Het is dus tijd en werk besparend om hiermee verder te werken.</td>
</tr>
<tr>
    <td>Database</td>
    <td><b>MongoDB</b></td>
	<td>MongoDB is een opensource document-georiënteerde database waarin documenten als BSON (Binary-JSON) wordt opgeslagen. Ideaal voor het werken met JSON bestanden, en ook wat in de As-Is situatie gebruikt wordt.</td>
</tr>
<tr>
    <td>Web API</td>
    <td><b>Python Flask</b></td>
	<td>
		Flask is een light-weight web framework in Python. Hiermee kan je zelf bepalen welke componenten en extension je wilt gebruiken voor de API.
		Wij gebruiken (<a href="https://towardsdatascience.com/creating-a-beautiful-web-api-in-python-6415a40789af">tutorial</a>):<br>
		<ul>
			<li><b>MongoEngine</b> voor het omgaan met MongoDB in een objectgeoriënteerde manier.</li>
			<li><b>Bcrypt</b> voor encryptie.</li>
			<li><b>RESTful</b> voor een REST API aan te maken.</li>
			<li><b>JWT-Extended</b> voor authenticatie en autorisatie.</li>
		</ul>
	</td>
</tr>
<tr>
    <td>Frontend</td>
    <td><b>Digital twin Port of Antwerp</b></td>
	<td>Deze wordt momenteel ontwikkeld en is ideaal om onze sensordata in weer te geven.</td>
</tr>

</table>

### Technisch realisatieproces prototype
1. Aankopen en testen van de componenten. Het testen van de sensors en modules kan met een Arduino gebeuren. Dit om eventuele moeilijkheden met de microcontroller hiervan los te koppelen.
2. De PCB en behuizing ontwerpen in Fusion 360 samen met de sensor plaatsing onderzoeken. Dit met oog op zo accuraat mogelijke metingen te bekomen en onderlinge invloeden te minimaliseren.
3. PCB ontwerp bestellen en testen. De behuizing 3D printen en testen.
4. Code ontwikkelen om de metingen uit te voeren.
5. Code ontwikkelen om de sensordata te verzenden met LoRaWAN.
6. Backend ontwikkelen met Node-RED om de sensordata te ontvangen en op te slaan in een MongoDB database.
7. Het gehele proces van metingen uitvoeren en de sensordata te verzenden en ontvangen automatiseren.
8. API ontwikkelen om de sensordata uit de database op te vragen, aanspreekbaar door de digital twin van de Port of Antwerp.

<div style="page-break-after: always"></div>