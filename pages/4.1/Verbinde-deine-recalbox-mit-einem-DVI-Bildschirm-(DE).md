---
layout: page
title: Verbinde deine recalbox mit einem DVI Bildschirm (DE)
wikiPageName: Verbinde-deine-recalbox-mit-einem-DVI-Bildschirm-(DE)
menu: wiki
---

Du möchtest deine _**recalbox**_ an einen DVI Bildschirm anschließen, bekommst aber nur ein schwarzes Bild?

[Bearbeite einfach die config.txt](https://github.com/recalbox/recalbox-os/wiki/%C3%84ndern-der-config.txt-Datei-%28DE%29), in dem Du folgende Zeile

`hdmi_drive=2`

mit einer # versiehst 

`#hdmi_drive=2`

In ***recalbox*** ist die `/boot` Partition ab Version 4.0.0 aufwärts nur mit Leserechten gemountet.
Bevor du also die `config.txt` editieren kannst, musst du die Partition mit Schreibrechten mounten. Verschaffe dir dafür [Root Zugriff](https://github.com/recalbox/recalbox-os/wiki/Root-Zugriff-auf-dem-Terminal-%28DE%29) und tippe folgendes Kommando in die Commandline:

`mount -o remount, rw /boot`
