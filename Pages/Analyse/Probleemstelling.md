#

# Probleemstelling

## Opdrachtgever
Maarten Luyts, in opdracht van Port of Antwerp.

## Korte samenvatting
[Schrijven op het einde 250-500 woorden + ondersteunend diagram, zie IOT template.]

## Opdracht

### Korte beschrijving opdracht
De Port of Antwerp is zeer geïnteresseerd in de luchtkwaliteit in de haven. Om dit in kaart te brengen zal dit projectteam een sensor ontwikkelen die de verschillende karakteristieken van luchtkwaliteit kan meten. Deze karakteristieken zijn, maar niet gelimiteerd tot:
- Temperatuur
- Vochtigheid
- Fijnstof
- NO<sub>X</sub>

Op zich geen complexe materie om te meten. De moeilijkheid ligt echter in het in kaart brengen van de volledige haven. Om dit te kunnen realiseren moet de te ontwikkelen sensor volledig draadloos zijn. Er zal draadloze technologie nodig zijn en één of andere vorm van batterij als stroomvoorziening. De Port of Antwerp heeft onlangs in de haven een LoRaWAN netwerk uitgerold. Deze Low Power Wide Area Netwerk technologie is uiterst geschikt voor de te ontwikkelen sensor. De integratie van LoRaWAN in de sensor is dus ook een vereiste.
Op AP en daarbuiten is er al wat geëxperimenteerd met de sensors rond de luchtkwaliteit. Het innovatieve gedeelte ligt vooral rond het volledig draadloze aspect. Voordat gestart wordt met de analyse is het aangeraden om hierover opzoekingswerk te verrichten.

<div style="page-break-after: always"></div>

### Verwachte output
Prototype in een oplage van 10 stuks met volgende eigenschappen:
- sensor metingen:
	- temperatuur
	- vochtigheid
	- fijnstof
	- optioneel: NO<sub>X</sub>
- LoRaWAN draadloze connectiviteit
- gebruikt low power MCU
- behuizing geschikt voor buiten
- batterijduur van meer dan 1 jaar
- user interface om de data op een landkaart weer te geven

<div style="page-break-after: always"></div>

## Situatie As-Is
De huidige luchtsensor waarop we verder werken is met een ander doel ontwikkeld.
Deze dient om de luchtkwaliteit in en buiten de stad Antwerpen in kaart te brengen voor collega Chemie studenten.
Deze luchtsensor is mobiel bruikbaar en slaat de data lokaal op aan de hand van een SD-kaart.
Het doel was om de data door te sturen, via WiFi of seriëel, naar een database. Dit werd niet gerealiseerd.
Er is wel een LCD-display aan toegevoegd om de sensordata in real-time te kunnen zien, en een aan/uit knop voor de gebruiker.

<img src="./Pictures/As-Is_v1.0/3D_Case_on.jpg" width="50%"><img src="./Pictures/As-Is_v1.0/3D_Case_off.jpg" width="50%"><br>

### Eigenschappen:
- sensor metingen:
	- CO2
	- TVOC
	- fijnstof
	- temperatuur
	- luchtvochtigheid
- WiFi en Bluetooth connectiviteit
- SD-kaart voor lokale data opslag
- GPS module
- mobiele behuizing met LCD
- batterijduur onbekend

### Werking 
<i>Zoals beschreven in Product As-Is v1.0</i>
- De ESP zal om de x-aantal tijd alle sensoren aanroepen en hiervan de waardes opvragen.
- De sensordata wordt in een JSON bestand opgeslagen op de SD-Card.
- Nadien kan de gebruiker deze SD-card in zijn computer uitlezen en de data met een simpele knop overzetten naar de MongoDB.
- Op de website kunnen we dan de data selecteren aan de hand van naam en datum.
- Op de ingebouwde LCD kan men de huidige metingen, datum, tijd en coördinaten zien.

### Blok diagram

<img src="./Pictures/Diagrams/As-Is_BlockDiagram.png"><br>

<img src="./Pictures/As-Is_v1.0/BRD.jpg" width="50%"><img src="./Pictures/As-Is_v1.0/3D_Case_inside1.jpg" width="50%">

### Probleemstelling
Het huidige prototype moet geoptimaliseerd worden zodat deze meer dan één jaar kan werken op een batterij. Om dit te realiseren is een andere MCU nodig en dienen er aanpassingen gemaakt te worden aan de keuze van componenten.
De sensor moet ook volledig autonoom kunnen werken, zodat deze ergens geplaatst kan worden zonder bijkomend onderhoud tot de batterij leeg is.
Voor de meest accurate metingen is het echter wel <a href="./Pages/Apendix/a-review-of-low-cost-particulate-matter-sensors-20-06819.pdf">aangeraden de fijnstofsensor de calibreren bij seizoenswisselingen</a>.
Het gaat nu ook over het in kaart brengen van de volledige haven waarbij de sensors een vaste locatie krijgen.
Nu gebeurt de dataoverdracht van sensor naar database manueel via een SD-kaart. Dit moet geautomatiseerd worden en draadloos gebeuren.
De luchttoevoer naar de sensor en koeling moet ook verbeterd worden.
Er is een kleine FAN op de fijnstofsensor in combinatie met een klein gat in de behuizing. Dit zorgt echter niet voor voldoende lucht toevoer om correcte metingen te bekomen.
De warmte die de componenten ontwikkelen hebben hier ook invloed op de temperatuur meting, wat natuurlijk niet gewenst is. De luchtdoorstroming moet hier ook voor voldoende koeling zorgen.
Belangrijk hierbij is wel dat er zo weinig mogelijk vocht en grotere stofdeeltjes in de sensor geraken.
Ook moet de sensor in de schaduw geplaatst worden of voorzien worden van een zonwerende coating of film.

<div style="page-break-after: always"></div>

## Situatie To-Be

### Doelstelling
Het doel is het in kaart brengen van de luchtkwaliteit in de gehele Port of Antwerp met volledig draadloze sensoren die voor meer als één jaar autonoom kunnen werken.
De data verzenden vanuit de sensor en ontvangen door een server zal gebeuren met LoRaWAN.
Er moet een nieuwe behuizing ontworpen worden waar meer rekening wordt gehouden met luchtdoorstroming en temperatuur zoals beschreven in de probleemstelling.
Dit ontwerp moet ook worden doorgevoerd naar het PCB ontwerp en de plaatsing van de sensoren.

De opdracht laat de GPS module uit de As-Is sensor achterwegen wegens extra stroomverbruik. Wij willen argumenteren om deze toch te behouden.
Om het in kaart brengen van de luchtkwaliteit zo accuraat en eenvoudig mogelijk te maken is het aangeraden om coördinaten te hebben van waar elke sensor zich bevind.
Zo kunnen we een exacte locatie geven aan de data gemeten door elke sensor.
Rekening houdend met de realiteit dat een sensor al eens verplaatst, vervangen of hersteld zal worden, kan een GPS module zorgen voor een eenvoudige manier om aan accurate coördinaten te komen.
Door de integratie van de GPS module in de sensor kan dit volledig automatisch gebeuren, zonder dat er extra handelingen vereist zijn van de gebruiker.

De weergave van de data zal gebeuren met de eigen digital twin die de Port of Antwerp in ontwikkeling heeft.
De data moet beschikbaar gemaakt worden in een API. Zo kan de digital twin de data ophalen en weergeven in 2D en 3D representatie van de haven.

### Projectdefinitie

#### Minimal Viable Product
Prototype met volgende eigenschappen:
- sensor metingen uitvoeren:
>	- temperatuur
>	- vochtigheid
>	- fijnstof
- werking op batterij
- behuizing 3D print
- sensordata verzenden met LoRaWAN
- sensordata ontvangen en opslaan

#### Epics
> 1. Metingen uitvoeren
> 2. Sensordata verzenden
> 3. Sensordata beheer
> 4. Weergave op kaart

### Blok diagram

Door de grote wijziging in doel tussen de As-Is en To-Be situaties wordt zowat elk blok van de sensor aangepast.
De algemene werking blijft hetzelfde: aan/uit → metingen uitvoeren → sensordata verzamelen → verzenden → in database opslaan → weergeven in GUI.
De effectieve werking zal voor elk blok echter verschillen door de andere component keuzes.

<img src="./Pictures/Diagrams/To-Be_BlockDiagram.png">

### Scope
- Component selectie, totaalprijs < €100:
>	- microcontroller: I<sub>max</sub> < 10mA
>	- GPS module: low-power I<sub>max</sub> < As-Is 67mA
>	- LoRaWAN module: zendbereik hele haven over 12.068 ha = 120.680 km²
>	- fijnstofsensor: PM2.5 en PM10 concentratie, meetbereik 0-40 µg/m3
>	- temperatuur sensor: meetbereik -20° ~ +42° (<a href="https://www.frankdeboosere.be/vragen/vraag53.php#:~:text=De%20hoogste%20maximumtemperatuur%20werd%20die,%3A%20MIN%2030%2C1%20graden.">kouste en warmste meting in België</a>)<br>
>	- luchtvochtigheid sensor: meetbereik 0% ~ 100% (<a href="https://www.eurabo.be/nl/lexicon/relatieve-vochtigheid">relatieve luchtvochtigheid</a>)<br>
>	- NO<sub>X</sub> sensor: concentratie, meetbereik 0-40 µg/m3
- Elektrisch schema ontwerp voor de PCB
- PCB en behuizing ontwerp met aandacht voor sensor plaatsing voor zo accuraat mogelijke metingen
- Schroefdraad in behuizing als bevestigingspunt voor een ophangsysteem
- Initiële calibratie fijnstofsensor: de analoge spannings output bij 0mg/m³ opmeten en aftrekken van de output Vo
- Backend en API code

### Niet in scope
- LoRaWAN ontvanger opzetten
- Servers en server onderhoud
- Field deployment/plaatsing van de sensors en het ophangsysteem
- In-the-field kalibratie
- Backend deployment
- Implementatie in de digital twin

<div style="page-break-after: always"></div>