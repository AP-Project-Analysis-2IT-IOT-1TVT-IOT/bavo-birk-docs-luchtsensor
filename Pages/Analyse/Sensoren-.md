# Sensoren:
####Moet zeker:

- Sharp GP2Y1014AU0F
	+ Fijnstof
	+ Vcc  = 4.5V - 5.5V
	+ Imax = 20mA
	+ Output voltage (zie grafiek)
	+ meetbereik (zie grafiek)
- BME280
	+ Temperatuur, barometer en luchtvochtigheid
	+ Vcc = 3.3V
	+ Imax = 4.5mA
	+ I²C protocol 3.3V
	+ Meetbereik temperatuur: -40°C ~ +85°C
	+ Meetbereik luchtvochtigheid: 0% ~ 100%
	+ Meetbereik luchtdruk: 300hPa ~ 1100hPa
	+ Leessnelheid: 1Hz (1s)
- MHZ19
	+ CO2
	+ Vcc = 3.6V - 5.5V
	+ Gemiddeld 18mA
	+ UART of PWM 
	+ 0ppm - 2000ppm
	+ 3 minuten opwarmtijd

####Optioneel:
- SGP41
	+ NOx + VOC
	+ Vcc = 1.7V - 3.6V
	+ Imax = 100mA
	+ I²C protocol
	+ 0-1000ppm ethanol
	+ 0-10ppb NOx