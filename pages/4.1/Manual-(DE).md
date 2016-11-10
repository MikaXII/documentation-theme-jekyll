---
layout: page
title: Manual (DE)
wikiPageName: Manual-(DE)
menu: wiki
---

# _recalbox_ 4.X
## Anleitung V1.0.8

![](http://blog.recalbox.com/wp-content/uploads/2015/01/retrobox-etiquette.png)

http://www.recalbox.com

- I - [Erstmalige Benutzung](#first-use)
- II - [Konfiguration](#configuration)
 - A - [Controller](#controllers)
   - 1 - [PS3 Controller](#ps3controllers)
    - 2 - [XBox 360 Controller](#xboxcontrollers)
    - 3 - [Bluetooth Controller](#btcontrollers)
    - 4 - [Controller konfigurieren](#configurecontrollers)
    - 5 - [Button-Belegung](#btnmapping)
    - 6 - [Tastatur-Belegung](#keyboardmapping)
    - 7 - [GPIO Controller](#gpiocontrollers)
    - 8 - [Virtual Gamepads](#virtualgamepads)
 - B - [System-Einstellungen](#system-settings)
- III - [EmulationStation](#es)
 - A - [Benutzeroberfläche](#es-pres)
 - B - [Einstellungen](#es-settings)
   - 1 - [System-Einstellungen](#es-settings-sys)
    - 2 - [Spiel-Einstellungen](#es-settings-games)
    - 3 - [Controller-Einstellungen](#es-settings-controllers)
    - 4 - [Benutzeroberflächen-Einstellungen](#es-settings-ui)
    - 5 - [Sound-Einstellungen](#es-settings-sound)
    - 6 - [Netzwerk-Einstellungen](#es-settings-network)
 - C - [Steuerungen](#controls)
 - D - [Favoriten](#favorites)
 - E - [Scraper](#scrapper)
- IV - [Während des Spieles](#duringgame)
 - A - [Speichern](#duringgame-saves)
 - B - [Spezialfunktionen](#duringgame-special)
- V - [Updates](#updates)
- VI - [Netzwerk](#network)
 - A - [Eigene Spiele hinzufügen](#network-add)
 - B - [Arcade Spiele] (#network-arcade)
 - C - [ScummVM Spiele](#network-scummvm)
 - D - [Screenshots (Bildschirmfotos)](#network-screenshots)
 - E - [Sichere deine gespeicherten Spielstände](#saves)
- VII - [Kodi](#kodi)
- VIII - [Problemlösungen](#trouble)
 - A - [Controller](#trouble-controllers)
 - B - [Sonstiges](#trouble-other)
 - C - [Zurücksetzen](#hard-reset)
 - D - [Root-Zugang](#root-access)
- IX - [recalbox.conf](#recalbox.conf)


## Einleitung
_**recalbox**_ ist ein System, das Dir auf einfache Weise ermöglicht Retro-Spiele zu spielen.

Es läuft auf einem Einplatinencomputer namens Raspberry Pi und benutzt eine Reihe optimierter Emulatoren.

## <a name='first-use'></a>I - Erstmalige Benutzung
Benötigte Komponenten :
- Ein Raspberry Pi 1, 2 oder 3
- Eine SD/microSD-Karte mit 16GB oder mehr
- HDMI-Kabel
- Ein Micro USB Stromkabel **> 1.5A**
- Einen USB- oder Bluetooth-Controller

Siehe **[recalbox.com/diy](http://www.recalbox.com/diyrecalbox)** für weitere Information über die Erstinstallation.

Nach der [[Installation|Installation-(DE)]], ist das erste was Du zu tun hast, Deine _**recalbox**_ mit dem Fernseher über das HDMI-Kabel zu verbinden.

Um die _**recalbox**_ einzuschalten, stecke einfach das USB Stromkabel ein.

Viele Controller sind gleich einsatzbereit, aber wenn Du direkt einen USB-Controller konfigurieren willst, stecke eine USB-Tastatur ein und siehe [USB-Controller hinzufügen](#configurecontrollers)

Um das System herunterzufahren: Drücke den Start Knopf und wähle "BEENDEN" und "SYSTEM HERUNTERFAHREN" aus. _(Shortcut: Drücke "Select" um das "Herunterfahren" - Menü aufzurufen)_

Danach kannst Du das USB Stromkabel abstecken. _(Kleiner Tipp: Warte bis das grün/orange Licht am PI aufhört zu blinken)_

## <a name='configuration'></a>II - Konfiguration

### <a name='controllers'></a>A - Controller
_PS3 DualShock_ und _Xbox 360_ Controller werden kabellos unterstützt. Viele **USB-** und **Bluetooth-** Controller werden ebenso unterstützt. Für mehr Informationen siehe [Peripherie Kompatibiliätsliste](https://github.com/digitalLumberjack/recalbox-os/wiki/Compatibility-(DE)

**Hinweis:** In der Konfiguration ist der PS3 Controller als Standard ausgewählt. Wenn Du andere Controller verwendest, kann es notwendig sein, den PS3 Controller abzuwählen, wähle den Controller den Du benutzt aus, speichere die Konfiguration & starte neu. Finde unten Deinen Controller, um weitere Spezifikationen zu erhalten.

#### <a name='ps3controllers'></a>1 - PS3 Controller
Um einen kabellosen PS3 Controller benutzen zu können, benötigst Du einen Bluetooth Dongle.
Du kannst die Sixaxis Controller nicht am Raspberry Pi laden, sondern musst sie direkt am USB Strom laden.  
Stecke den Controller an die _**recalbox**_ **nur** um den Controller mit Deiner _**recalbox**_ zu verbinden.  
Um einen PS3 Controller zu verbinden, stecke ihn an die _**recalbox**_ und **warte 10 Sekunden**. Jetzt kannst Du den Controller abstecken und den "Home" Button drücken.

Für asiatische Versionen des PS3 DualShock 3 Controllers (wie GASIA oder SHANWAN) siehe [[PS3 Controller Treiber|PS3-controllers-drivers-(DE)]]

Denke daran, dass die Controller-Konfiguration in _**recalbox**_ auf die der SNES-Button Belegung basiert :

| PS3 Pad | SNES Pad |
| :--------------: | :--------------: |
| x | B |
| ◯ | A |
| ⬜ | Y |
| △ | X |

**Hinweis:** Der Standard **HOTKEY** Button ist der **PS** Button. Der große in der Mitte vom Controller.

Für weitere Informationen über die **HOTKEY** Funktionen wie Speichern/Laden siehe [Spezialfunktionen](https://github.com/recalbox/recalbox-os/wiki/Manual-%28DE%29#duringgame-special) .

#### <a name='xboxcontrollers'></a>2 - XBox 360 Controller

**Hinweis:** XBox 360 Wireless Controller benötigen einen speziellen Wireless Empfänger.  

Falls Du einen kabelgebundenen oder kabellosen Xbox 360 Controller hast, aktiviere [xboxdrv in recalbox.conf](https://github.com/digitalLumberjack/recalbox-os/wiki/recalbox.conf-%28DE%29) um die bestmögliche Unterstützung zu erhalten.

Der einfachste Weg um die recalbox.conf einzustellen ist, die _**recalbox**_ Weboberfläche via Webbrowser aufzurufen (z.B. http://192.168.1.100) und die folgenden Änderungen im Konfigurations-Abschnitt zu machen:

* Zuerst den PS3 Controller (Standard) abwählen, dann `controllers.ps3.enabled=1` in `controllers.ps3.enabled=0` ändern
* Danach Xbox Einstellungen von `controllers.xboxdrv.enabled=0` in `controllers.xboxdrv.enabled=1` ändern

Anschliessend bei angestecktem Controller oder Wireless Empfänger einen Neustart durchführen. (Es wird empfohlen, vorher die Controller "aufzuwecken" bevor der PI gestartet wird")

Denke daran, dass die Controller-Konfiguration in _**recalbox**_ auf die der SNES-Button Belegung basiert :

| Xbox Pad | SNES Pad |
| :--------------: | :--------------: |
| A | B |
| B | A |
| X | Y |
| Y | X |

**Hinweis:** Der Standard **HOTKEY** Button ist der **PS** Button. Der große in der Mitte vom Controller.

Für weitere Informationen über die **HOTKEY** Funktionen wie Speichern/Laden siehe [Spezialfunktionen](https://github.com/recalbox/recalbox-os/wiki/Manual-%28EN%29#duringgame-special) .

#### <a name='btcontrollers'></a>3 - Bluetooth Controller
Um einen Bluetooth Controller hinzuzufügen, versetze Deinen Controller in den "Pairing" Modus.  
Dann gehst Du mit dem Start Button oder der Tastatur in das Menü und wählst **Controller-Einstellungen** aus. 

Wähle **Einen Bluetooth Controller verbinden**:  
[![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/bluetooth-pair-350px.jpg)](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/bluetooth-pair.jpg)

Es erscheint eine Liste mit erkannten Controllern, einfach Deinen auswählen und schon ist er verbunden! Jetzt kannst Du ihn konfigurieren, wenn es nicht eh schon ein untertützter Controller ist!

Für **8bitdo** Benutzer, siehe [[8bitdo auf der recalbox|8bitdo-on-recalbox-(EN)]]. 


#### <a name='configurecontrollers'></a>4 - Controller konfigurieren
Du kannst USB Controller zu Recalbox hinzufügen.

Die meisten Modelle sind kompatibel, siehe [Peripherie Kompatibilitätsliste](https://github.com/digitalLumberjack/recalbox-os/wiki/Compatibility-(DE)


Nachdem Du Deinen USB Controller eingesteckt hast oder Deinen Bluetooth Controller verbunden hast, drücke START mit einem bereits konfiguriertem Controller (oder ENTER auf der Tastatur) und wähle "EINGABEN KONFIGURIEREN" aus.

Dann den Anweisungen folgen. 

Der letzte Button, der **HOTKEY** ist ein Button, der verschiedene Button-Kombinationen aktiviert (siehe [Spezialfunktionen](#duringgame-special)). Für Xbox 360 und PS3 Controller, ist der Standard HOTKEY Button **HOME** oder **PS**. Für Diesen wird empfohlen **L3** (der linke Analog Stick Klick auf dem DualShock) oder _**SELECT**_ zu benutzen.  

Button Namen basieren auf dem Super Nintendo Controller :  
![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/snes-controller.jpg)

Die L und R Buttons (mit L2 R2 L3 R3) basieren auf den Playstation Controllern.


Buttons die Du nicht hast kannst Du umgehen, indem Du einen Button 2 Sekunden lang gedrückt hälst.


Zurück im Konfigurations-Bildschirm, kannst Du den Controller einem Spieler zuweisen. _Dein Controller ist nun konfiguriert !_


#### <a name='btnmapping'></a>5 - Button-Belegung

Bei Controllern mit 6 Buttons (SNES, PSX, Arcade, etc.) sind die Buttons schon so belegt, das sie mit dem Original Controller übereinstimmen.   
Bei Controllern mit 2 Buttons (NES, PC Engine, GameBoy, etc.) sind die belegten Buttons B und A.

#### <a name='keyboardmapping'></a>6 - Tastatur-Belegung
Solltest Du mit der Controller-Konfiguration nicht zurechtkommen oder Du willst einfach keinen Controller einrichten, kannst Du eine USB Tastatur an die _**recalbox**_ einstecken.
Entertaste ist **START**, Leerstaste (Space) ist **AUSWÄHLEN**, S ist **ZURÜCK**, A ist **OK**

#### <a name='gpiocontrollers'></a>7 - GPIO Controller
Du kannst Deine Arcade Joysticks und Buttons direkt mit Raspberry GPIOs verbinden. Siehe [[GPIO Controller|GPIO-Controller-(DE)]]

Du kannst Original Controller von PSOne, NES, SNES, Megadrive und Andere verbinden. Siehe [[DB9 und Gamecon Controller|DB9-und-Gamecon-Controller-(DE)]]


#### <a name='virtualgamepads'></a>8 - Virtual Gamepads
Mit Miroof's [Virtual Gamepads](https://github.com/miroof/node-virtual-gamepads) kannst Du bis zu 4 Controller über Dein Smartphone hinzufügen ! 
Du brauchst einfach nur den Internet Browser auf Deinem Smartphone starten und die _**recalbox**_ IP mit Portweiterleitung (Port=8080) eingeben. Die _**recalbox**_ IP findest Du im Menü Einstellungen [NETZWERK-EINSTELLUNGEN](#user-content-6---network-settings)

[![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/virutalgamepad_touch_zones-350px.png)](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/virutalgamepad_touch_zones.png)

Für weitere Informationen siehe [[Virtual Gamepad|Virtual-Gamepad-(DE)]]

### <a name='system-settings'></a>B - System-Einstellungen
Es gibt zwei Wege Deine _**recalbox**_ zu konfigurieren. Das Front-End von EmulationStation bietet viele Möglichkeiten zur Konfiguration. Siehe [EmulationStation Einstellungen](#es-settings)

Aber wenn Du jeden einzelnen Emulator konfigurieren willst, solltest Du einen Blick hierauf werfen **[[recalbox.conf|recalbox.conf-(DE)]]**


## <a name='es'></a>III - EmulationStation

### <a name='es-pres'></a>A - Benutzeroberfläche

Startest Du Deine _**recalbox**_, öffnet sich die EmulationStation.
Von hier aus kannst Du Deine vorhandenen Systeme (Emulatoren) auswählen, Spiele öffnen oder weitere Einstellungen im Menü vornehmen.

Als erstes öffnet sich der Systembildschirm der EmulationStation:

[![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/emulationstation-350px.jpg)](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/emulationstation.jpg)

Er zeigt Dir alle bisher vorhandenen Systeme.


### <a name='es-settings'></a>B - Einstellungen


Um Systemeinstellungen vorzunehmen, drücke Start.
[![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/settings-350px.jpg)](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/settings.jpg)

#### <a name='es-settings-sys'></a>1 - SYSTEM-Einstellungen
Von hier aus gelangst Du nun in folgende Einstellungen: **system information**, **language selection**, **overclock settings**, **updates settings** and **kodi settings**.
Auch dein RPi1 kannst Du hier übertakten. Die Reihenfolge der Geschwindigkeit lautet:
*NONE* < *HIGH* < *TURBO* < *EXTREM* 
Im Extremfall führt das Übertakten zum Garantieverlust des Raspberrys aber **es ist der einzige Weg** alle Emulatoren auf Deinem RPi1 zum laufen zu bringen.

Wenn Du ein N64 System emulieren möchtest, empfiehlt es sich auch das RPi2 zu übertakten.

#### <a name='es-settings-games'></a>2 - SPIEL-Einstellungen
Du kannst folgende Spiel-Einstellungen vornehmen : **video ratio** (16/9, 4/3), **image smooth**, **rewind** and **auto save/load**.  
Die **rewind** Einstellung erlaubt es Dir, die Zeit in Spielen zurückzuspulen.
:warning: _Es kann vorkommen das diese Einstellung manche Emulatoren verlangsamt (SNES, PSX)_, wenn Du es als Standard aktivierst. Du kannst es im Emulator aktivieren in [[recalbox.conf|recalbox.conf-(EN)]]

Die **auto save/load** Option erlaubt es Dir einen Spielstand automatisch zu sichern, sobald Du ein Spiel verlässt und diesen Spielstand automatisch wieder herzustellen, wenn Du dieses Spiel wieder startest. Sobald das Spiel gestartet ist und der Spielstand geladen, benutze die [Spezialfunktion] (#duringgame-special) **Spiel Beenden**, um zum Hauptbildschirm von diesem Spiel zurückzukehren. Du kannst sie im Emulator aktivieren in [[recalbox.conf|recalbox.conf-(EN)]]

Ebenso einfach kannst Du auch *Shaders* für Deine Systeme konfigurieren. Die **shader set** Konfiguration beinhaltet die Shader Sets die für _**recalbox**_ verfügbar sind. Die **scanlines** Shaders aktivieren Abtastlinien auf allen Systemen, damit es das Aussehen von einem CRT-Fernseher bekommt. Die **retro** Shaders sind ein Satz der besten Shaders, ausgewählt von der Community, welche Dir das möglichst authentischste Spielerlebnis bieten !  
Weitere Informationen auf [[Shaders configuration|Shaders-configuration-(EN)]] .  

Du kannst auch *Shaders* mit Deinem Controller im laufendem Spiel wechseln. Benutze die [Spezialfunktionen](#duringgame-special) Hotkey + R2 oder Hotkey + L2 um den nächsten oder vorherigen Shader zu sehen.




#### <a name='es-settings-controllers'></a>3 - CONTROLLER-Einstellungen
Hier kannst Du Deine Controller konfigurieren.

#### <a name='es-settings-ui'></a>4 - BENUTZEROBERFLÄCHEN-Einstellungen
Hier bekommst Du Zugang zu den Benutzeroberflächen-Einstellungen. Du kannst hier den Overscan festlegen wenn Du schwarze Ränder oder ein abgeschnittenes Bild hast. Siehe [[Overscan settings|Overscan-settings-(EN)]] für weitere Informationen.

#### <a name='es-settings-sound'></a>5 - SOUND-Einstellungen
Du kannst folgende Sounds aktivieren oder deaktivieren: **Hintergund Sounds** in der EmulationStation, stelle **System Lautstärke** ein und wähle das **Ausgangsignal** (*Auto*, *Klinke* oder *HDMI*)  
Wähle Klinke für analogen Audioausgang.  

#### <a name='es-settings-network'></a>6 - NETZWERK-Einstellungen
Hier kannst Du Wifi aktivieren und den **Hostnamen** festlegen, sowie Deine _**recalbox**_ **IP** einsehen.
Trage die SSID Deines Routers und den Netzwerkschlüssel mit einer Tastatur ein.
Wenn alle Daten korrekt sind wird Dein Wifi aktiviert.  
Ein vorhandener Fehler verhindert die Eingabe einiger Buchstaben sowie Sonderzeichen, die Du für Deine SSID oder Schlüssel benötigst.
Du kannst die benötigten Daten direkt in Deine: [[recalbox.conf|recalbox.conf-(DE)]] Datei eintragen.


### <a name='controls'></a>C - Steuerung

**Oberflächen Funktionen :**

B → Auswählen  
A → Zurück  
Y → Favoriten wechseln  
X → Kodi starten  
Start → Menü  
Select → Optionen (Reboot Menü im Systeme Bildschirm)  
R → Nächste Seite   
L → Vorherige Seite  

Wählst Du ein System mit A aus, öffnet es sich und zeigt alle vorhandenen Spiele an.

Wenn das Spiel läuft, gehe zur Sektion *Während des Spieles* um zu sehen wie Du zur Benutzeroberfläche zurückkehren kannst.


### <a name='favorites'></a>D - Favoriten

Du kannst ein Spiel als Favoriten markieren indem Du den Y-Button drückst. Das Spiel wird an oberster Stelle in der Spieleliste mit einem ☆ gekennzeichnet. Schalte den Favoriten mit Y um.
Es ist notwendig das System Aus-/Neuzustarten, vorzugsweise über das EmulationStation Menü um Deine Favoriten zu speichern und Diese beim nächsten Start zu finden.


### <a name='scrapper'></a>E - Scraper
Für jedes vorhandene Spiel das Du gespeichert hast, kannst Du Zusatzinformationen sowie Covers angezeigt bekommen, während Du Dich durch Deine Spieleliste bewegst. Drücke **START** und gehe auf **SCRAPER**. Folge danach den Anweisungen.



## <a name='duringgame'></a>IV - Während des Spieles

Wenn Du im Spiel bist, sind Spezialfunktionen verfügbar.

### <a name='duringgame-saves'></a>A - Speicherstände
Emulatoren bringen eine nützliche Funktion mit sich : Speicherstände. Ein Speicherstand ist ein aktueller Spielstand vom Spiel und erlaubt es Dir genau diesen Punkt vom Spiel wieder zu laden.

Mit Speicherständen wirst Du nie wieder nach Speicherpunkten suchen !

Wechselst Du den Speicherplatz kannst Du mehr als einen Speicherstand pro Spiel sichern.

Du kannst einen Spielstand speichern mit **Hotkey** + **Y**
Du kannst einen Spielstand laden mit **Hotkey** + **X**


### <a name='duringgame-special'></a>B - Spezialfunktionen

**Hotkey** + Y → Spielstand speichern  
**Hotkey** + X → Spielstand laden   
**Hotkey** + Oben → Save Slot -1 auswählen  
**Hotkey** + Unten → Save Slot +1 auswählen  

**Hotkey** + Start → Spiel beenden und zum Hauptmenü zurückkehren  
**Hotkey** + A → Spiel neustarten  
**Hotkey** + B → Retroarch Menü  
**Hotkey** + L1 → Screenshot  
**Hotkey** + Rechts → Spiel beschleunigen  
**Hotkey** + Links → Zurückspulen (wenn in Optionen aktiviert)  

**Hotkey** + R2 → Nächste Shader Vorlage  
**Hotkey** + L2 → Vorherige Shader Vorlage  


Drücke Select um einen Credit in FBA und Mame hinzuzufügen.
Falls Dein Hotkey in Mame Select ist, musst du *R1* + *Start* drücken um das Spiel zu beenden (da Select bereits belegt ist um Münzen zu erhalten). 


Du kannst das Retroarch Konfigurationsmenü öffnen indem Du den **Hotkey** + **B** drückst. 
Wenn Du Retroarch konfigurieren und speichern willst, kannst du „Einstellungen speichern beim Beenden“ (Save Settings on Exit) wählen im Retroarch Menü. Dies führt dazu, dass Deine gesamte Konfiguration die Du im rgui vorgenommen hast gespeichert wird.

## <a name='updates'></a>V - Updates
Die _**recalbox**_ Aktualisierung kann im Hauptmenü vorgenommen werden. Konfiguriere das Wifi oder stecke ein Netzwerkkabel in die _**recalbox**_, drücke Start und wähle "SYSTEMEINSTELLUNGEN" mit A, dann "UPDATES" und "STARTE UPDATE".

Nach dem Update wird das System neugestartet.


## <a name='network'></a>VI - Netzwerk
Wenn Du Wifi konfiguriert oder ein Netzwerkkabel mit Deiner _**recalbox**_ verbunden hast, werden Daten mit Deinem lokalen Netzwerk ausgetauscht. An Deinem Computer, gehe auf Netzwerk im Windows Explorer und wähle die _**recalbox**_ aus :

[![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/recalbox-network1-350px.jpg)](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/recalbox-network1.jpg)

Wenn die _**recalbox**_ in Deinem Netzwerk nicht sichtbar ist, versuche es indem Du **\\\\RECALBOX** in die Windows Explorer Adressleiste eintippst und mit Enter bestätigst. Falls das nicht funktioniert, öffne das _**recalbox**_ Menü, navigiere zu __NETZWERK EINSTELLUNGEN__ und notiere die IP Adresse. 
Danach gibst Du die IP Adresse in die Windows Explorer Adressleiste ein, z.B. **\\\\192.168.1.30**.

Du hast Zugriff auf alle freigegebenen _**recalbox**_ Ordner :

[![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/recalbox-network2-350px.jpg)](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/recalbox-network2.jpg)


### <a name='network-add'></a>A - Deine Spiele hinzufügen
Kopiere einfach die Dateien in den entsprechenden Ordner. Du kannst entweder *.zip* Dateien oder unkomprimierte Roms benutzen.
Um die Spiele-Bibliothek zu aktualisieren, gehe auf **Menü**, dann **Spiel-Einstellungen** dann **Spieleliste aktualisieren**

Zögere nicht und rede über Deine Lieblingsspiele im _**recalbox**_ Forum !
https://forum.recalbox.com/category/22/deutsch

### <a name='network-arcade'></a>B - Arcade Spiele
Wenn Du Arcade Spiele zu Deiner _**recalbox**_ hinzufügen möchtest, solltest Du die Kurzanleitung [[Einfach Arcade auf der recalbox|Einfach-Arcade-auf-der-recalbox-(DE)]] lesen und lernen wie das [[Prüfen von ROM-Versionen mit clrmamepro|Prüfen-von-ROM-Versionen-mit-clrmamepro-(DE)]] funktioniert.
Danach kannst Du das [[Neogeo UniBIOS|Neogeo-UniBIOS-(DE)]] aktivieren um mehr Optionen für Deine Spiele zu erhalten.

### <a name='network-scummvm'></a>C - ScummVM Spiele
Wenn Du ein ScummVM Spiel hinzufügst, muss es ein unkomprimierter Ordner sein. In diesen Ordner fügst Du eine einzelne Datei ein, die [spielkurzname].scummvm genannt wird.

Du kannst die Kurznamen für alle unterstützten Spiele auf http://scummvm.org/compatibility/ finden.

Beispiel, wenn Du den Ordner “Broken Sword 1” im ScummVM Verzeichnis anlegst, füge dort eine Datei namens sword1.scummvm ein. 

Dein Spiel erscheint nun im Front-End (ES) und Du kannst die zugehörigen Metadaten anpassen um z.B. einen gut lesbaren Namen einzufügen. 

### <a name='network-screenshots'></a>D - Screenshots (Bildschirmfotos)
Drücke den **Hotkey** + **L1** im jeweiligen Emulator um einen Screenshot aufzunehmen. Die .png – Datei wird im *screenshots* Verzeichnis abgelegt, welches über das Netzwerk erreichbar ist.
Teile Deine besten Screenshots mit uns auf https://forum.recalbox.com/

### <a name='saves'></a>E - Sichere Deine Speicherstände
Der *saves* Ordner beinhaltet alle Sicherungen und Speicherstände. Du kannst alle Dateien kopieren, wenn Du sie sichern möchtest.

## <a name='kodi'></a>VII - Kodi
Wenn Du den X-Button auf Deinem Controller drückst, kannst Du Kodi (ehemals XBMC) starten. Du kannst ebenso Kodi aufrufen, indem Du Start drückst und es dann aus dem Menü aus startest.

Um Kodi zu Beenden, navigiere zum Power Symbol in der unteren, linken Ecke und wähle "System herunterfahren" im Programm, Du gelangst zum _**recalboxOS**_ zurück. _Aktuell(3.3.0b17) benutzt den "Exit" Button könnte vielleicht Deinen PI_ sperren.

In Kodi werden jetzt auch Controller unterstützt, aber wenn Du es bevorzugst, kannst Du HDMI CEC oder eine Smartphone Remote App benutzen. Weitere Informationen im mini how to [[Kodi on recalbox|Kodi-on-recalbox-(EN)]]


## <a name='trouble'></a>VIII - Problemlösungen

### <a name='trouble-controllers'></a>A - Controller

- Der PS3 Controller blinkt, verbindet sich aber nicht:   
Verbinde den Controller per Kabel mit der _**recalbox**_ und warte 10 Sekunden. Du kannst das Kabel nun entfernen und den Home-Button auf dem Controller betätigen.

- PS3 Controller scheint defekt zu sein:  
Setze den Controller zurück, indem du ein kleinen Knopf auf der Rückseite des Controllers betätigst. Am besten Du benutzt eine Nadel oder Büroklammer um den Knopf zu erreichen (Er befindet sich in einem kleinen Loch).

### <a name='trouble-other'></a>B - Sonstiges

- Schwarzer Rand, Bild ist zu gross:  
Öffne das TV Bildmenü (mit der TV Fernbedienung) und setze die Bildgrösse auf *1:1 Pixel* oder *Full*. 
Falls das nicht zum gewünschten Resultat führt, aktiviere die Option *Overscan* im _**recalbox**_ Menü unter **SYSTEM EINSTELLUNGEN**.
 Siehe [[Overscan settings|Overscan-settings-(EN)]] für weitere Informationen (Nur auf Englisch bis jetzt).

 
- Schwarzer Bildschirm am PC Monitor:  
Wenn Du einen schwarzen Bildschirm am PC Monitor hast (Verbindung per HDMI oder DVI) bearbeite die *config.txt* – Datei (MAJ am Anfang) und entferne die Zeile *hdmi_drive=2*
Weitere Informationen siehe [[Mini HowTo - Connect your recalbox to a DVI screen|Connect-your-recalbox-to-a-DVI-screen-(EN)]] (Nur auf Englisch bis jetzt).


### <a name='hard-reset'></a>C - Zurücksetzen
- Wenn Du das System (_**recalboxOS**_) zurücksetzen willst, verbinde eine USB Tastatur mit Deiner _**recalbox**_ und drücke die Umschalttaste beim Startvorgang. Im folgenden Menü kannst Du _**recalboxOS**_ neu installieren. **Achtung:** Alle Deine Daten werden bei diesem Vorgang gelöscht (Werkszustand).

### <a name='root-access'></a>D - Root-Zugriff
- Benutzername `root` und das Passwort `recalboxroot` 
- Du kannst Dich via SSH mit _**recalbox**_ verbinden. 
- Du kannst ein Terminal aufrufen, indem Du mit F4 und dann ALT-F2 drücken EmulationStation verlässt.

Mehr Informationen gibt es hier: [[Mini HowTo - Root access on terminal|Root-access-on-terminal-(EN)]] (Nur auf Englisch bis jetzt).

## <a name='recalbox.conf'></a>IX - recalbox.conf
Die Datei `recalbox.conf` welche im Samba `system` Verzeichnis liegt, wird benutzt um diverse andere Einstellungen vorzunehmen und ist im Front-End nicht sichtbar.
Siehe [[recalbox.conf|recalbox.conf-(EN)]]
