## Projektbeskrivning

I slutet av kursen är tanken att vi ska göra en mindre projektuppgift där ni kommer jobba i grupper. Vi kommer tillhandahåll fyra olika stationer (två distans, två campus) med diverse sensorer/enheter inkopplade. Er uppgift blir att göra om dessa till "Web things" som stödjer sig på den teori och de modeller som tas upp i boken. Ni ska också göra ett enklare gränssnitt där man kan testa funktionaliteten. Det kan bestå av ett eget webbgränssnitt, slackkommandon eller andra typer av webhooks från tjänster. De av er som väljer att köra enskilda projekt på egen hårdvara bör läsa igenom de stationsbeskrivningar som finns för att få en uppfattning om projektets storlek.

###Examination
Projektuppgiften bedöms som godkänd eller underkänd. I samband med slutet av kursen kommer ett individuellt muntligt förhör på kursens innehåll genomföras som leder till ett betyg A-F.

###Handledning
Handledningspass finns inlagda i schemat där vi kommer finnas tillgängliga för frågor. Använd dessa! Då vi nu jobbar med hårdvara som kommer finnas på plats i ny228. De distansgrupper som kopplar upp sig mot dessa stationer och behöver manuellt ändra eller kontrollera något får ta kontakt med oss.

### Tänk på
Skriv simuleringskod. Du behöver inte hela tiden skicka upp din kod på hårdvaran. Det går att skriva kod som simulerar “actions” och “properties” för att få en enklare workflow.

Ni som är många i grupp. Dela upp arbetet. Ge ansvar till olika delar och ha sedan möten där ni diskuterar och lär varandra.

## Stationerna
Nedan följer beskrivningar av de stationer vi tillhandahåller. Ni är fria att själva utforma era “tjänster” utifrån den hårdvara som finns. Nedan är förslag och vi ger er frihet att omforma och lägga till egna idéer. Varje grupp kommer få en ssh-inloggning till respektive station. Detta konto är med i sudo-gruppen men använd sudo så sällan som möjligt då det är kraftfullt och kan förstöra om man inte är försiktig.

## Station A - Photobox - Distansgrupp
Hårdvara:
- Raspberry Pi 3 - Model B
- Raspberry Pi Camera Module (är aktiverad på denna pi)
- PIR Rörelsedektor (GIPO 17)
- 1 grön LED (GIPO 27)
- 1 blå LED (GIPO 22)
- 1 röd LED (GIPO 21)

Förlag: Denna station är tänkt att fungera som en fotolåda som reagerar på rörelser och tar ett foto och på något sätt sparar detta på något smart sätt så att användaren av systemet enkelt kan se de bilder som tagits och när. Stationen kommer finnas i en kartong så när någon öppnar eller kartongen eller rörelsedetektorn på annat blir aktiverad och en bild kan tas med Kameramodulen.

Stationen kan vara lite svår att hantera från distans men ta gärna hjälp av campusstudenter i salen för att aktivera rörelsedektorn och på så sätt ta foton.

https://www.npmjs.com/package/raspicam

## Station B - Sensorboard - Distans
Hårdvara:
- Raspberry Pi 3 - Model B
- Temperaturmätare/luftfuktighet AM2302 (GIPO 18)
- Lufttryck och temperaturmätare BMP180
- Ljussensor TSL2561

Förlag: Denna station kommer ha en mängd olika sensorer kopplade till sig. Denna enhet blir således en enhet som samlar in och ger ifrån sig massa data som kan presenteras både i realtid och i tidsintervall.

Tips: https://www.npmjs.com/package/raspi-sensors
(Bör vara installerad globalt och funka att köra require på)
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
bcm2835 ska vara installerat på enheten


## Station C - Bring in the student - Campus

Hårdvara:
- Raspberry Pi 3 - Model B
- LCD Display
- Diverse LEDs

Förlag: När man är på bilprovningen står man med sin bil utanför och tittar på en display där ens registreringsnummer kommer upp när man ska köra in. Vi tänkte oss något liknande för muntliga examinationer på campus. En display där det kommer upp studentens användarnamn och kontor denne ska gå till. Detta skulle man smidigt vilja kunna styra från t.ex. Slack notifieringar.

## Station D - Larmsimulator - Campus
Hårdvara:
- Raspberry Pi 3 - Model B
- PIR rörelsedetektor
- Knapp
- Diverse LEDs

Förlag: En rörelsedektor för larm. En knapp för att kunna aktivera och avaktivera larmet (kanske med viss trycksekvens för att kunna stoppa larmet). Använd ljuduttaget för att spela upp ljud när larmet går. Använd olika LED-lampor för att indikera olika statusar.

## Redovisning

### Gruppens Redovisning
Gruppen redovisar kod i det projektrepositorie som tilldelas er. Där ska också finnas en README.md som beskriver projektet.
Vad din/er "web thing" gör? Hur applikationen/tjänsten fungerar, eventuella installationsguider och beroenden som finns samt en motivering kring hur din/er implementering stödjer sig på teorierna kring web of things. Använd de termer som tas upp i litteraturen så som integration pattern och de olika lagren i arkitekturmodellen.

### Den enskilde studentens redovisning.
Du som arbetat i grupp skriver en personlig reflektion över arbetet. Vad har gått bra och vad har gått dåligt i grupparbetet. Vilka specifika delar har Du implementerat/jobbat med. Här har du möjlighet att uttrycka eventuella delar som du vill lyfta fram endest mellan dig och examinator. Detta skickas via mejl till john.haggerud@lnu.se 
