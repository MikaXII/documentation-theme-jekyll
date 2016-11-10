---
layout: page
title: Scrape deine Spiele mit deinem PC (DE)
wikiPageName: Scrape-deine-Spiele-mit-deinem-PC-(DE)
menu: wiki
---

Du kannst deine Spiele mit deinem Computer scrapen. Diese Methode prüft die Hash-Signatur deiner ROMs und nicht ihre Namen. Das macht diese Methode effizienter und schneller.  

Zuerst ein grosses Danke an [NeB](http://blog.recalbox.com/forums/user/neb/) für dieses How-To!  

Eine französische Version findest du im [Forum](http://blog.recalbox.com/forums/topic/tuto-scraper-ses-jeux-depuis-son-pc-plus-efficacement/).  
  
Was brauchst du dafür?  

- Einen Computer
- Die vorkompilierten Binärdateien für dein Betriebssystem: https://github.com/sselph/scraper/releases  

:HINWEIS: Dieses How-To wurde für PC und MAC geschrieben. Es lässt sich aber sehr einfach auch auf Linux anwenden.  

###Erster Schritt (Für PC und MAC)

Wenn du bspw. deine SNES-ROMs scrapen möchtest, legst Du auf deinem Computer einen Ordner mit dem Titel `snes` an. In diesen Ordner kopierst du deine SNES-ROMs. Die ROMs dürfen die Dateiendung .smc, .sfc oder .zip haben. Lege ebenfalls die Datei `scraper.exe` (Für Windows) oder `scraper` (Für MAC/UNIX), die du bereits heruntergeladen hast, in diesem Ordner ab.  

Du bist nun bereit, deine SNES-ROMs zu scrapen.  

###Zweiter Schritt

####Für PC

Drücke Shift+Rechtsklick auf deinem SNES-Ordner und wähle „Eingabeaufforderung hier öffnen“.  
Nachdem sich das Fenster geöffnet hat, führe Folgendes aus:  
  
`scraper.exe -image_path="~/.emulationstation/downloaded_images/SYSTEM_NAME" -no_thumb=true -max_width=375`  
  
Ersetze **SYSTEM_NAME** mit dem Namen des Systems, das du scrapen willst: _snes_, _nes_, _mastersystem_, etc...  
  
Am Beispiel SNES sieht der Befehl dann folgendermaßen aus:

`scraper.exe -image_path="~/.emulationstation/downloaded_images/snes" -no_thumb=true -max_width=375` 

Drücke nun Enter und warte bis der Vorgang abgeschlossen ist.  
  
Wenn du Arcade-ROMs scrapen willst (**MAME** oder **FBA** inklusive **NeoGeo**) führe folgenden Befehl aus:  
  
`scraper.exe -mame -mame_img "m,t,s" -image_path="~/.emulationstation/downloaded_images/MAME_ODER_FBA_ODER_NEOGEO" -no_thumb=true -max_width=375`  
  
Ersetze **MAME_ODER_FBA_ODER_NEOGEO** durch _mame_, _fba_ oder _neogeo_.  

####Für MAC (2 Lösungen)
  
- Öffne ein Terminal-Fenster (Applications/Utilities) und ziehe den SNES-Ordner, den du vorher erzeugt hast, in das Terminal-Fenster.  
  
oder  
  
- Aktiviere die Option «Neues Terminal im Ordner» (Der Text kann abweichen). Diese Option findest du in den Tastatur-Einstellungen unter _Tastatur-Kürzel_. In der linken Kolonne unter _Services_ findest du weiter unten die Linie «Neues Terminal im Ordner». Setze einen Haken über dieser Linie. 
  
Mache nun einen Rechtsklick in deinem SNES-Ordner und wähle «Neues Terminal im Ordner».  
  
Führe im Terminal-Fenster folgenden Befehl aus:  
  
`./scraper -image_path="~/.emulationstation/downloaded_images/SYSTEM_NAME" -no_thumb=true -max_width=375`  
  
Ersetze **SYSTEM_NAME** mit dem Namen des Systems, das du scrapen willst: _snes_, _nes_, _mastersystem_, etc...  
Am Beispiel SNES sieht der Befehl dann folgendermaßen aus:

`./scraper -image_path="~/.emulationstation/downloaded_images/snes" -no_thumb=true -max_width=375`  

Drücke nun Enter und warte bis der Vorgang abgeschlossen ist.  
  
Wenn du Arcade-ROMs scrapen willst (**MAME** oder **FBA** inklusive **NeoGeo**) führe den folgenden Befehl aus:
    
`scraper -mame -mame_img "m,t,s" -image_path="~/.emulationstation/downloaded_images/MAME_ODER_FBA_ODER_NEOGEO " -no_thumb=true -max_width=375`  
  
Ersetze **MAME_ODER_FBA_ODER_NEOGEO** durch _mame_, _fba_ oder _neogeo_.  

###Dritter Schritt (Für PC und MAC)

An diesem Punkt hast du nun deine ROM-Sets sowie die dazugehörigen Scrape-Dateien. Diese müssen nun auf deine ***recalbox*** kopiert werden.  
  
Bevor du mit dem Kopieren beginnst, musst du **zwingend EmulationStation beenden**.  
  
Dafür gibt es zwei Möglichkeiten:  
  
- Starte deine ***recalbox*** und drücke **ALT + F4** wenn du eine Tastatur verbunden hast.
- Öffne ein Terminal-Fenster (z.B. mit Putty) mit [Root-Zugriff](https://github.com/recalbox/recalbox-os/wiki/Root-Zugriff-auf-dem-Terminal-%28DE%29) 
  
In beiden Fällen kannst du nun EmulationStation mit dem folgenden Befehl beenden:  
  
`/etc/init.d/S31emulationstation stop`  
  
Um nun die Dateien zu kopieren, öffne den `system`-Ordner deiner ***recalbox*** über dein Netzwerk. Darin erzeugst du einen Ordner `backup_scrape` und fügst die beiden Ordner `downloaded_images` und `gamelists` ein.
  
Nun kannst du die folgenden Anweisungen ausführen: [Mini How-To – Sektion "Wiederherstellung"] (https://github.com/recalbox/recalbox-os/wiki/Sicherungskopie-deiner-Scrapes-%28DE%29#wiederherstellung). 
  
Vergiss nicht EmulationStation neuzustarten wenn du alles fertiggestellt hast. Führe dazu folgenden Befehl aus:  
  
`/etc/init.d/S31emulationstation start`
