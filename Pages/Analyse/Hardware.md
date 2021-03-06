#

# Hardware Analyse
## Smart Objects
### Monitoring
> Dit is het enigste smart object dat in dit project gebruikt wordt. De luchtsensoren moeten enkel de luchtkwaliteit monitoren. Er wordt geen controle gedaan, er wordt ook niets geoptimaliseerd en de sensor werkt al zeker niet autonoom. Iemand moet deze sensor opzetten, en iemand moet de data dat deze sensor verzamelt interpreteren.

### Blokdiagram
<img src="./Pictures/Diagrams/SmartObject_Hardware.png" width="700px"><br>
<a href="./Pictures/Diagrams/SmartObject_Hardware.png">Full size</a><br>

---

## Specificaties

### Microcontroller

<table style="width: 100%">
<colgroup>
    <col span="1" style="width: 15%;">
    <col span="1" style="width: 30%;">
    <col span="1" style="width: 40%;">
	<col span="1" style="width: 25%;">
</colgroup>
<tr>
    <th>Naam</th>
    <th>Eigenschappen</th>
    <th>Argumentatie</th>
    <th>Data</th>
</tr>
<tr>
    <td>Microchip ATSAMD21G18A-AUT</td>
    <td>
        <ul>
            <li><b>Low-power MCU</b></li>
            <li>V<sub>cc</sub> = 1.62V - 3.63V</li>
            <li>I<sub>max</sub> = 4.7mA</li>
			<li>CORTEX-M0+PROCESSOR aan 48MHz</li>
			<li>USB naar UART aanwezig op de chip</li>
			<li>256KB FLASH geheugen</li>
			<li>32-bit RTC</li>
			<li>6 SERCOM interfaces</li>
			<li><i>Eenheidsprijs vanaf 10 stuks: €3,60</i></li>
			<li><i>Lead time: 54 weken</i></li>
        </ul>
    </td>
    <td>
		Uit het interview met de opdrachtgever gaf hij aan dat we deze MCU moeten gebruiken. Deze is low-power en dus zeer geschikt voor de applicatie.
	</td>
    <td>
		<a href="./Pages/Apendix/Datasheets/ATSAMD21G18A-AUT_SAM-D21-DA1-Family_Datasheet.pdf">Datasheet</a><br>
		<a href="https://www.microchip.com/en-us/product/ATsamd21g18#document-table style="width: 100%"">Documentatie fabrikant</a><br>
		<a href="https://www.mouser.be/ProductDetail/Microchip-Technology-Atmel/ATSAMD21G18A-AUT?qs=KLFHFgXTQiBkLYobE%2Fq9Qw%3D%3D">Winkel</a><br>
	</td>
</tr>
</table>

---

### Modules

<table style="width: 100%">
<colgroup>
    <col span="1" style="width: 15%;">
    <col span="1" style="width: 30%;">
    <col span="1" style="width: 40%;">
	<col span="1" style="width: 25%;">
</colgroup>
<tr>
    <th>Naam</th>
    <th>Eigenschappen</th>
    <th>Argumentatie</th>
    <th>Data</th>
</tr>
<tr>
    <td>Grove GPS Air530</td>
    <td>
        <ul>
            <li><b>GPS localisatie</b></li>
            <li>V<sub>cc</sub> = 3.3V / 5V</li>
            <li>I<sub>max</sub> = 60mA</li>
			<li>Capture current value@3.3V = 42.6mA</li>
			<li>Tracking current value@3.3V = 36.7mA</li>
			<li>Low power mode@3.3V = 0.85mA</li>
			<li>Ultra-low-power mode@3.3V = 31uA</li>
            <li>UART protocol</li>
			<li>Time of warm start: 4s</li>
			<li>Time of cold boot: 30s</li>
			<li><i>Eenheidsprijs vanaf 10 stuks: €8,98</i></li>
			<li><i>Lead time: 11 weken</i></li>
        </ul>
    </td>
    <td>
		Deze GPS module is zeer energie zuinig met verschillende low-power modi. Ze is ook relatief goedkoop en werkt op 3.3V.
	</td>
    <td>
		<a href="./Pages/Apendix/Datasheets/Air530-GPS_Manual_Text_English.pdf">Handleiding</a><br>
		<a href="https://wiki.seeedstudio.com/Grove-GPS-Air530/">Documentatie fabrikant</a><br>
		<a href="https://www.seeedstudio.com/Grove-GPS-Air530-p-4584.html">Winkel (fabrikant)</a><br>
		<a href="https://www.mouser.be/new/seeed-studio/seeedstudio-grove-gps-air530-module/">Winkel</a><br>
		<a href="./Pages/Apendix/Datasheets/Air530_GPS_User_Booklet.V1.7(Chinese).pdf">Booklet (Chinese)</a><br>
	</td>
</tr>
<tr>
    <td>HopeRF RFM95W-868S2 868MHz v2.0 LoRa Module</td>
    <td>
        <ul>
            <li><b>LoRaWAN module</b></li>
            <li>V<sub>cc</sub> = 1.8V - 3.7V</li>
            <li>I<sub>+13dBm(Typ)</sub> = 29mA</li>
			<li>P<sub>output</sub> = +13dBm</li>
			<li>SPI interface</li>
			<li>Payload lenght max 64 bytes</li>
			<li>Werkingstemperatuur: -20°C ~ +70°C</li>
			<li>Operating band: 868MHz</li>
			<li><i>Eenheidsprijs vanaf 10 stuks: €16,36</i></li>
			<li><i>Lead time: 17 weken</i></li>
        </ul>
    </td>
    <td>
		Een veel gebruikte module waardoor er veel documentatie over te vinden is. Ook relatief klein.
	</td>
    <td>
		<a href="./Pages/Apendix/Datasheets/HopeRF_RFM95W-V2.0_Datasheet.pdf">Datasheet</a><br>
		<a href="https://www.hoperf.com/modules/lora/RFM95.html">Documentatie fabrikant</a><br>
		<a href="https://www.mouser.be/ProductDetail/RF-Solutions/RFM95W-868S2?qs=sGAEpiMZZMu3sxpa5v1qriuzrjO9DfPi5Wv3OoHC154%3D">Winkel</a><br>
	</td>
</tr>
</table>

---

### Sensoren

<table style="width: 100%">
<colgroup>
    <col span="1" style="width: 15%;">
    <col span="1" style="width: 30%;">
    <col span="1" style="width: 40%;">
	<col span="1" style="width: 25%;">
</colgroup>
<tr>
    <th>Naam</th>
    <th>Eigenschappen</th>
    <th>Argumentatie</th>
    <th>Data</th>
</tr>
<tr>
    <td>Sharp GP2Y1014AU0F</td>
    <td>
        <ul>
            <li><b>Fijnstof</b></li>
            <li>V<sub>cc</sub> = 4.5V - 5.5V</li>
            <li>I<sub>max</sub> = 20mA</li>
            <li>Analoog</li>
            <li>Output voltage: 0.9~3.7V (zie grafiek)</li>
            <li>Meetbereik PM2.5 en PM10: 0~50µg/m3 (zie grafiek)</li>
			<li><i>Eenheidsprijs vanaf 10 stuks: €6,25</i></li>
			<li><i>Lead time: 53 weken</i></li>
        </ul>
    </td>
    <td>
		De Nova SDS011 die bij de As-Is sensor gebruikt wordt heeft als grote nadeel dat er een FAN zit ingebouwd om lucht in de sensor te krijgen. Dit zorgt voor extra stroomverbruik en werkte in het prototype daarbij nog is niet voldoende.
		De Sharp GP2Y1010AU0F komt uit test op vlak van accuraatheid even goed uit als de SDS011, maar heeft het voordeel van geen FAN te hebben, kleiner te zijn, energiezuiniger en goedkoper.
	</td>
    <td>
		<a href="./Pages/Apendix/Datasheets/Sharp-GP2Y1014AU0F_nieuwere-versie-itteratie-GP2Y1010AU0F.pdf">Datasheet GP2Y1014AU0F</a><br>
		<a href="./Pages/Apendix/Datasheets/Sharp-GP2Y1010AU0F.pdf">Datasheet voorganger GP2Y1010AU0F</a><br>
		<a href="./Pages/Apendix/Datasheets/Sharp-GP2Y1010AU0F_Application-notes.pdf">Application notes GP2Y1010AU0F</a><br>
		<a href="http://global.sharp/products/device/lineup/selection/opto/dust/index.html">Documentatie fabrikant</a><br>
		<a href="https://www.mouser.be/ProductDetail/Sharp-Microelectronics/GP2Y1014AU0F?qs=rrS6PyfT74eynj5J61tvwA%3D%3D">Winkel</a><br>
	</td>
</tr>
<tr>
    <td>Bosch Sensortec BME280</td>
    <td>
        <ul>
            <li><b>Temperatuur, barometer en luchtvochtigheid</b></li>
            <li>V<sub>cc</sub> = 3.3V</li>
            <li>I<sub>max</sub> = 4.5mA</li>
            <li>I²C protocol 3.3V, en SPI</li>
            <li>Meetbereik temperatuur: -40°C ~ +85°C</li>
            <li>Meetbereik luchtvochtigheid: 0% ~ 100%</li>
			<li>Meetbereik luchtdruk: 300hPa ~ 1100hPa</li>
			<li>Leessnelheid: 1Hz (1s)</li>
			<li><i>Eenheidsprijs vanaf 10 stuks: €5,42</i></li>
			<li><i>Lead time: tijdelijk beperkt aanbod op moment van schrijven</i></li>
        </ul>
    </td>
    <td>
		Deze IC heeft als voordeel beide temperatuur en luchtvochtigheid te meten. Het is ook een SMD component dus eenvoudig op een PCB te krijgen. Hier moet wel rekening gehouden worden met de warmte ontwikkeling van andere componenten die de temperatuur metingen kunnen beïnvloeden.
	</td>
    <td>
		<a href="./Pages/Apendix/Datasheets/BoschSensortec-BME280_Datasheet.pdf">Datasheet</a><br>
		<a href="https://www.bosch-sensortec.com/products/environmental-sensors/humidity-sensors-bme280/">Documentatie fabrikant</a><br>
		<a href="https://www.mouser.be/ProductDetail/Bosch-Sensortec/BME280?qs=2OnyuXx6vpj2fK9HX7qb3g%3D%3D">Winkel</a><br>
	</td>
</tr>
<tr>
    <td>Sensirion SGP41-D-R4</td>
    <td>
        <ul>
            <li><b>NO<sub>X</sub> en VOC</b></li>
            <li>V<sub>cc</sub> = 1.7V - 3.6V</li>
			<li>Werkvoedingsspanning = 3.3V</li>
            <li>I<sub>max</sub> = 4.6mA</li>
			<li>I<sub>nominaal</sub> = 3.2mA</li>
            <li>I²C interface</li>
            <li>Meetbereik NO<sub>2</sub>: 0-10.000ppb</li>
			<li>Werkingstemperatuur: -20°C ~ +55°C</li>
			<li>SMD</li>
			<li><i>Eenheidsprijs vanaf 10 stuks: €7,46</i></li>
			<li><i>Lead time: 16 weken</i></li>
        </ul>
    </td>
    <td>
		Klein low-power SMD component Ideaal voor deze toepassing
	</td>
    <td>
		<a href="./Pages/Apendix/Datasheets/Sensirion-SGP41-D-R4_Datasheet.pdf">Datasheet</a><br>
		<a href="https://www.sensirion.com/en/environmental-sensors/gas-sensors/sgp40/">Documentatie fabrikant</a><br>
		<a href="https://www.mouser.be/ProductDetail/Sensirion/SGP41-D-R4?qs=A6eO%252BMLsxmRqwfOE5NYPVA%3D%3D">Winkel</a><br>
	</td>
</tr>
</table>

---
	
### Voeding

Zoals bij de As-Is sensor gebruikt dit project ook onderdelen die werken op 3.3V en op 5V.<br>
Voor 5V is er slechts één, de Sharp GP2Y1014AU0F met I<sub>max</sub> = <b>20mA</b>.<br>
Voor de 3.3V componenten moet een herberekening gedaan worden:<br>

> Herberekeningen voor 3.3V <br>
I<sub>max</sub> = I<sub>ATSAMD21G18A-AUT</sub> + I<sub>BME280</sub> + I<sub>SGP41</sub> + I<sub>Grove GPS Air530</sub> + I<sub>RFM95W LoRa</sub> <br>
I<sub>max</sub> = 4.7mA + 4.5mA + 4.6mA + 60mA + 29mA = 102.8mA <br>
Om wat marge te hebben doen we deze waarde maal <i>1.2</i> :<br> 102.8mA • 1.2 = <b>123.4mA</b>

De spanningsvereisten liggen dit maal dus een stuk lager:

> Voor 5V <b>20mA</b> To-Be tegenover <b>390mA</b> As-Is.<br>
Voor 3.3V <b>123.4mA</b> To-Be tegenover <b>822.6mA</b> As-Is.

<table style="width: 100%">
<colgroup>
    <col span="1" style="width: 15%;">
    <col span="1" style="width: 30%;">
    <col span="1" style="width: 40%;">
	<col span="1" style="width: 25%;">
</colgroup>
<tr>
    <th>Naam</th>
    <th>Eigenschappen</th>
    <th>Argumentatie</th>
    <th>Data</th>
</tr>
<tr>
    <td>EEMB LP103395</td>
    <td>
        <ul>
            <li><b>Batterij</b></li>
            <li>V<sub>out</sub> = 3.7V</li>
            <li>I<sub>max</sub> = 2A</li>
			<li>I<sub>h</sub>   = 3700mAh</li>
            <li>Operating Temperatuur = -20~60</li>
			<li><i>Eenheidsprijs vanaf 10 stuks: €16,99</i></li>
			<li><i>Lead time: onbekend</i></li>
        </ul>
    </td>
    <td>
		Deze batterij is makkelijk verkrijgbaar en is relatief goedkoop. Deze batterij heeft een hoog aantal mAh tegenover de prijs.
	</td>
    <td>
		<a href="./Pages/Apendix/Datasheets/EEMB_LP103395.pdf">Datasheet</a><br>
		<a href="">Documentatie fabrikant</a><br>
		<a href="https://www.amazon.com/EEMB-3700mAh-Rechargeable-Connector-Certified/dp/B08215B4KK">Winkel</a><br>
	</td>
</tr>
<tr>
    <td>LTC3200ES6</td>
    <td>
        <ul>
            <li><b>5V Voltage Regulator</b></li>
            <li>V<sub>in</sub> = 2.7V~4.5V</li>
            <li>V<sub>out</sub> = 5V</li>
            <li>I<sub>max</sub> = 150mA</li>
            <li>Operating Temperatuur = -40~85</li>
			<li><i>Eenheidsprijs vanaf 10 stuks: €3,89</i></li>
			<li><i>Lead time: 39 weken</i></li>
        </ul>
    </td>
    <td>
		Deze voltage regulator is een SMD component dat op een groot bereik aan temperatuur kan werken. Daarbovenop valt Vin mooi samen met Vout van de batterij
	</td>
    <td>
		<a href="./Pages/Apendix/Datasheets/LTC3200.pdf">Datasheet</a><br>
		<a href="">Documentatie fabrikant</a><br>
		<a href="https://eu.mouser.com/ProductDetail/Analog-Devices/LTC3200ES6-5TRPBF?qs=hVkxg5c3xu8FsASPkjrjjA%3D%3D">Winkel</a><br>
	</td>
</tr>
<tr>
    <td>AP7343D-33W5-7</td>
    <td>
        <ul>
            <li><b>3.3V Voltage Regulator</b></li>
            <li>V<sub>in</sub> = 1.7V~5.25V</li>
            <li>V<sub>out</sub> = 3.3V</li>
            <li>I<sub>max</sub> = 300mA</li>
            <li>Operating Temperatuur = -40~85</li>
			<li><i>Eenheidsprijs vanaf 10 stuks: €0,332</i></li>
			<li><i>Lead time: 68 weken</i></li>
        </ul>
    </td>
    <td>
		Deze regulator werkt goed samen met de batterij die gekozen werd. Het is ook een SMD component dat op een groot bereik aan temperatuur kan werken.
	</td>
    <td>
		<a href="./Pages/Apendix/Datasheets/AP7343D.pdf">Datasheet</a><br>
		<a href="">Documentatie fabrikant</a><br>
		<a href="https://eu.mouser.com/ProductDetail/Diodes-Incorporated/AP7343D-33W5-7?qs=EDJ299gKAZQ2xV9YzJ9Zog%3D%3D">Winkel</a><br>
	</td>
</tr>
<tr>
    <td>2N7002K-7</td>
    <td>
        <ul>
            <li><b>MOSFET</b></li>
            <li>V<sub>GS(th)</sub> = 1 - 2.5V</li>
            <li>V<sub>DDS(max)</sub> = 60V</li>
            <li>I<sub>max</sub> = 380mA</li>
			<li>SOT-23</li>
			<li><i>Eenheidsprijs vanaf 10 stuks: €0,169</i></li>
			<li><i>Lead time: 89 weken</i></li>
        </ul>
    </td>
    <td>
		De 2N7002K-7 zal gebruikt worden om de modules en sensoren, zonder sleep mode, uit te zetten tijdens de intervallen. (Overgenomen van As-Is)
	</td>
    <td>
		<a href="./Pages/Apendix/Datasheets/MOSFET-2N7002K-7_Datasheet.pdf">Datasheet</a><br>
		<a href="https://www.diodes.com/part/view/2N7002K">Documentatie fabrikant</a><br>
		<a href="https://www.mouser.be/ProductDetail/Diodes-Incorporated/2N7002K-7?qs=rGAXPo9uwV0%2Fp9r5KJ7huA%3D%3D">Winkel</a><br>
	</td>
</tr>
</table>

<br>

---

## Elektrisch Schema

<img src="./Pictures/Diagrams/Elektrisch_schema.png" width="100%"><br>
<a href="./Pictures/Diagrams/Elektrisch_schema.sch">Schematic File</a><br>

---
