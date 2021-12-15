# Hardware Analyse

## Microcontroller

## Modules
<table>
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
            <li>NOx + VOC</li>
            <li>V<sub>cc</sub> = 3.3V / 5V</li>
            <li>I<sub>max</sub> = 60mA</li>
			<li>Capture current value@3.3V = 42.6mA</li>
			<li>Tracking current value@3.3V = 36.7mA</li>
			<li>Low power mode@3.3V = 0.85mA</li>
			<li>Ultra-low-power mode@3.3V = 31uA</li>
            <li>UART protocol</li>
			<li>Time of warm start: 4s</li>
			<li>Time of cold boot: 30s</li>
        </ul>
    </td>
    <td></td>
    <td>
		<a href="https://wiki.seeedstudio.com/Grove-GPS-Air530/">Documentation</a>
		<a href="https://www.seeedstudio.com/Grove-GPS-Air530-p-4584.html">Winkel</a>
		<a href="https://www.mouser.be/new/seeed-studio/seeedstudio-grove-gps-air530-module/">Winkel (Mouser)</a>
		<a href="./Pages/Apendix/Datasheets/Air530_GPS_User_Booklet.V1.7(Chinese).pdf">Booklet (Chinese)</a>
	</td>
</tr>
</table>

- HopeRF RFM95W LoRa Module - 868Mh
	

## Sensoren

#### Moet zeker:

<table>
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
            <li>Fijnstof</li>
            <li>V<sub>cc</sub> = 4.5V - 5.5V</li>
            <li>I<sub>max</sub> = 20mA</li>
            <li>Analoog</li>
            <li>output voltage (zie grafiek)</li>
            <li>meetbereik (zie grafiek)</li>
        </ul>
    </td>
    <td></td>
    <td>
		<a href="./Pages/Apendix/Datasheets/Sharp-GP2Y1014AU0F_nieuwere-versie-itteratie-GP2Y1010AU0F.pdf">Datasheet GP2Y1014AU0F</a>
		<a href="./Pages/Apendix/Datasheets/Sharp-GP2Y1010AU0F.pdf">Datasheet voorganger GP2Y1010AU0F</a>
		<a href="./Pages/Apendix/Datasheets/Sharp-GP2Y1010AU0F_Application-notes.pdf">Application notes GP2Y1010AU0F</a>
	</td>
</tr>
<tr>
    <td>BME280</td>
    <td>
        <ul>
            <li>Temperatuur, barometer en luchtvochtigheid</li>
            <li>V<sub>cc</sub> = 3.3V</li>
            <li>I<sub>max</sub> = 4.5mA</li>
            <li>I²C protocol 3.3V</li>
            <li>Meetbereik temperatuur: -40°C ~ +85°C</li>
            <li>Meetbereik luchtvochtigheid: 0% ~ 100%</li>
			<li>Meetbereik luchtdruk: 300hPa ~ 1100hPa</li>
			<li>Leessnelheid: 1Hz (1s)</li>
        </ul>
    </td>
    <td></td>
    <td><a href="./">Datasheet</a></td>
</tr>
<tr>
    <td>MHZ19</td>
    <td>
        <ul>
            <li>CO2</li>
            <li>V<sub>cc</sub> = 3.6V - 5.5V</li>
            <li>I<sub>max</sub> = 18mA</li>
            <li>UART of PWM</li>
            <li>Meetbereik: 0ppm - 2000ppm</li>
            <li>3 minuten opwarmtijd</li>
        </ul>
    </td>
    <td></td>
    <td><a href="./">Datasheet</a></td>
</tr>
</table>

#### Optioneel:

<table>
<tr>
    <td>SGP41</td>
    <td>
        <ul>
            <li>NOx + VOC</li>
            <li>V<sub>cc</sub> = 1.7V - 3.6V</li>
            <li>I<sub>max</sub> = 100mA</li>
            <li>I²C protocol</li>
            <li>Meetbereik: 0-1000ppm ethanol</li>
            <li>Meetbereik: 0-10ppb NOx</li>
        </ul>
    </td>
    <td></td>
    <td><a href="./">Datasheet</a></td>
</tr>
</table>
	
## Voeding

## Alternatieven