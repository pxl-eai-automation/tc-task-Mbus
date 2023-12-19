![Overview](./resources/Overview.jpg)

## The setup

MBus (Meter-Bus) is a communication protocol used for remote reading of gas, water, electricity, and heat meters. It is a standardized protocol for transmitting consumption data from the meter to a central data collection point, typically located at the utility company.

The MBus protocol operates on a two-wire serial bus, with a maximum cable length of up to 2 kilometers. The protocol defines the data format, baud rate, and message protocol for communication between the meter and the data collection system. MBus also supports different types of meters, such as single-jet, multi-jet, and turbine meters.

The data link layer of MBus uses a packet-based protocol that consists of a header, data field, and checksum. The header contains information about the packet, such as the address of the meter and the type of data being transmitted. MBus is designed to provide a reliable and efficient data transmission rate for metering applications, rather than high transfer-speed.

> Beckhoff Application Film: [LIMTEC+, Belgium: Media technology and building automation on one platform](https://www.youtube.com/watch?v=ULxKM4GE4ZU&list=PLO_MYxzSFFnYWlXqCy7Ek5_9-lSvw86cJ&index=12)

## Hardware

- Mbus devices:
  - Elvaco CMa10 temperature and humidity sensor
  - Schneider Electric iEM315 energie meter
  
- PLC terminal: 
  - KL6781 Mbus master terminal


## Preperations

- Lees de [documentatie van de Mbus temperature and humidity sensor](https://www.elvaco.se/Image/GetDocument/en/247/cma10%20cma11%20quick%20manual%20english.pdf)

- Lees de [documentatie van de Mbus energie meter](https://www.se.com/ww/en/product/A9MEM3135/iem3135-energy-meter-63-a-mbus-1-digital-i-1-digital-o-multitariff-mid/)

- Raadpleeg de handleiding van de Beckhoff [KL6781 Mbus Master](https://download.beckhoff.com/download/document/io/bus-terminals/kl6781en.pdf). Lees zeker de pagina’s:
    - Product overview => Introduction
    - Product overview => Technical data 
    - Mounting and wiring => connection assignment
    - Access from the user program => Process image
    
- Lees volgende pagina’s over de Mbus bibliotheek [TC2_MBUS](https://infosys.beckhoff.com/english.php?content=../content/1033/tcplclib_tc2_mbus/index.html&id=)
    - Introduction
    - M-Bus
    - M-Bus => Bulletin
    - Programming => POUs => FB_MBUSKL6781
    - Programming => POUs => General device blocks, elvaco en Schneider Electric
    - Programming => DUTs => Structures => ST_KL6781inData22B, ST_KL6781outData22B en ST_MBUS_Communication

## Goals

1.  Leg in je eigen woorden Mbus uit. Hoe is het opgebouwd en wat kan je ermee?
2.  Beschrijf de aansluitingen van de KL6781.
3.  Beschrijf de ‘FB_MBUSKL6781’ functieblok. Welke zijn de in- en uitgangen en waarvoor wordt deze gebruikt?
4.  Beschrijf de ‘ST_KL6781outData22B ’ structure. Wat is de inhoud en waarvoor wordt deze gebruikt?
5.  Beschrijf de ‘ST_EL6851OutData’ structure. Wat is de inhoud en waarvoor wordt deze gebruikt?
6.  Beschrijf de ‘ST_MBUS_Communication’ structure. Wat is de inhoud en waarvoor wordt deze gebruikt?
7.  Beschrijf de aansluitingen en de werking van de Mbus temperature and humidity sensor.
8.  Beschrijf de aansluitingen en de werking van de Mbus energie meter.

## Exercises

Programmeer de PLC zodat alle toestellen op het M-bus netwerk en hun data zichtbaar zijn vanuit een visualisatie. Voor M-bus te programmeren dien je de bibliotheek Tc2_MBUS toe te voegen bij je References.

Programmatie (minimaal vereist om 60% te behalen)

1. Maak gebruik van de ‘FB_MBUSKL6781’ functieblok voor de communicatie met de KL6781. Koppel de juiste variabelen met de KL6781. Scan vervolgens alle devices op het M-bus netwerk en achterhaal de fabrikant van elk. Zorg dat dit vanuit de visualisatie mogelijk is. (10%)
2. Lees alle mogelijke data-waarden van de Mbus temperature en vochtigheidssensor uit en toon deze in de visualisatie. (10%)
3. Lees alle mogelijke data-waarden van de Mbus energie meter uit en toon deze in de visualisatie. (10%)
4. Allemaal goed en wel met zo'n kant-en-klare FB's. Probeer hetzelfde voor de temperature en vochtigheidssensor te bereiken aan de hand van de general blocks en toon deze in de visualisatie. Je zal hiervoor de registers moeten raadplegen. (15%)
5.	Allemaal goed en wel met zo'n kant-en-klare FB's. Probeer hetzelfde voor de energie meter te bereiken aan de hand van de general blocks en toon deze in de visualisatie. Je zal hiervoor de registers moeten raadplegen. (15%)

Bijkomende programmatie (Percentage telt enkel indien minimale programmatie bereikt is).

6.	Bereken de maximale spanning, stroom en vermogen over een tijdsperiode van x aantal seconden. In de visualisatie moet je de tijdsduur kunnen instellen, de maximale waarden kunnen tonen en de max. waarden resetten via een druktoets. (15%)
7.	Schrijf alle nuttige data waarden van de Mbus sensoren weg naar een CSV file. Deze moeten tegen een - via de visualisatie - instelbare sample rate toegevoegd worden aan de CSV en getoond worden in de visualisatie. (20%)




## Questions

For questions and support please place a comment in the pull request titled **Feedback**.

## Remarks

Take care of the setup. Afterwards return the setup to its original state and place it on top of the lab table in the same place. If you notice a defect, you must immediately inform the teacher.
