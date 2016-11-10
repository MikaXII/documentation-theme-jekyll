---
layout: page
title: Nützliche Linux Befehle (DE)
wikiPageName: Nützliche-Linux-Befehle-(DE)
menu: wiki
---

##Boot und _recalbox_-Partitionen beschreibbar machen
Standardmässig sind alle Partitionen read-only. Das bedeutet du kannst keine Dateien editieren und abspeichern. Falls du Änderungen vornehmen möchtest, musst du zuerst die Partitionen beschreibbar machen: 
  
* Boot-Partition 
   
`mount -o remount, rw /boot`  
  
* ***recalbox***-Partition  
  
`mount -o remount rw, /`

##Scripte
  
Alle ***recalbox***-Scripte, welche auf dem System vorhanden sind, liegen in:   
  
`cd /recalbox/scripts`  
  
Alle Startup-Scripte, welche beim Systemstart ausgeführt werden, liegen in:  
  
`cd /etc/init.d`  
  
##Python-Datei ausführbar machen
  
In der Regel führt man ein Script nicht immer über einen geeigneten Interpreter aus (z.B. **python myFile.py**), sondern es wird ausführbar gemacht. Da in ***recalbox*** die Scripte mit Root-Rechten erstellt werden, wird das so gemacht:  
  
`chmod +x myFile.py`  
  
Wenn das nicht funktioniert, dann fehlt noch das richtige "Shebang". Es handelt sich dabei um die erste Zeile im Script, dass bei der Ausführung auf den richtigen Interpreter hinweist.  

Das richtige "Shebang" ist vom Interpreter abhängig:  
  
* Bash: #!/bin/bash
* Perl: #!/usr/bin/perl
* Python: #!/usr/bin/python
* ...
  
Mehr über Python, Bash etc. findest du über Google im Internet. 

##CPU Temperatur überprüfen
  
Führe den folgenden Befehl aus, um die aktuelle Temperatur der CPU zu erhalten:  
  
`cat /sys/class/thermal/thermal_zone0/temp`  
  
Um danach die Temperatur in °C zu haben, dividiere das Resultat durch 1000.

##Aktuelle Übertaktungswerte überprüfen
Um die aktuellen Übertaktungswerte auf deinem Raspberry Pi zu überprüfen, musst du diesen Befehl ausführen:  
  
` nano /boot/config.txt`  
  
Die entsprechenden Parameter befinden sich am Ende der Datei.  
  
Zum Beispiel:  
  
    arm_freq=1200
    core_freq=525
    sdram_freq=480
    over_voltage=4
    over_voltage_sdram=2
    gpu_freq=350  
  
**arm_freq** = Taktrate des Prozessors (CPU) in MHz  
**core_freq** = Taktrate des Grafikprozessors (GPU) in MHz  (Sollte gleich sein wie gpu_freq)  
**sdram_freq** = Taktfrequenz des Arbeitsspeichers (SDRAM) in MHz  
**over_voltage** = Spannung für CPU und GPU. Erhöhung um 1 = +0.025  
**over_voltage_sdram** = Spannung für alle SDRAM-Teile (c, i und p)  
**gpu_freq** = Taktrate aller GPU-Teile in MHz (Sollte gleich sein wie core_freq)  
  
##Verhindern, dass das System neustartet, wenn Mupen64 (N64 Emulator) einfriert
Falls dein System beim Benutzen von Mupen64 durch inkompatible ROMs manchmal einfriert, kannst du anstelle eines Systemneustarts einfach den N64 Emulator beenden.  Gib dazu den folgenden Befehl ein:  
   
`ps aux | grep mupen64`   
    
Finde die Prozess-ID (PID) welche zu Mupen64 gehört. Im Beispiel unten ist die ID 26193:  
  
    26193 root     mupen64plus --corelib /usr/lib/libmupen64plus.so.2.0.0 --gfx /usr/lib/mupen64plus/mupen64plus-video-gliden64.so --configdir /recalbox/configs/mupen64/ --datadir /recalbox/configs/mupen64/ /recalbox/share/roms/n64/007 - GoldenEye (Europe).n64
    26196 root     grep mupen64

Führe danach den folgenden Befehl aus, mit der entsprechenden PID von Mupen64: 
  
`kill -1 <DEINE_PID>`  
  
Danach gelangst du zurück zu EmulationStation.  

##EmulationStation starten / stoppen
EmulationStation stoppen:  
  
`/etc/init.d/S31emulationstation stop`  
  
EmulationStation starten:  
  
`/etc/init.d/S31emulationstation start`
