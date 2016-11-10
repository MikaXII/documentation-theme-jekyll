---
layout: page
title: Multi Disc Management in PS1 Spielen (DE)
wikiPageName: Multi-Disc-Management-in-PS1-Spielen-(DE)
menu: wiki
---

Es ist möglich, eine einzige Datei für Multi-Disc Spiele zu haben anstatt mehrere einzelne kleine Dateien.

/!\ **Erinnerung: Du musst deine eigenen PSX CD – Abbilder haben** /!\

Dazu musst du lediglich eine eboot – Datei erzeugen, welche deine .ISO, .bin und .img – Dateien enthält. Die eboot – Datei kann mit der Gratissoftware _psx2psp_ erzeugt werden.

Prüfe die es_system_cfg – Datei.

Gehe über die Konsole/das Terminal zu `nano /root/.emulationstation/es_systems.cfg`

Gehe auf Bearbeiten und prüfe ob .pbp / .PBP vorhanden sind.   
`<extension>.img .IMG .pbp .PBP .bin .BIN .cue .CUE .iso .ISO</extension>`

## Erzeugung der eboot - Datei

Lade dir die Anwendung _psx2psp v1.42_ herunter (Google hilft) und starte sie.

Wähle den “Classic” Modus aus. Auf der linken Seite kannst du die .ISO – Dateien einzeln in das Programm laden. Drücke auf den “Convert” – Button und warte einen Moment.

Lade deinen Ordner hoch oder benenne die eboot – Datei um, die in deiner **_recalbox_** erzeugt wurde im Ordner `/recalbox/share/roms/psx`

## CD - Wechsel

Um eine CD während dem Spielen zu wechseln, musst du 2 oder 3 Optionen im retroarch Menü aktivieren:

- Öffne das retroarch Menü innerhalb des Spiels (standardmässig _Hotkey+B_)
- Gehe zu _Settings/general settings_ und ändere die Option _configuration save on exit_ auf ON.
  Sei vorsichtig wenn du das machst. Alle Änderungen die in den Optionen gemacht werden, werden beim Verlassen von retroarch automatisch gespeichert.
- Verlasse retroarch und kehre zum Spiel zurück.
Wenn du die Meldung für einen CD – Wechsel auf dem Bildschirm siehst, musst du lediglich die CD virtuell auswerfen (Hotkey + Tastenkürzel für die CD – Auswerf Option), die CD wechseln und den CD Spieler virtuell wieder schliessen.
Das Spiel wird dann auf der nächsten CD gestartet.

Bei Problemen kann dir der folgende Thread im **_recalbox_** Forum helfen (Französisch): [http://blog.recalbox.com/forums/topic/roms-playstation-et-nombre-de-jeux/] (http://blog.recalbox.com/forums/topic/roms-playstation-et-nombre-de-jeux/)

## CD – Wechsel für PCSX-reARMed (r22)   
### Methode mit .bin - Dateien   
 * Öffne das Retroarch Menü (standardmässig Hotkey + B)    
* Wähle Quick Menü aus und danach _core disk option_   
* Werfe die virtuelle CD aus indem du _disk cycle tray status_ auswählst   
* Suche nach der Datei die du willst (sollte sich in recalbox/roms/psx befinden), indem du _Disk Image append_ auswählst.  
