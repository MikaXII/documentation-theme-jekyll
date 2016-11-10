---
layout: page
title: N64: Ton funktioniert, jedoch bleibt der Bildschirm schwarz (DE)
wikiPageName: N64:-Ton-funktioniert,-jedoch-bleibt-der-Bildschirm-schwarz-(DE)
menu: wiki
---

Der N64 Emulator befindet sich in der Beta Phase. Einige Spiele funktionieren perfekt, andere nicht. Wenn ein Spiel gestartet wird, kann es vorkommen dass zwar der Ton, aber kein Bild vorhanden ist.

Eine mögliche Lösung ist:

* Drücke `F4`, um EmulationStation zu beenden
* Drücke `ALT + F2` an einer kabelgebundenen Tastatur, um den Terminal anzuzeigen
* Login mit dem Benutzer `root` und dem Passwort `recalboxroot`
* Folgendes eingeben: `cd ../recalbox/scripts`    
* Danach `nano emulatorlauncher.sh`, um die Datei zu bearbeiten
* Finde folgende Zeilen:
`if [[ « $emulator » == « n64″ ]]; then /recalbox/scripts/runcommand.sh 4 « SDL_VIDEO_GL_DRIVER=/usr/lib/libGLESv2.so mupen64plus –corel…`
* Ersetze die Zahl `4` durch die Zahl `2`
* Nun müssten die Zeilen wie folgt aussehen:
`if [[ « $emulator » == « n64″ ]]; then /recalbox/scripts/runcommand.sh 2 « SDL_VIDEO_GL_DRIVER=/usr/lib/libGLESv2.so mupen64plus –corel…`
* Drücke `STRG + X`, um den Editor zu beenden, und dann `Y`, um die Änderungen zu speichern.

Zum Schluss noch einen Neustart des Systems durchführen.
