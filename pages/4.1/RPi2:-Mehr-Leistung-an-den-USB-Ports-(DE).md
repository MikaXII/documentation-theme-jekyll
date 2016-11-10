---
layout: page
title: RPi2: Mehr Leistung an den USB Ports (DE)
wikiPageName: RPi2:-Mehr-Leistung-an-den-USB-Ports-(DE)
menu: wiki
---

### Allgemein:

Mit den Standardeinstellungen begrenzt der Raspberry Pi 2 den Strom auf 600mA für alle vier USB-Ports. Die hier vorgeschlagenen Softwareänderungen werden diese Grenze auf 1200mA erhöhen.

### Hinweis:

* Diese Änderung ist nicht nur für _**recalbox**_ gedacht.
* Diese Änderung kann rückgängig gemacht werden.
* Ein Netzteil von 2000mA wird empfohlen, unabhängig von der Verwendung des Rasbperry Pi 2.
* Der maximal zulässige Strom des Raspberry Pi 2 beträgt 2000mA.

### Warum benötige ich mehr Leistung für meine USB-Ports?

Die Gründe für diese Änderung können zum Beispiel sein:

* Um eine 2,5 Zoll Festplatte ohne externe Stromversorgung betreiben zu können.
* Um mehrere USB-Controller gleichzeitig verwenden zu können.

### Konfiguration:

Um die Änderung durchführen zu können, muss die [config.txt](https://github.com/recalbox/recalbox-os/wiki/Ändern-der-config.txt-Datei-%28DE%29) editiert werden.

In der `config.txt`nach dem Eintrag `max_usb_current=...` suchen. Ändert diesen Eintrag in `max_usb_current=1`. Falls dieser Eintrag nicht existiert, fügt ihn einfach am Ende der `config.txt` hinzu.

Nun noch die `config.txt` speichern und einen Neustart des Systems durchführen.

