#

# Planning

## Analyse

We gebruiken Agile en Kanban om flexibel te werken en zo snel mogelijk vooruit te gaan.
Elke week tijdens het labo krijgen we feedback van onze begeleider meneer Van Houtven. Waarna we verbeteringen kunnen uitvoeren en de planning bijsturen.
Ten opzichte van de opdrachtgever is het analyse proces wel eerder Waterfall. Er is enkel een ineterview geweest aan de start van de analyse.
Om de planning op te volgen werken we met een Kanban bord op GitHub Projects.

### Epics (hoofdlijnen)
> 1. Probleemstelling + planning
> 2. Design + hardware analyse
> 3. Hardware schema + I/0 software
> 4. Software analyse + datamigratie + infrastructuur + security + documentatie
> 5. Release Plan + samenvatting + afwerking


### Toelichting fases
Dit is de ruwe volgorde waarin de analyse wordt uitgevoerd door de opvolgbaarheid van de onderdelen.
We kunnen bijvoorbeeld geen software analyse doen zonder de hardware outputs te kennen.
We werken wel Agile dus zullen gaande weg aanpassingen maken doorheen de analyse.

##### 1. Probleemstelling + planning
> - Omschrijving van de opdrachtgever, korte samenvatting, de situatie as-is, en de situatie to-be met een projectdefinitie (doelstelling, blokschema's, scope, niet in scope).
> - Planning met user stories voor de Analyse volgens de Kanban methodologie.
> - Omschrijven van het functioneel design, en in het algemeen het technisch design.

##### 2. Design + hardware analyse
> Vooraleer je de software kan analyseren moet je weten waarop de software gaat draaien. Vandaar dat we de hardware als eerste analyseren.

##### 3. Hardware schema + I/O software
> Eens je weet welke componenten je hebt en hoe ze tussen mekaar verbonden zijn in het hardware schema kan je de inputs en outputs oplijsten. Dit is handig voor de diagrammen later.

##### 4. Software analyse + datamigratie + infrastructuur + security + documentatie
> - Nu dat de inputs en outputs gekend zijn is het veel eenvoudiger om de diagrammen op te stellen van de software. Eens die diagrammen er zijn is het mogelijk om het dashboard te analyseren.
> - Omschrijven of er datamigratie nodig is en hoe dit zal gebeuren.
> - Omschrijven of er impact is op de huidige infrastructuur.
> - Zwakke punten rond beveiliging aangeven en wat er aan gedaan zal worden.
> - Omschrijven hoe er zal worden omgegaan met data en privacy.
> - Omschrijven wat de verschillende autorisatierollen zullen zijn.
> - Omschrijven welke documentatie zal worden voorzien en hoe dit zal gebeuren.

##### 5. Release Plan + samenvatting + afwerking
> - We weten nu wat er gemaakt moet worden dus kunnen we het Release Plan, met Gantt Chart methodologie, uitwerken.
> - We kunnen nu een samenvatting schrijven van het gehele project.
> - Als laatste zorgen we nog dat er een terminologie tabel is, en dat de versiecontrole en bronvermelding volledig is.

<div style="page-break-after: always"></div>

#

### User stories
<!-- - Als [PERSOON] wil ik [...], zodat ik [...]. -->

##### 1. Probleemstelling + planning:
> - Als GELDSCHIETER wil ik weten wie de opdrachtgever is en wat de opdracht in het kort is, zodat ik een snel idee kan krijgen van het project.
> - Als GELDSCHIETER wil ik weten wat de huidige as-is situatie is van het vorige project en de probleemstelling adhv dit huidige proces, zodat ik goed weet hoever het nu staat, wat de eventuele moeilijkheden zijn en hoe er hierop gaat voortgebouwd worden.
> - Als GELDSCHIETER wil ik weten wat de situatie to-be moet worden, wat de doelstelling van het project is, zodat ik kan inschatten of het haalbaar is. 
> - Als OPDRACHTGEVER wil ik weten wat wel en niet binnen de scope van het project valt, zodat ik weet wat ik juist zal krijgen en wat ik eventueel zelf nog moet voorzien.
> - Als ONTWIKKELAAR wil ik weten wat de planning is, zodat ik weet wat wanneer af moet zijn en om het project op te volgen.

##### 2. Design + hardware analyse:
> - Als ONTWIKKELAAR wil ik weten wat het FUNCTIONEEL DESIGN is, zodat ik weet hoe de eind gebruiker met het product zal kunnen omgaan.
> - Als ONTWIKKELAAR wil ik weten wat het TECHNISCH DESIGN is, zodat ik weet wat de architectuur is, welke technologieën zullen gebruikt worden, en hoe het project technisch zal worden gerealiseerd.
> - Als OPDRACHTGEVER wil ik weten welke HARDWARE COMPONENTEN er gaan gebruikt worden en waarom, zodat ik weet wat de sensor zal kunnen en de onderdelen zullen kosten.
> - Als HARDWARE ONTWIKKELAAR wil ik weten wat voor HARDWARE SMART OBJECT moet worden ontwikkeld, zodat ik een leidraad heb voor de ontwikkeling van de sensor.

##### 3. Hardware schema + I/0 software:
> - Als HARDWARE ONTWIKKELAAR wil ik een ELEKTRISCH SCHEMA, zodat ik het PCB kan ontwerpen.
> - Als SOFTWARE ONTWIKKELAAR wil ik de INPUTS EN OUTPUTS van de verschillende blokken weten, zodat ik weet waarmee ik in de software moet werken.

##### 4. Software analyse + datamigratie + infrastructuur + security + documentatie:
> - Als SOFTWARE ONTWIKKELAAR wil ik een SOFTWARE SMART OBJECT, zodat ik weet wat de software in zijn geheel gaat moeten doen.
> - Als SOFTWARE ONTWIKKELAAR wil ik een STATEDIAGRAM van de software, zodat ik weet welke verschillende states moeten worden ingebouwd.
> - Als SOFTWARE ONTWIKKELAAR wil ik een FLOWCHARTS voor de verschillende states van de software, zodat ik weet hoe elke transitie moet gebeuren.
> - Als OPDRACHTGEVER wil ik een MOCK UP zien van hoe de GUI er zal uitzien, zodat ik kan zien of het voldoet aan mijn wensen en eventuele feedback kan geven.
> - Als OPDRACHTGEVER wil ik weten of er eventuele DATAMIGRATIE moet gebeuren en hoe, zodat ik weet hoe dit zal gebeuren.
> - Als GELDSCHIETER wil ik weten wat de IMPACT is op de HUIDIGE INFRASTRUCTUUR, zodat ik rekening kan houden met de eventuele kosten.
> - Als OPDRACHTGEVER wil ik weten wat er rond SECURITY EN PRIVACY zal gedaan worden, zodat ik weet hoe het project zal beveiligd worden en hoe er zal omgegaan worden met data privacy.
> - Als SOFTWARE ONTWIKKELAAR wil ik weten welke AUTORISATIEROLLEN er moeten zijn, zodat ik deze kan inbouwen.
> - Als HARDWARE ONTWIKKELAAR wil ik weten wat de HARDWARE SECURITY moet zijn, zodat ik deze kan inbouwen in de hardware.
> - Als ONTWIKKELAAR wil ik weten welke DOCUMENTATIE er moet worden voorzien, zodat ik weet wat ik moet schrijven.

##### 5. Release Plan + samenvatting + afwerking:
> - Als ONTWIKKELAAR wil ik een RELEASE PLAN, zodat ik een idee heb van hoe het ontwikkelingsproces er zal uitzien.
> - Als LEZER van de analyse wil ik een KORTE SAMENVATTING, zodat ik snel kan weten waarover deze analyse gaat.
> - Als ANALYST wil ik een VERSIECONTROLE tabel kunnen raadplegen, zodat ik een overzicht heb van wat er gedaan is.
> - Als LEZER van de analyse wil ik een tabel met TERMINOLOGIE, zodat ik alles kan begrijpen.
> - Als LEZER van de analyse wil ik een BRONVERMELDING, zodat ik de correctheid en betrouwbaarheid van de data kan nagaan.

<div style="page-break-after: always"></div>

#

## Release Plan

### Epics (hoofdlijnen)
> 1. Metingen uitvoeren
> 2. Sensordata verzenden
> 3. Sensordata beheer
> 4. Weergave op kaart

### Toelichting fases

#### 1. Metingen uitvoeren
> Alles wat er moet gebeuren om metingen te kunnen uitvoeren.

#### 2. Sensordata verzenden
> Voorbereiding van de sensordata voor verzending, het verzenden zelf en het ontvangen.

#### 3. Sensordata beheer
> Alles omtrent het opslaan en opvragen van de sensordata in de database.

#### 4. Weergave op kaart
> De sensordata weergeven in de GUI.

### User stories
<!-- - Wanneer [situatie], wil ik [motivatie, waarom], zodat ik [verwachte uitkomst].]
[Deze stories helpen ons om een bepaalde situatie vast te leggen, welke handeling hierop moet
gebeuren en wat de verwachte uitkomst is van deze handeling. -->

##### 1. Metingen uitvoeren:
> - Als ONTWIKKELAAR wil ik alle COMPONENTEN BESTELLEN, zodat ik alles heb wanneer de PCB klaar is.
> - Wanneer de SENSOR GEPLAATST wordt, wil ik dat de sensor aangezet of gereset wordt, zodat de sensor zijn GPS LOCATIE kan bepalen en starten met metingen uit te voeren.
> - Wanneer er een TEMPERATUUR EN LUCHTVOCHTIGHEID METING moet worden uitgevoerd, wil ik dat de metingen worden uitgevoerd, zodat ze kunnen worden verzonden.
> - Wanneer er een FIJNSTOF METING moet worden uitgevoerd, wil ik dat de metingen worden uitgevoerd, zodat ze kunnen worden verzonden. 
> - Wanneer er een STIKSTOFOXIDEN METING moet worden uitgevoerd, wil ik dat de metingen worden uitgevoerd, zodat ze kunnen worden verzonden.
> - Wanneer alle SENSOR DATA OUTPUTS in de MCU zijn binnengekomen, wil ik dat deze worden GEFORMATTEERD IN EEN BESTAND (JSON), zodat alles bij elkaar staat.
	
##### 2. Sensordata verzenden:
> - Wanneer de SENSORDATA moet worden VERZONDEN, wil ik dat de data wordt GEFORMATTEERD IN BYTES, zodat deze draadloos kan worden verzonden.
> - Wanneer de SENSORDATA moet worden VERZONDEN, wil ik dat er VERBINDING WORDT OPGEZET, zodat de sensordata kan worden verzonden.
> - Wanneer de SENSORDATA wordt ONTVANGEN, wil ik dat de data wordt GEHERFORMATTEERD IN EEN BESTAND, zodat deze kan worden gevalideerd en klaar is om opgeslagen te worden.

##### 3. Sensordata beheer:
> - Wanneer de SENSORDATA klaar staat om te worden OPGESLAGEN, wil ik dat deze in de DATABASE komt, zodat het kan worden opgevraagd.
> - Als ONTWIKKELAAR wil ik de RUWE SENSORDATA BEKIJKEN, om deze te kunnen valideren.
> - Als ONTWIKKELAAR wil ik dat de SENSORDATA BESCHIKBAAR is in een API, zodat ik deze kan opvragen vanuit de digital twin.
	
##### 4. Weergave op kaart:
> - Als GEBRUIKER wil ik de SENSORDATA IN KAARTVORM BEKIJKEN, zodat ik een overzicht heb van de metingen.
> - Als GEBRUIKER wil ik de SENSORDATA PER SENSOR IN DETAIL BEKIJKEN, zodat ik de exacte metingen kan raadplegen van een bepaalde locatie en tijd.
> - Als GEBRUIKER wil ik de SENSORDATA BESCHIKBAAR hebben in de DIGITAL TWIN van de Port of Antwerp, zodat deze daar beschikbaar is en automatisch geanalyseerd kan worden door <a href="https://www.portofantwerp.com/en/smart-port">APICA</a>.

### Lead times
De lead times van de aan te kopen componenten, materialen, en de te
produceren PCB’s.

Zie Hardware Analyse voor lead times componenten.
PCB levertermijnen variëren van 5 tot 20 werkdagen.

<div style="page-break-after: always"></div>

#
	
### Gantt chart

<img src="./Pictures/Planning/Planning_GanttChart.JPG" width="100%">

<!-- https://www.wrike.com/workspace.htm?acc=5250985#path=folder&id=817193039&c=timeline3&vid=62103984&p=817191900&a=5250985&so=10&bso=10&sd=0&st=space-817191900 -->

<div style="page-break-after: always"></div>