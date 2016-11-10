---
layout: page
title: Multiplayer auf dem SNES (DE)
wikiPageName: Multiplayer-auf-dem-SNES-(DE)
menu: wiki
---

Auf der ***recalbox*** kannst du mit bis zu 4 Spielern SNES (Super Nintendo Entertainment System) spielen.  
  
Dazu brauchst du 4 Controller (1 Controller pro Spieler), die alle konfiguriert sind.
Bearbeite die [[recalbox.conf|recalbox.conf-(DE)]]-Datei und ersetze den SNES-Emulator durch `snes9x_next`.  
  
    # ------------ I - EMULATORS CHOICES ----------- #
    ## You can override the global configuration here
    snes.core=snes9x_next  
  
Speichern und ***recalbox*** neustarten.  
  
Starte ein SNES Spiel, z.B. _Micro Machines_. Öffne danach das RetroArch-Menü mit **Hotkey+B** und ändere die folgenden Parameter:  
  
    Setting / Configuration / Save Configuration On Exit : ON
    Setting / Input / User 2 Device Type / Multitap
    Quick menu / Restart Content  
  
Du kannst die Einstellung `Save Configuration On Exit` wieder zurück auf `OFF` setzen, wenn du das Spiel neugestartet hast. Falls du das nicht machst ist die Gefahr grösser, dass ungewollte Änderungen beim Beenden von RetroArch gespeichert werden.  
  
Und voilà. Das Spiel funktioniert und du bist der Star der Party!  
