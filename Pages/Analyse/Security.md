#

# Security

De sensor heeft twee grote zwaktes met betrekking tot security:

1. <b>De microcontroller</b>:<br>
De zwakte van de MCU is voornamelijk dat deze geherprogrammeerd kan worden en voor andere doeleinden gebruikt worden.
Dit process moet na opleveren zo moeilijk mogelijk gemaakt worden. Hoe dit best te doen moet onderzocht worden tijdens de ontwikkeling.

2. <b>Het verzenden van de data</b>:<br>
Zoals in het gedeelte over privacy hieronder beschreven gaat het hier niet om gevoelige data.
Het kan echter beschouwd worden als best practice om de te verzenden data te encrypteren voor het verzenden.
Moest er gewenst worden om de data toch niet publiek beschikbaar te maken is de data op deze manier niet leesbaar wanneer onderschept.

## Hardware security
De sensors kunnen best op een zekere hoogte geplaatst worden waar ze niet te gemakkelijk toegankelijk zijn.
Dit om diefstal en manipulatie te bemoeilijken en te ontmoedigen.

## Privacy en omgang met data
De luchtkwaliteit metingen die de sensor gaat uitvoeren is geen gevoelige data. Het kan beschouwd worden als openbaar goed. Privacy is dus niet van toepassing.
Zolang de sensors geplaatst worden op het grondgebied van de Stad Antwerpen mag de data vrij toegankelijk zijn voor de burger.
Dit is in lijn met de huidige omgang van gelijkaardige data van de Stad Antwerpen die publiek beschikbaar is.
Bij plaatsing van een sensor op privé terrein moet wel expliciete toelating gevraagd worden om de data toegankelijk te maken.

## Autorisatierollen
Twee autorisatierollen zullen voor dit project voldoende zijn:
- <b>Administrator</b>:<br>
kan wijzigingen maken aan instellingen, code en data. Deze krijgt wachtwoord beveiliging.
- <b>Gebruiker</b>:<br>
kan enkel data opvragen.

<div style="page-break-after: always"></div>