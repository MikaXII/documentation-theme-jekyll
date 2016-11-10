---
layout: page
title: Cave Story (DE)
wikiPageName: Cave-Story-(DE)
menu: wiki
---

Cave-Story ist ein Freeware Plattform-Abenteuer Videospiel, das im Jahr 2004 für den PC erschienen ist. Siehe auch [http://www.cavestory.org/](http://www.cavestory.org/) für mehr Informationen. Um Cave Story auch auf deiner ***recalbox*** spielen zu können, musst Du folgende Schritte befolgen (bitte achte auf die Version von ***recalbox***, die Du benutzt)
  
##Für ***recalbox***-Version 3.2.11
####1. Schritt:
Öffne und bearbeite die Datei `emulatorlauncher.sh` via [SSH](https://github.com/recalbox/recalbox-os/wiki/Root-Zugriff-auf-dem-Terminal-%28DE%29), oder auf dem [lokalen Terminal](https://github.com/recalbox/recalbox-os/wiki/Root-Zugriff-auf-dem-Terminal-%28DE%29):  
  
`nano /recalbox/scripts/emulatorlauncher.sh ` 
  
Füge am Schluss der Datei noch folgende Zeilen ein:  
  
    if [[ "$emulator" == "nxengine" ]]; then  
    	/recalbox/scripts/runcommand.sh 2 "$retroarchbin -L $retroarchcores/nxengine_libretro.so --config /recalbox/configs/retroarch/retroarchcustom.cfg \"$1\""  
    fi  
  
####2. Schritt:
Öffne und bearbeite die Datei `es_system.cfg`:
  
`nano /root/.emulationstation/es_systems.cfg  `
  
Füge die folgenden Zeilen vor `</systemList>` ein
  
    <system>  
            <name>Ports</name>  
            <fullname>Ports</fullname>  
            <path>/recalbox/share/roms/ports/</path>  
            <extension>.exe .EXE .sh .SH</extension>  
            <command>/recalbox/scripts/emulatorlauncher.sh %ROM% "nxengine"</command>  
            <platform>ports</platform>  
            <theme>ports</theme>  
    </system>  
  
####3. Schritt:
Füge das Cave-Story Dateiverzeichnis in das _ports_-Verzeichnis mit SCP, oder WinSCP ein:  
1. Gehe auf [http://www.cavestory.org/](http://www.cavestory.org/).  
2. Lade dir die englische Windows-.zip-Version (pre-patched) herunter. Die französiche Version funktioniert nicht.  
3. Entpacke die .zip-Datei in ein Verzeichnis, das du _cave_story_ oder so nennst.  
4. Benenne die Datei `doconf.exe` zu `doconf.exe.old` um.  
5. Lege das gesamte Verzeichnis in deiner ***recalbox*** unter `/recalbox/share/roms/ports/` ab. Eventuell musst du das _ports_-Verzeichnis zuerst erzeugen.  
6. Starte deine **_recalbox_** neu und los gehts!  

##Für **_recalbox_**-Version 3.3.0 und höher
Kopiere den Inhalt des Cave-Story Ordners in den `/cavestory` Ordner innerhalb des `/share` Verzeichnisses mit SCP oder WinSCP ein:  
1. Gehe auf [http://www.cavestory.org/](http://www.cavestory.org/)  
2. Lade dir die englische Windows-.zip-Version (pre-patched) herunter. Die französische Version funktioniert nicht.  
3. Entpacke die .zip-Datei in ein Verzeichnis, das du _cave_story_ oder so nennst.  
4. Benenne die Datei `DoConfig.exe` in `DoConfig.exe.old` um.  
5. Lege den gesamten Inhalt des Verzeichnisses in deiner ***recalbox*** unter `/recalbox/share/roms/cavestory/`ab. Auf Windows mit WinSCP un unter Linux mit: `scp cave_story root@RECALBOXIP:/recalbox/share/roms/cavestory/`   
6. Starte deine ***recalbox*** neu und spiele los!  
