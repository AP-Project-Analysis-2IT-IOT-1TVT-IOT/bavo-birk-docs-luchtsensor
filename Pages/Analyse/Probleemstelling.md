# Probleemstelling
## Opdrachtgever
Maarten Luyts is product owner, in opdracht van Port of Antwerp.

## Korte samenvatting
De Port of Antwerp wilt de luchtkwaliteit in de haven in kaart brengen. Hiervoor moet een sensor ontwikkeld worden met volgende eigenschappen:
- sensor metingen:
	- temperatuur
	- vochtigheid
	- fijnstof
- LoRaWAN draadloze connectiviteit
- gebruikt low power MCU
- casing geschikt voor buiten
- batterijduur van meer dan 1 jaar

## Situatie As-Is
De huidige luchtsensor waarop we verder werken is met een ander doel ontwikkeld.
Deze dient om de luchtkwaliteit in en buiten de stad Antwerpen in kaart te brengen voor collega Chemie studenten.
Deze luchtsensor is mobiel bruikbaar en slaat de data lokaal op op een SD kaart.
Het doel was om de data door te sturen, via WiFi of serieel, naar een database, maar dit werd niet gerealiseerd.
Er is wel een LCD-display aan toegevoegd om de sensor data in real-time te kunnen zien, en een aan/uit knop voor de gebruiker.

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
- mobiele casing met LCD
- batterijduur onbekend

### Werking (uit Product.md Versie 1.0):
- De ESP zal om de x-aantal tijd alle sensoren aanroepen en hiervan de waardes opvragen.
- Hij zal dit dan opslaan als een JSON op de SD-Card.
- Nadien kan de gebruiker deze SD-card in zijn computer uitlezen en de data met een simpele knop overzetten naar de MongoDB.
- Op de website kunnen we dan de data selecteren adhv naam en datum.
- Op de ingebouwde LCD kan men de huidige metingen, datum, tijd en coördinaten zien.

#### Blok diagram
<img src="./Pictures/BlockDiagrams/As-Is_BlockDiagram.png" width="100%">

## Situatie To-Be

### Opdracht

#### Korte beschrijving opdracht
De Port of Antwerp is zeer geïnteresseerd in de luchtkwaliteit in de haven. Om dit in kaart te brengen zal dit projectteam een sensor ontwikkelen die de verschillende karakteristieken van luchtkwaliteit kan meten. Deze karakteristieken zijn maar niet gelimiteerd tot:
- Temperatuur
- Vochtigheid
- Fijnstof
- NOx

Op zich geen complexe materie om te meten. De moeilijkheid ligt echter in het kaart brengen van de volledige haven. Om dit te kunnen realiseren moet de te ontwikkelen sensor volledig draadloos zijn. Er zal dus draadloze technologie moeten zijn en een of andere vorm van batterij als stroomvoorziening. De Port of Antwerp heeft onlangs in de haven een LoRaWAN netwerk uitgerold. Deze Low Power Wide Area Netwerk technologie is uiterst geschikt voor de te ontwikkelen sensor. De integratie van LoRaWAN in de sensor is dus ook een vereiste.
Op AP en daarbuiten is er al wat geëxperimenteerd met de sensors rond de luchtkwaliteit. Het innovatieve gedeelte ligt vooral rond het volledige draadloze aspect. Voordat je start met je analyse is het aangeraden om je hierin in te lezen.

#### Verwachte output
Prototype in een oplage van 10 stuks met volgende eigenschappen:
- sensor metingen:
	- temperatuur
	- vochtigheid
	- fijnstof
- LoRaWAN draadloze connectiviteit
- gebruikt low power MCU
- casing geschikt voor buiten
- batterijduur van meer dan 1 jaar
- user interface om de data in kaart vorm weer te geven

#### Blok diagram
<img src="./Pictures/BlockDiagrams/To-Be_BlockDiagram.png" width="100%">

### Projectdefinitie

#### Doelstelling
Het in kaart brengen van de luchtkwaliteit in de gehele Port of Antwerp adhv volledig draadloze sensoren.
De data verzenden vanuit de sensor en ontvangen door een server gebeurt adhv LoRaWAN.
De sensor moet meer dan een jaar autonoom werken in open lucht in een vochtige en zoute omgeving met vier seizoenen.
Hier moet rekening mee gehouden worden bij de componenten selectie en ontwerp.

De opdracht laat de GPS module uit de As-Is sensor achterwegen wegens extra stroomverbruik, maar wij willen argumenteren om deze toch te behouden.
Om het in kaart brengen van de luchtkwaliteit zo accuraat en eenvoudig mogelijk te maken is het aangeraden om coördinaten te hebben van waar elke sensor zich bevind.
Zo kunnen we een exacte locatie geven aan de data gemeten door elke sensor.
Rekening houdend met de realiteit dat een sensor al eens verplaatst, vervangen of hersteld zal worden, kan een GPS module zorgen voor een eenvoudige manier om aan accurate coördinaten te komen.
Door de integratie van de GPS module in de sensor kan dit volledig automatisch gebeuren, zonder dat er extra handelingen vereist zijn van de gebruiker.

#### Scope:
- component selectie
- elektrisch schema ontwerp
- PCB ontwerp
- casing ontwerp
- initiële sensor calibratie

#### Niet in scope:
- front-end user interface
- servers en server onderhoud
- field deployment
- in-the-field kalibratie