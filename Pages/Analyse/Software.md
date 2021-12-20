#

# Software Analyse

#

## Data I/O

<table style="width: 100%">
<colgroup>
    <col span="1" style="width: 20%;">
    <col span="1" style="width: 40%;">
    <col span="1" style="width: 40%;">
</colgroup>
<tr>
    <th>Blok</th>
    <th>Data input</th>
    <th>Data output</th>
</tr>
<tr>
    <td>MCU ATSAMD21G18A-AUT</td>
    <td>
        <ul>
            <li>Sensordata fijnstof, temperatuur, luchtvochtigheid en stikstofoxiden</li>
			<li>GPS NMEA0183 V4.1 protocol data</li>
			<li>LoRa module feedback</li>
        </ul>
    </td>
    <td>
		<ul>
            <li>Configuratie en aansturing sensors en modules</li>
			<li>Sensordata als JSON object, SPI</li>
        </ul>
	</td>
</tr>
<tr>
    <td>fijnstofsensor GP2Y1014AU0F</td>
    <td>
        <ul>PWM om LED aan te sturen (T = 10ms; Pw = 0.32ms)</ul>
    </td>
    <td>
		<ul>Analoge spanning pulse (Vo lezen na 0.28ms)</ul>
	</td>
</tr>
<tr>
    <td>Temperatuur en luchtvochtigheid sensor BME280</td>
    <td>
        <ul>Uit te lezen register, I²C</ul>
    </td>
    <td>
		<ul>Register data uitlezen, I²C</ul>
	</td>
</tr>
<tr>
    <td>Stikstofoxiden sensor SGP41-D-R4</td>
    <td>
        <ul>
            <li>Conditioning instructies, I²C</li>
			<li>Raw signal meting instructies, I²C</li>
			<li>Stop instructie, I²C</li>
        </ul>
    </td>
    <td>
		<ul>Meting resultaat uitlezen, I²C</ul>
	</td>
</tr>
<tr>
    <td>GPS module Grove GPS Air530</td>
    <td>
        <ul>Start en configuratie instructies, serieel UART (2.8V)</ul>
    </td>
    <td>
		<ul>GPS NMEA0183 V4.1 protocol data, serieel UART (2.8V, default 9600bps)</ul>
	</td>
</tr>
<tr>
    <td>LoRaWAN module RFM95W v2.0</td>
    <td>
        <ul>
			<li>Mode instructie, SPI</li>
			<li>Sensordata als JSON object, SPI</li>
		</ul>
    </td>
    <td>
		<ul>Sensordata als payload van max 51 bytes, TTN 868MHz +13dbM</ul>
	</td>
</tr>
<tr>
    <td>LoRaWAN ontvanger</td>
    <td>
        <ul>Sensordata als payload van max 51 bytes, TTN 868MHz +13dbM</ul>
    </td>
    <td>
		<ul>Sensor data opgedeeld in bytes in een byte array van max 51 bytes</ul>
	</td>
</tr>
<tr>
    <td>Backend Node-RED</td>
    <td>
        <ul>Sensor data opgedeeld in bytes in een byte array van max 51 bytes</ul>
    </td>
    <td>
		<ul>Sensor data bytes gedecodeerd in JSON object</ul>
	</td>
</tr>
<tr>
    <td>Database MongoDb</td>
    <td>
        <ul>Sensordata als JSON object</ul>
    </td>
    <td>
		<ul>Sensordata als JSON object</ul>
	</td>
</tr>
<tr>
    <td>GUI Port of Antwerp digital twin</td>
    <td>
        <ul>Sensordata als JSON object</ul>
    </td>
    <td>
		<ul>Weergave op een scherm</ul>
	</td>
</tr>
</table>


#

## GUI

De data van de sensors bevat een coördinaat en tijdstip van de meting voor eenvoudige weergaven op een kaart.
Zo kan de data eenvoudig geïntegreerd worden in de <a href="https://www.portofantwerp.com/en/smart-port">digital twin van de Port of Antwerp</a> en weergegeven worden in zowel 2D en 3D.
De data kan in realtime worden weergegeven, er kan genavigeerd worden door de tijd, of een exacte timestamp kan ingegeven worden.

<img src="./Pictures/Mockups/Mockup_GUI_2D.png" width="100%"><br><br>
<img src="./Pictures/Mockups/Mockup_GUI_3D.png" width="100%"><br>

<div style="page-break-after: always"></div>

<div style="page-break-after: always"></div>