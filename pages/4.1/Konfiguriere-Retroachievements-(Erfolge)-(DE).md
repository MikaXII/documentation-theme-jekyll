---
layout: page
title: Konfiguriere Retroachievements (Erfolge) (DE)
wikiPageName: Konfiguriere-Retroachievements-(Erfolge)-(DE)
menu: wiki
---

##Herausforderungen/Erfolge mit RetroArch
Die Webseite [retroachievements.org](http://www.retroachievements.org) bietet Herausforderungen/Erfolge/Trophäen für Plattformen wie z.B. NES, SNES, GB, GBC, GBA, Genesis/Megadrive, TurboGrafx16/PCEngine an.  
  
Diese Heraufsforderungsfunktionalität wurde Stück für Stück zu RetroArch hinzugefügt.
  
##Account erstellen
[Registriere](http://retroachievements.org/createaccount.php) dich auf [retroachievements.org](http://www.retroachivements.org).  
Merke dir unbedingt deinen Nickname (Benutzername) sowie dein Passwort. Diese Angaben werden später gebraucht um RetroAchievements in RetroArch zu konfigurieren.  

##Account-Aktivierung in EmulationStation unter ***recalbox*** 4.0.0
* Verbinde eine Tastatur mit deiner ***recalbox***
* Öffne das EmulationStation-Menü (mit Start)
Navigiere zu `Spieleinstellungen > Retroachievements Einstellungen`  
  
![](https://github.com/lackyluuk/recalbox-os/blob/master/wiki/images/Retroachievementseinstellungen.png)
![](https://github.com/lackyluuk/recalbox-os/blob/master/wiki/images/Retroachievements.png) 
    
* RetroAchievements > **ON**  
  
* Benutzername > Trage hier deinen **Nickname** ein  
  
* Passwort > Trage hier dein **Passwort** ein  
  
##Account-Aktivierung (manuell) unter ***recalbox*** 4.0.0
###Bearbeite die recalbox.conf-Datei
Via SSH mit PuTTY und dem Befehl `nano`:  
  
* `nano /recalbox/share/system/recalbox.conf` (Leerschlag zwischen `nano` und `/`)  
  
oder mit 
  
* [WinSCP und dem Texteditor Notepad++]( https://github.com/recalbox/recalbox-os/wiki/Netzwerk-Zugriff-mit-WinSCP-(DE))  
  
Füge die folgenden Zeilen hinzu und ersetze `username` und `password` mit den Angaben, die du bei der Registrierung gewählt hast.  
  
    ## Enable retroarchievements (0,1)   
    ## Lege dein www.retroachievements.org username/password fest  
    global.retroachievements=1  
    global.retroachievements.username=username  
    global.retroachievements.password=password  
  
Speichere die recalbox.conf-Datei ab und starte deine ***recalbox*** neu.  

##Konfiguration von mit RetroAchievements kompatiblen Emulatoren/Cores 
Nicht jede *libretro* Core ist mit RetroAchievements kompatibel. Nachfolgend siehst du eine Liste mit Emulatoren/Cores, die mit RetroArch/RetroAchievements arbeiten.  
  
Öffne das EmulationStation-Menü (mit Start) und navigiere zu Spieloptionen > Erweitert >  
  
* NES > EMULATOR LIBRETRO > CORE QUICKNES  
* SNES > EMULATOR LIBRETRO > CORE SNES9X_NEXT  
* GB/GBC/GBA > DEFAULT  
* MEGADRIVE > DEFAULT (picodrive)  
* PCENGINE > DEFAULT (Dies wird derzeit nicht durch die libretro Core unterstützt)  
  
So könnte deine RetroAchievements-Seite dann aussehen. Hier kannst du auch neue Herausforderungen finden, die es zu meistern gilt.  
  
<a href="http://www.zimagez.com/zimage/retroachivement.php" target="_blank" title="Visionner l'image"><img src="http://www.zimagez.com/miniature/retroachivement.png" alt="Visionner l'image" /></a>  
  
Um die verfügbaren Herausforderungen/Trophäen eines Spiels in RetroArch sehen zu können, musst du das RetroArch-Menü mit **Hotkey+B** öffnen. Navigiere dann zu Quick Menu> Achievements list.  
  
Besuche [diese Seite](http://retroachievements.org/gameList.php) für eine Liste von kompatiblen Spielen.  
