---
layout: page
title: Dual Boot einrichten: Raspbian   recalboxOS (DE)
wikiPageName: Dual-Boot-einrichten:-Raspbian---recalboxOS-(DE)
menu: wiki
---

1. Lade dir NOOBS «Offline and network install» (beinhaltet die neueste Raspian-Version) hier herunter: https://www.raspberrypi.org/downloads/noobs/  
  
2. Entpacke das .zip-Archiv und kopiere alle Dateien in das Root-Verzeichnis deiner SD-Karte. Deine SD-Karte sollte im **FAT32**-Dateiformat sein. Das kannst du z.B. mit der Software SDFormatter machen: https://www.sdcard.org/downloads/formatter_4/eula_windows/SDFormatterv4.zip  
  
3. Lade dir nun die neueste ***recalbox***-Version hier herunter: https://github.com/digitalLumberjack/recalbox-os/releases/latest  
  
4. Lege im Root-Verzeichnis auf deiner SD-Karte einen Ordner an, den du `os` nennst.  
  
5. Entpacke nun dein heruntergeladenes ***recalbox***-.zip-Archiv und kopiere den Order «recalboxOS-rpi3» (oder die entsprechende OS-Version für dein Raspberry Pi) aus dem `os`-Ordner in den `os`-Ordner, den du auf deiner SD-Karte angelegt hast.  
  
6. Deine SD-Karte ist nun bereit und du kannst sie in deinen Raspberry Pi einsetzen.  
  
7. Beim ersten Start erscheint nach dem Startbildschirm ein Fenster, welches dir verschiedene Betriebssysteme zur Auswahl anzeigt. Wähle «Raspian» und ***recalbox*** an und klicke danach auf «Installieren».  
  
8. Nach ein paar Minuten sollte die Installation erfolgreich abgeschlossen sein.  
  
9. Beim Neustart nach der Installation, erscheint wieder ein Fenster, welches dir nun die beiden installierten Betriebssysteme zeigt. Du hast nun die Möglichkeit entweder «Raspian» oder ***recalbox*** zu starten.  
  
Standardmässig bleiben dir rund 10 Sekunden um sich zu entscheiden, welches Betriebssystem du starten möchtest. Lässt du diese Zeit verstreichen, so startet das System automatisch das zuletzt benutzte OS.  
  
**Wichtige Information:**  
  
**Wenn du dich für ein Dualboot «Raspian/_recalbox_» entschieden hast und eine 16 GB SD-Karte benutzt, wird der Speicherplatz standardmässig wie folgt aufgeteilt: 4.1 GB für «Raspian» und 3 GB für _recalbox_.**
