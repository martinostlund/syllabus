## Projektbeskrivning

I slutet av kursen är tanken att vi ska göra en mindre projektuppgift där ni kommer jobba i grupper. Ni kommer själva få ansvara för hårdvara och projektet ska utmynna i att ni byggt en "web thing" **enligt de principer och modeller som tas upp i kurslitteraturen (kap 6 till och med 10)**. Ni delar in er i grupper två och två. Vill man absolut arbeta enskilt får man. Vill man absolut jobba tre och tre får man.

**Innan 3/3 10:00 anmäler ni er grupp (namn och student-id) och en kortare beskrivning av ert projekt** till johan.leitet@lnu.se. Då skapas ett projektrepo åt er där ni kan redovisa er kod med mera.

Ni ska också göra ett enklare gränssnitt där man kan testa funktionaliteten. Det kan bestå av ett eget webbgränssnitt, slackkommandon eller andra typer av webhooks från tjänster. Detta gränsnitt ska finnas tillgängligt för examinatorerna att testa efter projektet genomgång.

### Examination

Projektuppgiften bedöms som godkänd eller underkänd.
**I samband med slutet av kursen kommer ett individuellt muntligt förhör på kursens teoretiska innehåll genomföras som leder till ett betyg A-F.**

### Handledning

Handledningspass finns inlagda i schemat där vi kommer finnas tillgängliga för frågor. Använd dessa! Ställ frågor i kursens slackkanal. 

## Hårdvara och förslag på "web things"

Som studenter ansvarar ni själva för hårdvaran. Vårt förslag är att införskaffa en Raspberry Pi som har stöd för att köra någon typ av serverscript-kod. Det finns mängder med olika resurser för hur man konfigurerar sin Raspberry Pi, installerar språket man vill och hur man kopplar sina sensorer. Några tips kan vara:

- https://www.raspberrypi.org/downloads/raspbian/ - Raspbian är det OS vi brukar rekommendera att installera för att kunna köra mjukvara på enheten
- https://github.com/cncjs/cncjs/wiki/Setup-Guide:-Raspberry-Pi-%7C-Install-Node.js-Manually - För er som kör Node.js

När det kommer till att koppla ihop sensorer och annat med er enhet kan det verkar skrämmande för en ovan. Boken visar några exempel och oftast brukar man hitta kopplingsschema för den sensor man har. Boken visar några exempel på hur man kan koppla ihop och skriva kod mot några sensorer, speciellt i kapitel 4. Många guider, hjälpforum finns att hitta på nätet.

Nedan följer några förslag på "web things" man skulle kunna bygga. Ni är fria att själva utforma era “tjänster” utifrån den hårdvara som ni införskaffar. Nedan är endast förslag och vi ger er frihet att omforma och lägga till egna idéer. Nedan beskrivningar bör dock ge en uppfattning om storleken på projekt. 

## Krav

Vi har egentligen inte några speciella krav på er WoT än att API:et den ger använder sig av de modeller och principer som tas upp i litteraturen. Detta gås igenom i kapitlen 6 till 10. Viktigt blir kapitel 8.3 som går igenom "The web thing model" vilken ska implementeras. Det ska således fungerar att koppla en generellt skriven klient mot WoT:ens "entry point" och därefter kunna kommunicera med den enligt denna model.

## Förslag A - Photobox

Hårdvara:
- Raspberry Pi 3 - Model B
- Raspberry Pi Camera Module 
- PIR Rörelsedektor (GIPO 17)
- 1 grön LED (GIPO 27)
- 1 blå LED (GIPO 22)
- 1 röd LED (GIPO 21)

Förlag: Denna station är tänkt att fungera som en fotolåda som reagerar på rörelser och tar ett foto och på något sätt sparar detta på något smart sätt så att användaren av systemet enkelt kan se de bilder som tagits och när. När rör sig så att rörelsedetektorn blir aktiverad och tas en bild med Kameramodulen som arkiveras på lämpligt sätt.

## Förslag B - Sensorboard

Hårdvara:
- Raspberry Pi 3 - Model B
- Temperaturmätare/luftfuktighet AM2302 (GIPO 18)
- Lufttryck och temperaturmätare BMP180
- Ljussensor TSL2561

Förlag: Denna station kommer ha en mängd olika sensorer kopplade till sig. Denna enhet blir således en enhet som samlar in och ger ifrån sig massa data som kan presenteras både i realtid och i tidsintervall.

Tips: https://www.npmjs.com/package/raspi-sensors
```
var RaspiSensors = require('raspi-sensors');

// Init the BMP180 sensor
var BMP180 = new RaspiSensors.Sensor({
        type    : "BMP180",
        address : 0x77
}, "temp_sensor");

// Init the TSL2561 sensor
var TSL2561 = new RaspiSensors.Sensor({
    type    : "TSL2561",
    address : 0x39
}, "
```

https://github.com/momenso/node-dht-sensor

## Förslag C - Larmsimulator
Hårdvara:
- Raspberry Pi 3 - Model B
- PIR rörelsedetektor
- Knapp
- Diverse LEDs

Förlag: En rörelsedektor för larm. En knapp för att kunna aktivera och avaktivera larmet (kanske med viss trycksekvens för att kunna stoppa larmet). Använd ljuduttaget för att spela upp ljud när larmet går. Använd olika LED-lampor för att indikera olika statusar.

redLed GPIO 22
greenLed GPIO 10
PIR GPIO 17
Button GPIO 27


### Tänk på
**Skriv simuleringskod.** Du behöver inte hela tiden ssh:a upp din kod på hårdvaran. Det går att skriva kod som simulerar “actions” och “properties” för att få en enklare workflow under tiden man jobbar. Integrera sedan in koden i hårdvaran. Ni som jobbar i grupp. Dela upp arbetet. 

## Redovisning - Senast 25/3 klockan 08:00

Kod redovisas i det projektrepositorie som tilldelas er. Där ska också finnas en README.md som beskriver projektet.
* Vad din/er "web thing" gör? 
* Hur applikationen/tjänsten fungerar - Vi vill kunna ha en adress att besöka, inte installera applikationen lokalt
* En motivering kring hur din/er implementering stödjer sig på teorierna kring web of things. Använd de termer som tas upp i litteraturen så som integration pattern och de olika lagren i arkitekturmodellen.

### Den enskilde studentens redovisning.
Varje student ska också skriva en personlig reflektion över arbetet. 

* Vad har gått bra och vad har gått dåligt i arbetet.
  * Vad kunde gjorts bättre?
  * Vad har du lärt dig av projektet.
* Tidsrapport där du tydligt visar hur många timmar du lagt på uppgiften
* Vilka specifika delar har Du implementerat/jobbat med (om ni jobbat i grupp).

Här har du möjlighet att uttrycka eventuella delar som du vill lyfta fram endast mellan dig och examinator. 
**Detta skickas via mejl till john.haggerud@lnu.se senast innan deadline ( 25/3 klockan 08:00)**
