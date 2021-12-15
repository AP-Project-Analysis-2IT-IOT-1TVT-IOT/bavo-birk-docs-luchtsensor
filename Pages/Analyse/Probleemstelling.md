# Probleemstelling
## Opdrachtgever
Maarten Luyts is product owner, in opdracht van Port of Antwerp.

## Korte samenvatting
[Schrijven op het einde 250-500 woorden + ondersteunend diagram, zie IOT template.]

## Opdracht

### Korte beschrijving opdracht
De Port of Antwerp is zeer geïnteresseerd in de luchtkwaliteit in de haven. Om dit in kaart te brengen zal dit projectteam een sensor ontwikkelen die de verschillende karakteristieken van luchtkwaliteit kan meten. Deze karakteristieken zijn maar niet gelimiteerd tot:
- Temperatuur
- Vochtigheid
- Fijnstof
- NOx

Op zich geen complexe materie om te meten. De moeilijkheid ligt echter in het kaart brengen van de volledige haven. Om dit te kunnen realiseren moet de te ontwikkelen sensor volledig draadloos zijn. Er zal dus draadloze technologie moeten zijn en een of andere vorm van batterij als stroomvoorziening. De Port of Antwerp heeft onlangs in de haven een LoRaWAN netwerk uitgerold. Deze Low Power Wide Area Netwerk technologie is uiterst geschikt voor de te ontwikkelen sensor. De integratie van LoRaWAN in de sensor is dus ook een vereiste.
Op AP en daarbuiten is er al wat geëxperimenteerd met de sensors rond de luchtkwaliteit. Het innovatieve gedeelte ligt vooral rond het volledige draadloze aspect. Voordat je start met je analyse is het aangeraden om je hierin in te lezen.

### Verwachte output
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

![As-Is block diagram](./Pictures/BlockDiagrams/As-Is_BlockDiagram.png "As-Is block diagram")


### Probleemstelling
Het huidige prototype moet geoptimaliseerd worden zodat deze meer als één jaar kan werken op een batterij. Hiervoor moet een andere MCU gebruikt worden en enkele aanpassingen naar componenten en sensors toe.
De sensor moet ook volledig autonoom kunnen werken, zodat deze ergens geplaatst kan worden en er niet naar moet worden omgekeken tot de batterij leeg is.
Het gaat nu ook over het in kaart brengen van de volledige haven, dus de data moet 
Nu gebeurt de data overgang van sensor naar database manueel via een SD-kaart. Dit zou automatisch moeten gebeuren.
De lucht toevoer naar de sensor en koeling moet ook verbeterd worden.
Nu is er een kleine FAN op de fijnstof sensor in combinatie met een klein gat in de behuizing. Dit zorgt echter niet voor voldoende lucht toevoer om correcte metingen te bekomen.
De warmte die de componenten ontwikkelen hebben nu ook invloed op de temperatuur meting, wat natuurlijk niet gewenst is. De lucht doorstroming moet dus ook voor voldoende koeling zorgen.
Belangrijk hierbij is wel dat er zo weinig mogelijk vocht en grotere stofdeeltjes in de sensor geraken.
Ook moet de sensor in de schaduw geplaatst worden of voorzien worden van een zon afwerende coating of film.

## Situatie To-Be

#### Blok diagram

![To-Be block diagram](./Pictures/BlockDiagrams/To-Be_BlockDiagram.png "To-Be block diagram")

### Projectdefinitie

#### Doelstelling
Het doel is het in kaart brengen van de luchtkwaliteit in de gehele Port of Antwerp adhv volledig draadloze sensoren die voor meer als één jaar autonoom kunnen werken.
De data verzenden vanuit de sensor en ontvangen door een server zal gebeuren adhv LoRaWAN.
Er moet een nieuwe behuizing ontworpen worden waar meer wordt rekening gehouden wordt met lucht doorstroming en temperatuur, beschreven in de probleemstelling.
Dit ontwerp moet ook worden doorgevoerd naar het PCB ontwerp en de plaatsing van de sensoren.

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
- sensor bevestigingssysteem
- LoRaWAN ontvanger opzetten
- front-end user interface
- servers en server onderhoud
- field deployment
- in-the-field kalibratie