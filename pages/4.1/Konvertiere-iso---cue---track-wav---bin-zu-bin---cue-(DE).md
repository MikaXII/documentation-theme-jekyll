---
layout: page
title: Konvertiere iso   cue   track wav   bin zu bin   cue (DE)
wikiPageName: Konvertiere-iso---cue---track-wav---bin-zu-bin---cue-(DE)
menu: wiki
---

##Erklärungen
Hier wird erklärt, wie sich `.iso` und `.cue`-Dateien, sowie `.wav`-Audiodateien zu einer `.bin` und `.cue`-Datei umwandeln lassen. Um ein Verständnis dieser verschiedenen Endungen, sowie einen Grund für solch eine Umwandlung zu bekommen, gibt es zuerst eine kleine Einführung:
* **.cue-Datei:** Eine `.cue`-Datei (Cuesheet) ist eineTextdatei, die normalerweise Metadaten (z.B. Titellängen, Gesamtspieldauer) über Abbilder von CDs enthält, die benötigt werden, um diese auf eine CD brennen zu können.
* **.iso-Datei:** Eine `.iso`-Datei (ISO-Image) enthält ein identisches Speicherabbild des Dateisystems einer CD oder DVD. Das Dateisystem wird beim Erzeugen eines ISO-Abbildes unverändert kopiert, wodurch die Berechtigungen, sowie andere Metadaten, unverändert enthalten bleiben.
* **.bin-Datei:** Eine`.bin`-Datei ist wie eine `.iso`-Datei ein Speicherabbild einer CD, oder DVD. Der Unterschied ist aber, dass dieses Abbild in **binärer** Form vorliegt. Das bedeutet es ist keine Textdatei, die nur druckbare Zeichen enthält, sondern sie kann auch beliebige Bitmuster enthalten. Binärdateien können je nach Format auch Datenteile enthalten, die als Texte/Zeichen interpretierbar sind. Zu einer `.bin`-Datei gehört immer auch eine `.cue`-Datei, die alle Informationen (Metadaten) des Abbilds enthält.
* **.wav-Datei:** Eine `.wav`-Datei (WAVE Form Audio) dient der digitalen Speicherung von Audiodaten. In den allermeisten Fällen enthält eine `.wav`-Datei dabei unkomprimierte Rohdaten. Der Verzicht auf eine Komprimierung bedeutet folglich, dass die Audiodatei in höchster Qualität gespeichert ist. Allerdings erfordert dies einen enormem Speicherbedarf. Zwei Minuten Musik können schnell um die 20 Megabyte (MB) Platz belegen.
Da die Abbildung einer Audio CD in einem ISO-Image nicht möglich ist (eine Audio-CD besitzt kein ISO9660 Dateisystem, sondern die Audiodaten sind direkt PCM kodiert auf den Datenträger geschrieben), kann es vorkommen, dass das Spiel als `.iso`-Datei und die Audio-Tracks als einzelne .wav-Dateien vorliegen. Zusätzlich existiert noch eine `.cue`-Datei, welche alle Informationen zu den Audio-Dateien enthält.  
Um nun die Datei-Flut zu reduzieren, können die `.iso`- und die `.wav`-Dateien zu einer einzigen `.bin`-Datei zusammengefasst werden. So hat man am Schluss noch zwei Dateien, bestehend aus einer PCM kodierten Datei (`.bin`) und einer Textdatei (`.cue`) mit der Aufteilung der `.bin`-Datei in Tracks.  

##Anwendung
  
SegaCD oder PSX-Spieldateien können verschiedene Endungen besitzen:  
  
* .iso + .cue + .wav
* .iso
* .bin + .cue
* .ccd + .img + .sub
* .bin

Beispiel:  
  
    Wonder Dog (1993)(Sega)(PAL)(Track 01 of 21)[!].iso  
    Wonder Dog (1993)(Sega)(PAL)(Track 02 of 21)[!].wav  
    Wonder Dog (1993)(Sega)(PAL)(Track 03 of 21)[!].wav  
    Wonder Dog (1993)(Sega)(PAL)(Track 04 of 21)[!].wav   
    Wonder Dog (1993)(Sega)(PAL)(Track 05 of 21)[!].wav  
    Wonder Dog (1993)(Sega)(PAL)(Track 06 of 21)[!].wav  
    Wonder Dog (1993)(Sega)(PAL)(Track 07 of 21)[!].wav  
    Wonder Dog (1993)(Sega)(PAL)(Track 08 of 21)[!].wav  
    Wonder Dog (1993)(Sega)(PAL)(Track 09 of 21)[!].wav  
    Wonder Dog (1993)(Sega)(PAL)(Track 10 of 21)[!].wav  
    Wonder Dog (1993)(Sega)(PAL)(Track 11 of 21)[!].wav  
    Wonder Dog (1993)(Sega)(PAL)(Track 12 of 21)[!].wav  
    Wonder Dog (1993)(Sega)(PAL)(Track 13 of 21)[!].wav  
    Wonder Dog (1993)(Sega)(PAL)(Track 14 of 21)[!].wav  
    Wonder Dog (1993)(Sega)(PAL)(Track 15 of 21)[!].wav  
    Wonder Dog (1993)(Sega)(PAL)(Track 16 of 21)[!].wav  
    Wonder Dog (1993)(Sega)(PAL)(Track 17 of 21)[!].wav  
    Wonder Dog (1993)(Sega)(PAL)(Track 18 of 21)[!].wav  
    Wonder Dog (1993)(Sega)(PAL)(Track 19 of 21)[!].wav  
    Wonder Dog (1993)(Sega)(PAL)(Track 20 of 21)[!].wav  
    Wonder Dog (1993)(Sega)(PAL)(Track 21 of 21)[!].wav  
    Wonder Dog (1993)(Sega)(PAL)[!].cue  
  
    Rockman 8 - Metal Heroes (Japan) (Track 1).bin  
    Rockman 8 - Metal Heroes (Japan) (Track 2).bin  
    Rockman 8 - Metal Heroes (Japan) (Track 3).bin  
    Rockman 8 - Metal Heroes (Japan) (Track 4).bin  
    Rockman 8 - Metal Heroes (Japan).cue  
  
Nachfolgend beschreiben wir eine Möglichkeit, `.iso` + `.cue` mit `.wav`-Dateien in `.bin` + `.cue` zu konvertieren.  
  
Dieses Vorgehen funktioniert für PSX und SegaCD.  
  
1. Lade dir <a href="http://eu-uk7.disk-tools.com/request?p=a6574b3d8017942f37e77e7611a397e3/DTLiteInstaller.exe">Daemon Tools Lite (freeware)</a> herunter.  
1.1. Software installieren.  
1.2. Starte das Programm und wähle „Image Disc“ an und klicke auf das „+“-Zeichen.  
1.3. Wähle deine `.cue`-Datei.  
1.4. Klicke auf „Öffnen“ oder mit Rechtsklick auf „Mount to create virtual drive“ (Einbinden um virtuelles Laufwerk zu erzeugen).  
  
<img src="https://github.com/lackyluuk/recalbox-os/blob/master/wiki/images/cue+bin example 1.PNG" alt=""> 
  
2. Lade dir <a href="http://www.digital-digest.com/software/download.php?sid=470&amp;ssid=0&amp;did=1">Imgburn </a> herunter.  
2.1 Software installieren.  
2.2 Wähle „Create image file from disc“  
2.3 Wähle das virtuelle Laufwerk als Quelle aus (1).  
2.4 Wähle einen Zielordner für die Erzeugung der `.bin`- und der `.cue`-Datei (2).  
2.5 Klicke auf den „Schreiben“-Button (3).  
2.6 Nun musst du nur noch warten bis die Dateien erzeugt wurden.  
  
<img src="https://github.com/lackyluuk/recalbox-os/blob/master/wiki/images/cue+bin example 2.PNG" alt="">
<img src="https://github.com/lackyluuk/recalbox-os/blob/master/wiki/images/cue+bin example 3.PNG" alt="">   
  
Nachdem die Konvertierung abgeschlossen wurde, kannst du das virtuelle Laufwerk wieder «entfernen». Gehe dazu mit einen Rechtsklick auf das Icon von „Daemon Tools“ und wähle dann „Unmount“ (Auswerfen).  
  
### Gut zu wissen  
Eine fehlende `.cue`-Datei (für eine `.bin`-Datei) kann auch selber erzeugt werden.  
Im folgenden Beispiel werden die Audio-Dateien aus der Datei „r-type.bin“ generiert. Die Daten dort sind Binärdaten (Rohdaten) und keine Audio-Dateien. Öffne dazu das Programm Notepad++:  
  
* Die erste Zeile muss das Wort BINARY enthalten:  
  
`FILE "NameDerDatei.bin" BINARY`  
   
* Die zweite Zeile repräsentiert die Audio-Datei (Track). **Immer** in **MODE2/2352** angeben.  
  
`TRACK 01 MODE2/2352`  
  
* Die dritte Zeile zeigt den Index der Audio-Datei „Index 01“. Dieser sagt aus, ab welcher Minute/Sekunde die Datei beginnt.  
  
`INDEX 01 00:00:00`  
  
Das Ganze sieht dann so aus:  
  
    FILE "r-type.bin" BINARY
      TRACK 01 MODE2/2352
        INDEX 01 00:00:00
  
Wenn es mehrere Audio-Dateien gibt kann die `.cue`-Datei einfach mit TRACK 02, TRACK 03 etc. erweitert werden.   
Speichere die `.cue`-Datei mit dem selben Namen wie die `.bin`-Datei ab: „r-type.cue“.  
