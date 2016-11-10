---
layout: page
title: Security (DE)
wikiPageName: Security-(DE)
menu: wiki
---

Ab Version 4.0.0 ist _**recalbox**_ in der Standard-Konfiguration nicht gegen Angriffe geschüzt.
In der Regel gilt:
* Verbinde Deine _**recalbox**_ nicht direkt mit dem Internet
* Sichere keine wichtigen Daten auf Deiner _**recalbox**_
* Fertige regelmäßige Backups (Sicherungen) an
* Schalte Deine _**recalbox**_ zwischen Sitzungen auch mal aus

# Root Passwort

_**recalbox**_ kommt mit einem Standard Root Passwort. Ab Version 4.0.0 ist es möglich das Root Passwort zu ändern, indem Du folgende Kommandozeilen ausführst:
* Einhängen der / Partition im read-write Modus

    mount -o remount,rw /

* Root Passwort ändern

    passwd

Bitte beachte, dass Du nach einem Update diese Prozedur wiederholen musst, da beim Updaten der _**recalbox**_ Dateien überschrieben werden und dabei das Root Passwort zurückgesetzt wird.
Ab Version 4.1 und höher sollte das Standard Passwort nicht mehr vorhanden sein.

# Netzwerkdienste

Die _**recalbox**_ aktiviert standardmäßig verschiedene Dienste. Obwohl es praktisch ist, sind diese doch leichte Zugangpunkte für Angreifer. Es erweist sich als eine gute Übung, alle Dienste die Du nicht nutzt zu deaktivieren, indem Du die "Netzwerk" Sektion in der recalbox.conf bearbeitest.

## Wifi

Wenn Du keine Netzwerk Verbindung benötigst oder ein Netzwerkkabel benutzt, schalte Wifi aus:

    wifi.enabled=0

Bitte beachte, dass _**recalbox**_ Dein Wifi Passwort als unverschlüsselten Text im Feld wifi.key sichert, also stelle sicher, dieses Feld zu löschen wenn Du Wifi ausschaltest.  
Version 4.1 sollte das Wifi Passwort nicht mehr unverschlüsselt sichern.

## Samba

Samba ist zur Dateiübertragung von einem anderen Computer nützlich. Wenn Du diesen Dienst nicht benutzt, schaltest Du ihn so aus:

    system.samba.enabled=0

Version 4.1 sollte passwortgeschützten Samba Austausch unterstützen.

## Virtual Gamepads

Virtual Gamepads ermöglicht es Dir, Dein Smartphone oder Tablet als Gamepad zu benutzen. Wenn Du dies nicht benutzt, schalte den Dienst aus, indem Du folgendes tippst:

    system.virtual-gamepads.enabled=0

# _**recalbox**_ Manager

_**recalbox**_ ist mit einem eingenem Webserver ausgestattet, der über Port 80 läuft. Dieser Server ermöglicht es Dir, Dateien wie Roms von Deinem Desktop zu Deiner _**recalbox**_ via Drag and Drop einzufügen und die Konfiguration zu ändern. Leider ist auch dies eine Goldgrube für einen Angreifer sich Deiner Box zu bemächtigen.
Solltest Du den _**recalbox**_ Manager nicht benutzen (zum Beispiel, weil Du zufrieden mit Deiner Konfiguration und Deinen Roms bist oder Du zum Upload von Roms den Samba Share Dienst benutzt), kannst Du ihn folgendermaßen ausschalten::

    system.manager.enabled=0


Diese Schritte sollten Deine Box (vorrausgesetzt alle Geräte sind mit dem selben Netzwerk verbunden) ein wenig sicherer machen.
