---
layout: page
title: NOOBS Bildschirm überspringen (DE)
wikiPageName: NOOBS-Bildschirm-überspringen-(DE)
menu: wiki
---

Du kannst beim Starten von ***recalbox*** ein paar Sekunden gewinnen, indem du **NOOBS** (New-Out-Of-The-Box-Software, Wiederherstellungspartition von ***recalbox***) zwingst, direkt von der `boot`-Partition zu starten.  
  
1. Stecke deine SD-Karte in deinen Computer/Laptop. 
2. Öffne den Windows-Explorer und navigiere zur `RECOVERY`-Partition. 
3. Öffne diese und erzeuge darin die Textdatei `autoboot.txt`.    
4. Öffne `autoboot.txt` mit einem Texteditor deiner Wahl und füge in Abhängigkeit deiner ***recalbox***-Version folgende Zeile hinzu:  
  
###Mit ***recalbox*** in Version 3.3.0, oder höher
  
* `boot_partition=5` 
  
###Mit ***recalbox*** in Version 4.0.0, oder höher
  
* `boot_partition=6`  
  
Die Textdatei verhindert nun das Anzeigen des NOOBS Startbildschirms und bootet direkt in das ***recalboxOS***.  
  
Wenn du den NOOBS Startbildschirm reaktivieren möchtest, musst du einfach die Textdatei `autoboot.txt` aus der `RECOVERY`-Partition deiner ***recalbox*** löschen.
