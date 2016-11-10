---
layout: page
title: Start   Stop Button zu deiner recalbox hinzufügen (DE)
wikiPageName: Start---Stop-Button-zu-deiner-recalbox-hinzufügen-(DE)
menu: wiki
---

#Start/Stop Button

Seit Version 4.0.0-beta3 kannst du deine ***recalbox*** mit einem Start/Stop Button aufrüsten. Im Folgenden wird erklärt wie du das machst. 
 
##Hardware

Du hast zwei Möglichkeiten, einen Start/Stop Button hinzuzufügen. Entweder benutzt du einen  
* **Taster** oder einen  
* **Schalter**
  
Ein **Taster** wird durch Drücken betätigt und kehrt danach wieder in seine Ausgangsposition zurück. Er bleibt nicht eingerastet, sondern schliesst/öffnet seine Kontakte nur solange er betätigt bleibt.  
  
![](https://github.com/lackyluuk/recalbox-os/blob/master/wiki/images/Taster%20image.PNG)  
  
Ein **Schalter** wird durch einmaliges Drücken betätigt und bleibt danach in dieser Position. Erst nach erneutem Drücken, kehrt dieser in seine Ausgangsposition zurück. Er bleibt eingerastet.  
  
![](https://github.com/lackyluuk/recalbox-os/blob/master/wiki/images/schalter%20image.jpg)  
  
##Schema
Der Start/Stop Button wird über den **GPIO 3** (Pin 5) und **GND** (z.B. Pin 6, es können auch andere GND benutzt werden) mit deinem Raspberry Pi verbunden. Beide Arten von Buttons, Taster oder Schalter, werden auf diese Weise verdrahtet.  
  
![](https://github.com/lackyluuk/recalbox-os/blob/master/wiki/images/Start%20Stop%20Button.PNG)  
  
Damit der Start/Stop Button aber funktioniert, muss deine ***recalbox*** noch konfiguriert werden.

##Konfiguration

**1.** Öffne die **recalbox.conf**. Wie du das machst, erfährst du [HIER]( https://github.com/recalbox/recalbox-os/wiki/recalbox.conf-%28DE%29)  
  
**2.** Navigiere zum Kapitel _A – System Options_   
  
**3.** Jetzt kommt es darauf an, was für ein Button du verwendet hast. Benutzt du einen Taster, so entferne das Kommentierzeichen der folgenden Zeile:  
  
* `system.power.switch=PIN56PUSH`  
  
Benutzt du einen Schalter, so entferne es bei folgender Zeile:  
  
* `system.power.switch=PIN56ONOFF`  
  
**4.** Speichere die **recalbox.conf** ab und starte deine ***recalbox*** neu. Du kannst dein System nun mit einem Taster/Schalter starten und herunterfahren.  
  
#Reset Button und Power LED

Seit Version 4.0.0-beta4 kannst du deine ***recalbox*** zusätzlich mit einem Reset Button und einer Power LED aufrüsten. Im Folgenden wird erklärt wie du das machst.  
  
##Hardware

Der Reset Button funktioniert **NUR** mit einem **Taster**. Wenn du parallel zum **Reset Button** einen **Start/Stop Button** hast, muss der **Start/Stop Button** zwingend ein **Schalter** sein, da er sonst nicht mehr funktioniert.  
  
* Reset Button = Taster  
  
* Start/Stop Button = Schalter  
  
Für die Power LED verwendest du am besten eine einfarbige LED irgendeiner Farbe.  
  
![](https://github.com/lackyluuk/recalbox-os/blob/master/wiki/images/led%20image.png)  
  
##Schema

Der Reset Button wird über den **GPIO 2** (Pin 3) und **GND** (z.B. Pin 6, es können auch andere GND benutzt werden) mit deinem Raspberry Pi verbunden.   
Die Power LED wird mit der Anode (+, langes Bein) an **GPIO 14** (Pin 8) und mit der Kathode (-, kurzes Bein) an **GND** (z.B. Pin 6, es können auch andere GND benutzt werden) angeschlossen. Die Kathode (-) erkennt man auch oft an der abgeflachten Seite der LED (Siehe Abbildung oben).  
Da die GPIOs vom Raspberry Pi einen _High-Pegel_ von 3.3V DC haben, muss je nach verwendeter LED noch ein Vorwiderstand angeschlossen werden, damit deine LED nicht thermisch zerstört wird. Wie du den Vorwiderstand berechnest, wird im Kapitel **Berechnung Vorwiderstand** weiter unten erklärt.  

![](https://github.com/lackyluuk/recalbox-os/blob/master/wiki/images/Reset%20Button%20Power%20LED.PNG)  
  
Damit der Reset Button und die Power LED funktionieren, muss deine ***recalbox*** noch konfiguriert werden.

##Konfiguration
**1.** Öffne erneut die **recalbox.conf**. Wie du das machst, erfährst du [HIER]( https://github.com/recalbox/recalbox-os/wiki/recalbox.conf-%28DE%29)  
  
**2.** Navigiere zum Kapitel _A – System Options_   
  
**3.** Entferne das Kommentierzeichen der folgenden Zeile:  
  
* `system.power.switch=PIN356ONOFFRESET`  
  
Stelle sicher, dass die Zeilen vom Start/Stop Button wieder auskommentiert sind.  
  
**4.** Speichere die **recalbox.conf** ab und starte deine ***recalbox*** neu. Du kannst dein System nun mit einem Schalter starten/herunterfahren, mit einem Taster einen Reset durchführen und siehst an der LED den Status deiner ***recalbox***.  
  
#Berechnung Vorwiderstand
Damit sich deine Power LED nicht vorzeitig verabschiedet, solltest du einen Vorwiderstand einbauen, der die Stromaufnahme der LED begrenzt. Für die Berechnung nehmen wir eine rote LED mit einer Durchflussspannung von `2.1V` und einer Stromaufnahme von `20mA`.  
  
Um den Widerstand zu berechnen, müssen wir wissen wieviel Spannung darüber abfällt. Der GPIO-Ausgang liefert `3.3V` und über der LED fallen `2.1V` ab. Somit bleiben `3.3V – 2.1V = 1.2V` übrig, die über dem Widerstand abfallen müssen. Da alles in Serie geschaltet ist, bleibt der Strom konstant. D.h. es fliessen auch `20mA` durch den Widerstand.  
  
Der Widerstand berechnet sich nach dem ohmschen Gesetz: **`R = U / I`**   
 
**`R = 2.1V / 0.02A = 105 Ohm`**  
  
Das bedeutet, dass du mit einem `105 Ohm` Widerstand die maximale Helligkeit der LED erreichst.
  
Falls du nicht den passenden Widerstand zur Hand hast, so nehme im Zweifelsfalle einen grösseren. Somit leuchtet die LED zwar nicht maximal, da die `20mA` nicht erreicht werden. Die Lebenszeit erhöht sich jedoch drastisch. Nimmst du einen kleineren Widerstand, leuchtet sie zwar heller aber je nachdem auch weniger lang.  

Hier ist eine kleine Liste mit Standard LEDs. An GPIO = `3.3V` und Strom = `20mA` 
   
|Farbe|Halbleiter|Spannung|Widerstand (exakt)|
| :--------------: | :--------------: | :--------------: | :--------------: |
|Rot|GaAsP|1.6V|85Ω|
|Rot|GaP|2.1V|60Ω|
|Orange|GaAsP|1.8V|75Ω|
|Grün|GaP|2.1V|60Ω|
|Gelb|GaP|2.2V|55Ω|
|Blau|GaN|2.9V|20Ω|  
  
Diese Tabelle zeigt nur Beispiele und gilt nicht für alle diese LED-Farben. Die Spannung und der Strom sollten immer über das Datenblatt herausgesucht werden.  
  
#Zusammenfassung
Hier gibt es nochmals eine kurze Zusammenfassung zu den vorherigen Erklärungen:  
* Start/Stop Schalter an **GPIO 3 (Pin 5)** und **GND (z.B. Pin 6)**
* Reset Taster an **GPIO 2 (Pin 3)** und GND **(z.B. Pin 6)**
* LED Anode (+) und Widerstand an **GPIO 14 (Pin 8)** und **GND (z.B. Pin 6)**. Falls du kein Widerstand benötigst, dann die Anode direkt an GPIO 14 anschliessen.  
  
![](https://github.com/lackyluuk/recalbox-os/blob/master/wiki/images/Start%20Stop%20Reset%20Power%20LED.PNG)
