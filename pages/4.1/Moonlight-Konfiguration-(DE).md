---
layout: page
title: Moonlight Konfiguration (DE)
wikiPageName: Moonlight-Konfiguration-(DE)
menu: wiki
---

#**1. Intro**
Moonlight ist eine Open-Source Version von Nvidias GameStream-Technologie. Falls dein PC die Voraussetzungen erfüllt, kannst du die meisten deiner Spiele auf deine ***recalbox*** streamen. ***recalbox*** liest die Controller-Konfiguration von EmulationStation und konvertiert diese dann zu Moonlight.  
  
##Moonlight-Features auf der ***recalbox***
* Streamt Spiele über dein lokales Netzwerk oder über das Internet
* Unterstützung für bis zu 4 Spieler
* Anzeige bis zu 1080p/60fps
* Hardwarebeschleunigte H264-Decodierung auf jeder beliebigen Version des Raspberry Pis
* Unterstützung für Tastatur und Maus
* Unterstützung bis zu GFE 2.11  
  
##Anforderungen
***recalbox*** und PC-Anforderungen um Moonlight zu benutzen:
* Einen konfigurierten Controller in EmulationStation
* Steam-Account (Optional) oder stand-alone unterstützte Spiele (siehe https://shield.nvidia.com/game-stream)
* Eine von Nvidia unterstützte GPU (siehe http://www.geforce.com/geforce-experience/system-requirements)
* Es wird empfohlen eine Ethernet-Verbindung zu benutzen. WiFi ist nicht zuverlässig genug und es können Geschwindigkeitsprobleme auftauchen.  

**Wenn du ein Upgrade von 3.3.0 auf 4.0.0 machst, lies bitte folgendes sorgfältig durch.**

#**2. Moonlight-Konfiguration**
Prüfe zuerst deine ***recalbox***-Version und fahre dann beim jeweiligen Kapitel A, B, C oder D fort.  

##A: Version >= 4.0.0 beta1
***recalbox*** 4.0.0 führt neue Features für Moonlight ein:  
  
* Gamepads werden automatisch für Moonlight konfiguriert
* Einfache Konfiguration: Du musst keine Computer IP-Adresse mehr spezifizieren
* Moonlight-Parameter können in der folgenden Datei verändert werden: `/recalbox/share/sysem/configs/moonlight/moonlight.conf`.  
Oder über das Netzwerk: `\\recalbox\User Data\system\configs\moonlight\moonlight.conf`  
  
**Bitte beachten**: 
* ***recalbox*** 4.0.0-beta2 unterstützt Moonlight viel besser, verglichen zur Version 4.0.0-beta1. Es wird somit empfohlen, dass du ein Upgrade durchführst.
* Der konfigurationslose Setup-Prozess funktioniert nur zuverlässig, wenn du nur **1** GameStream-kompatiblen Computer hast. Hast du mehrere, so musst du die IP-Adresse von deinem GameStream-Host in der Konfiguration spezifizieren.
* Es kann vorkommen, dass IPv6 anstelle von IPv4 verwendet wird. Um das zu vermeiden, schalte IPv6 in Windows ab.
* Benutze immer die neueste Version von ***recalbox***. Mit Version 4.0.0-beta4 wurde die GFE 2.11-Unterstützung eingeführt.
* Wenn du beim Pairing stecken bleibst: Lösche die Datei `/recalbox/share/system/configs/moonlight/keydir`, entferne alle Geräte in GFE, logge dich bei deinem Nvidia-Accoount ein und versuche erneut zu pairen.    
  
**Controller-Konfiguration** : Falls dein verwendeter Controller in Moonlight nicht wie erwartet funktioniert, versuche eine Neukonfiguration in EmulationStation und versuche es danach erneut.
  
Nun bist du bereit, deine ***recalbox*** für das Gamestreaming vorzubereiten:
  
1. Beende EmulationStation (via SSH oder F4 drücken)  
2. Einloggen als root-Benutzer (siehe [hier]( https://github.com/recalbox/recalbox-os/wiki/Root-Zugriff-auf-dem-Terminal-(DE)))  
3. Navigiere zu Moonlight: `cd /recalbox/scripts/moonlight`  
4. Stelle sicher, dass nur dein GameStream-kompatibler Computer im Netzwerk vorhanden ist  
5. Führe `./Moonlight.sh` pair aus und tippe die erhaltene Zahl in deinen PC ein  
6. Sobald dein Computer und deine ***recalbox*** gepaart sind, führe `./Moonlight.sh init` aus um die Datenlinks zu deinen ROMs herzustellen. Diese Daten werden von EmulationStation und Scraper benutzt um die ROMs anzuzeigen.  
7. Starte EmulationStation neu und geniesse Moonlight!  
  
Hier siehst du den Vorgang um deinen PC mit deiner ***recalbox*** zu pairen:  
  
    Username: root
    Password: recalboxroot
    # /etc/init.d/S31emulationstation stop
    # cd /recalbox/scripts/moonlight
    # ./Moonlight.sh pair
    Moonlight Embedded 2.2.0 (EMBEDDED;CEC;PI)
    Too many options: No such file or directory
    Moonlight Embedded 2.2.0 (EMBEDDED;CEC;PI)
    Searching for server...
    Connect to 192.168.0.28...
    Generating certificate...done
    NVIDIA GeForce GTX 960M, GFE 2.11.4.0 (protocol version 7)
    Please enter the following PIN on the target PC: 3660
    1017 / 1017
    Succesfully paired
    # ./Moonlight.sh init
    Fetching games from  ...
    Scraping games ...
    # /etc/init.d/S31emulationstation start  
  
Optionaler Schritt wenn du noch weitere GameStream-kompatible Computer hast:  
* Bearbeite `/recalbox/share/sysem/configs/moonlight/moonlight.conf`
* Enterne das Zeichen `#` vor `#address =`
* Tippe deine IP-Adresse ein. Zum Beispiel: `address = 192.168.0.12`
* Datei speichern und schliessen 
  
Zurzeit kann ***recalbox*** nur ein GameStream-PC verarbeiten. Eine Unterstützung für mehrere Host-PCs wird eventuell durch einen zukünftigen Release ermöglicht.  
  
##B: Version >= 3.3.0 beta15
1. Beende EmulationStation (via SSH oder F4 drücken)
2. Einloggen als root-Benutzer (siehe [hier]( https://github.com/recalbox/recalbox-os/wiki/Root-Zugriff-auf-dem-Terminal-(DE)))  
3. Stelle sicher, dass `/recalbox/share/roms/moonlight` existiert. Falls nicht, erstelle den Ordner mit `mkdir -p /recalbox/share/roms/moonlight`  
4. Navigiere zu Moonlight: `cd /recalbox/scripts/moonlight ` 
5. Bearbeite Moonlight.sh mit `nano Moonlight.sh` und füge bei `moonlight_ip=` die IP-Adresse ein, von der du streamen willst. Zum Beispiel, wenn die IP-Adresse deines Computers `192.168.1.1` lautet, so ändere die Zeile ab in `moonlight_ip=192.168.1.1`. Speichere und beende den Texteditor.  
6. Führe `./Moonlight.sh pair` aus und tippe die erhaltene Zahl in deinen PC ein  
7. Sobald dein Computer und deine ***recalbox*** gepaart sind, führe `./Moonlight.sh init` aus um die Datenlinks zu deinen ROMs herzustellen. Diese Daten werden von EmulationStation und Scraper benutzt um die ROMs anzuzeigen.  
8. Führe `./Moonlight.sh map` aus um deinen Controller zu konfigurieren. Zurzeit wird nur ein 1-Player-Controller unterstützt. Die Tastatur sowie die Maus funktionieren tadellos.  
9. Starte EmulationStation neu und geniesse Moonlight!  

##C: 3.3.0 beta7 <= Version < 3.3.0 beta15
Navigiere zu `\\recalbox\roms\moonlight` oder über SSH zu `/recalbox/share/roms/moonlight`. In diesem Ordner findest du:  
  
* Moonlight.sh.hide 
* Moonlight.conf  
  
##D: Version < 3.3.0 beta7
Hier findest du die Moonlight.sh.hide-Datei =>  
  
Benenne `Moonlight.sh.hide` zu `Moonlight.sh` um. Öffne die Datei mit Notepad++ oder einem anderen Programm deiner Wahl und ersetze den Inhalt mit diesem hier: [Moonlight.sh.hide_v2](https://github.com/steak3/recalbox-buildroot/blob/unified/board/recalbox/share/roms/moonlight/Moonlight.sh.hide_v2).  
Die Zeile `moonlight_ip=YOUR_IP_HERE` muss danach so abgeändert werden, dass die IP-Adresse deines Computers drinsteht (`moonlight_ip=192.168.x.x`).  
  
Die Datei speichern und beenden.  
  
remove **Moonlight.conf** possible problem here
  
Führe folgenden Befehl mit SSH in `/recalbox/share/roms/moonlight` aus:  
  
`./Moonlight.sh pair`  
  
Wenn der Befehl erfolgreich ausgeführt wurde, siehst du folgende Nachricht:  
  
    **Too many options: No such file or directory
    Can't open configuration file: hosts/192.168.x.x.conf
    Generating certificate...done
    Please enter the following PIN on the target PC: 9958
    Succesfully paired**  
  
Auf deinem PC sollte nun eine Nvidia-Nachricht erscheinen um den erhaltenen Pin einzugeben.  
  
Nun musst du deinen Controller konfigurieren. Führe dazu diesen Befehl aus:  
  
`./Moonlight.sh map ` 
  
und folge den Anweisungen auf dem Bildschirm.  
  
Starte deine ***recalbox*** neu und los geht es mit Moonlight.  

#**3. ANNEXE**
##Version 4.0.0 spezifisch
Nur für fortgeschrittene User: Es ist auch möglich von einem entfernten Computer über das Internet zu streamen. Dazu muss die folgende Datei geändert werden um die Remote-Host-IP-Adresse zu spezifizieren: `/recalbox/scripts/moonlight/Moonlight.sh`  
  
Die gleiche IP-Adresse muss auch in der `moonlight.conf`-Datei eingefügt werden. Danach muss noch das „Port-Forwarding“ konfiguriert werden gemäss https://github.com/moonlight-stream/moonlight-android/wiki/Setup-Guide#streaming-over-the-internet.  
##Version 3.3.0 spezifisch
Die Bildanzeige kann in Moonlight konfiguriert werden.  
  
720p in 30fps  
1080p in 30fps  
  
720p in 60fps  
1080p in 60fps  
  
Dazu muss Linie 23 in `Moonlight.sh` abgeändert werden. Ersetze die **fettgedruckten** Parameter mit denen, die du benötigst:  
  
_cmd="moonlight stream -remote -**1080 -60fps** -keydir ${moonlight_keydir} –mapping ${moonlight_mapping} ${moonlight_ip}" ;;_
