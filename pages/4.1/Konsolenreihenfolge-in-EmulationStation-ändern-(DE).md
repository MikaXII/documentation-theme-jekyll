---
layout: page
title: Konsolenreihenfolge in EmulationStation ändern (DE)
wikiPageName: Konsolenreihenfolge-in-EmulationStation-ändern-(DE)
menu: wiki
---

Wenn Du die Reihenfolge der Systeme in EmulationStation ändern möchtest, geht dies nur mit ein paar Eingriffen die im Folgenden erklärt werden:

# SSH
1. Melde Dich via SSH auf deiner ***recalbox*** an
2. Aktiviere die Schreibrechte auf der Systempartition mit `mount -o remount,rw /`
3. Wechsle in das `share_init` Verzeichnis von EmulationStation mit `cd /recalbox/share_init/system/.emulationstation`
4. Stoppe EmulationStation mit `/etc/init.d/S31emulationstation stop`
5. Bearbeite die `es_system.cfg` Datei mit `nano es_system.cfg`
6. In oben genannter Datei findest Du alle Systeme, die von EmulationStation unterstützt werden. Ändere einfach die Reihenfolge der Einträge nach belieben. Ein System geht immer von `<system>` bis `</system>`
7. Speichere deine Änderungen
8. Starte EmulationStation mit `/etc/init.d/S31emulationstation start`
9. Die neue Reihenfolge wird nun angezeigt. 

# Lokales Terminal
1. Drücke **F4**, um EmulationStation zu beenden
2. Drücke **ALT+F2**, um das Terminal zu öffnen
3. Melde Dich mit `root` als Benutzername und mit `recalboxroot` als Passwort an
4. Aktiviere die Schreibrechte auf der Systempartition mit `mount -o remount,rw /`
5. Wechsle in das `share_init` Verzeichnis von EmulationStation mit `cd /recalbox/share_init/system/.emulationstation`
6. Bearbeite die `es_system.cfg` Datei mit `nano es_system.cfg`
7. Speichere deine Änderungen
8. Starte EmulationStation mit `/etc/init.d/S31emulationstation start`
9. Die neue Reihenfolge wird nun angezeigt.

# Alternativer Weg
Kopiere die `es_systems.cfg` Datei via [SCP](https://github.com/recalbox/recalbox-os/wiki/Netzwerk-Zugriff-mit-WinSCP-%28DE%29) auf deinen Rechner und bearbeite sie dort lokal in einem Texteditor wie **UltraEdit**, oder **Notepad++**. Bedenke aber, dass Du die Schreibrechte auf dem PI aktivieren musst (s.o.), um die Datei dann wieder auf den PI kopieren zu können!

# Hinweise
* Leider ist es zur Zeit nicht möglich, die Favoriten an erster Stelle anzeigen zu lassen.
* Bevor Du die Datei änderst, solltest Du ein Backup anlegen, falls etwas beim Bearbeiten schief geht!
