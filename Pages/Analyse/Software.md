#

# Software Analyse

### Data I/O

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
    <td>MCU: Microship ATSAMD21G18A-AUT</td>
    <td>
        <ul>
            <li>Sensordata fijnstof, temperatuur, luchtvochtigheid en stikstofoxiden, <b>I²C, Analoog</b></li>
			<li>GPS NMEA0183 V4.1 protocol data, <b>UART</b></li>
			<li>LoRa module feedback, <b>SPI</b></li>
        </ul>
    </td>
    <td>
		<ul>
            <li>Configuratie en aansturing sensors en modules, <b>serieel UART, I²C, PWM, SPI</b></li>
			<li>Sensordata als JSON object, <b>SPI</b></li>
        </ul>
	</td>
</tr>
<tr>
    <td>Fijnstofsensor: Sharp GP2Y1014AU0F</td>
    <td>
        <ul>PWM om LED aan te sturen (T = 10ms; Pw = 0.32ms), <b>PWM</b></ul>
    </td>
    <td>
		<ul>Analoge spanning pulse (Vo lezen na 0.28ms), <b>Analoog</b></ul>
	</td>
</tr>
<tr>
    <td>Temperatuur en luchtvochtigheid sensor: Bosch Sensortec BME280</td>
    <td>
        <ul>Uit te lezen register, <b>I²C</b></ul>
    </td>
    <td>
		<ul>Register data uitlezen, <b>I²C</b></ul>
	</td>
</tr>
<tr>
    <td>Stikstofoxiden sensor: Sensirion SGP41-D-R4</td>
    <td>
        <ul>
            <li>Conditioning instructies, <b>I²C</b></li>
			<li>Raw signal meting instructies, <b>I²C</b></li>
			<li>Stop instructie, <b>I²C</b></li>
        </ul>
    </td>
    <td>
		<ul>Meting resultaat uitlezen, <b>I²C</b></ul>
	</td>
</tr>
<tr>
    <td>GPS module: Seeed Studio Grove-GPS Air530</td>
    <td>
        <ul>Start en configuratie instructies, <b>serieel UART</b> (2.8V)</ul>
    </td>
    <td>
		<ul>GPS NMEA0183 V4.1 protocol data, <b>serieel UART</b> (2.8V, default 9600bps)</ul>
	</td>
</tr>
<tr>
    <td>LoRaWAN module: HopeRF RFM95W v2.0</td>
    <td>
        <ul>
			<li>Mode instructie, <b>SPI</b></li>
			<li>Sensor data opgedeeld in bytes, byte array van max 51 bytes, <b>SPI</b></li>
		</ul>
    </td>
    <td>
		<ul>Sensordata als payload van max 51 bytes, <b>TTN 868MHz +13dbM</b></ul>
	</td>
</tr>
<tr>
    <td>LoRaWAN ontvanger</td>
    <td>
        <ul>Sensordata als payload van max 51 bytes, <b>TTN 868MHz +13dbM</b></ul>
    </td>
    <td>
		<ul>Sensor data opgedeeld in bytes, byte array van max 51 bytes, <b>netwerk</b></ul>
	</td>
</tr>
<tr>
    <td>Backend: Node-RED</td>
    <td>
        <ul>Sensor data opgedeeld in bytes, byte array van max 51 bytes, <b>netwerk</b></ul>
    </td>
    <td>
		<ul>Sensor data bytes gedecodeerd in JSON object, <b>netwerk</b></ul>
	</td>
</tr>
<tr>
    <td>Database: MongoDb</td>
    <td>
        <ul>Sensordata als JSON object, <b>netwerk</b></ul>
    </td>
    <td>
		<ul>Sensordata als JSON object, <b>netwerk</b></ul>
	</td>
</tr>
<tr>
    <td>Web API: Pyhton Flask</td>
    <td>
        <ul>Sensordata als JSON object, <b>netwerk</b></ul>
    </td>
    <td>
		<ul>Sensordata als JSON object, <b>HTTP respons</b></ul>
	</td>
</tr>
<tr>
    <td>GUI: Port of Antwerp digital twin</td>
    <td>
        <ul>Sensordata als JSON object, <b>HTTP request</b></ul>
    </td>
    <td>
		<ul>Weergave op scherm</ul>
	</td>
</tr>
</table>

#### Blok diagram

<img src="./Pictures/Diagrams/To-Be_BlockDiagram.png" width="100%">

---

<div style="page-break-after: always"></div>

#

## Smart Object

Het Smart Object is de sensor zelf.

### Smart Object Statediagram

<img src="./Pictures/Diagrams/SmartObject_Statediagram.png"><br>

---

<div style="page-break-after: always"></div>

# 

### Smart Object Flowcharts

##### 1. MCU boot
<img src="./Pictures/Diagrams/SmartObject_FlowChart-01_MCUboot.png"><br>

---

##### 2. Get GPS location
<img src="./Pictures/Diagrams/SmartObject_FlowChart-02_GetGPSlocation.png"><br>

---

##### 3. Standby
<img src="./Pictures/Diagrams/SmartObject_FlowChart-03_Standby.png"><br>

---

##### 4. Get sensordata
<img src="./Pictures/Diagrams/SmartObject_FlowChart-04_GetSensordata.png"><br>

---

##### 5. Send data
<img src="./Pictures/Diagrams/SmartObject_FlowChart-05_SendData.png"><br>

---

<div style="page-break-after: always"></div>

#

## Backend

De backend is het gedeelte dat achter de schermen gebeurt vanaf ontvangst van de sensordata.

### Backend Statediagram

<img src="./Pictures/Diagrams/Backend_Statediagram.png"><br>

---

<div style="page-break-after: always"></div>

# 

### Backend Flowcharts

<img src="./Pictures/Diagrams/Flowchart_01.png"><br>

---

<div style="page-break-after: always"></div>

#

## Graphical User Interface

De sensordata bevat een GPS coördinaat en tijdstip van de meting voor eenvoudige weergaven op een kaart.
Zo kan de data eenvoudig worden opgevraagd via een API en geïntegreerd worden in de <a href="https://www.portofantwerp.com/en/smart-port">digital twin van de Port of Antwerp</a>.<br>

De data kan in realtime worden weergegeven, er kan genavigeerd worden door de tijd, of een exacte timestamp kan ingegeven worden.
Dit zowel op een 2D kaart als in een 3D nabootsing van de haven.

In dit onderdeel wordt enkel de nodige werking voor het weergeven van de sensordata bekeken.
Andere functionaliteiten van de digital twin komen niet aan bod.

### GUI mockup

<img src="./Pictures/Mockups/Mockup_GUI_2D.png" width="100%"><br><br>
<img src="./Pictures/Mockups/Mockup_GUI_3D.png" width="100%"><br>

<div style="page-break-after: always"></div>

#

### GUI Statediagram

<img src="./Pictures/Diagrams/GUI_Statediagram.png"><br>

---

<div style="page-break-after: always"></div>

# 

### GUI Flowcharts

<img src="./Pictures/Diagrams/Flowchart_01.png"><br>

---

<div style="page-break-after: always"></div>
