---
layout: page
title: SD Karte klonen (DE)
wikiPageName: SD-Karte-klonen-(DE)
menu: wiki
---

Um deine SD-Karte zu **klonen** und somit ein vollständiges **Backup** deiner ***recalbox*** zu erhalten, kannst du folgende Software-Anwendungen benutzen:  
* **Windows**: [Win32 Disk Imager](http://sourceforge.net/projects/win32diskimager/) (mit der READ Funktion)
* **MacOS X**: [ApplePi Baker]( http://www.tweaking4all.com/software/macosx-software/macosx-apple-pi-baker/)
* **Linux**: Benutze den DD-Befehl in der Kommandozeile (Terminal). Mehr Informationen dazu findest du unten. 

##Linux

###Backup

1. Stecke deine SD-Karte in deinen Computer.  
2. Bestimme mit folgendem Befehl, welches Gerät deine verwendete SD-Karte ist: 
`sudo fdisk -l`  
3. Navigiere auf deinem PC zum dem Verzeichnis in das du dein Backup ablegen willst. Dort kannst du mit folgendem Befehl deine SD-Karte extrahieren und komprimieren: `sudo dd if=/dev/sdX | gzip -9 > ./recalbox-JJJJMMTT-sdb.img.gz`  

Der Buchstabe X muss mit der Nummer der SD-Karte ersetzt werden, die Du zu Beginn ausgewählt hast. Das Datum sollte ebenfalls angepasst werden: z.B. recalbox-20160923-sdb.img.gz.  

###Wiederherstellung
  
Um dein Backup **wiederherzustellen**, stecke eine SD-Karte (FAT32 formatiert) in deinen PC/Laptop und führe folgenden Befehl aus: `gunzip ./recalbox-JJJJMMTT-sdb.img.gz | sudo dd of=/dev/sdX`  

Auch hier steht der Buchstabe X wieder für die SD-Karte, die Du ausgewählt hast.  

Sobald dieser Vorgang erfolgreich abgeschlossen wurde, hast du ein vollständiges Backup deiner ***recalbox*** auf der SD-Karte.
