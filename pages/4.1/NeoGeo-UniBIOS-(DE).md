---
layout: page
title: NeoGeo UniBIOS (DE)
wikiPageName: NeoGeo-UniBIOS-(DE)
menu: wiki
---

###Was macht UniBIOS überhaupt?  
* Regionen- (Europa/USA/Japan) und Moduswechsel: (AES/MVS)  
* Erhalte Zugriff auf die Soft-DIP-Schalter um den Schwierigkeitsgrad/Leben/Zeit etc. zu ändern.  
* In-Game Cheat-Datenbank  
* Jukebox-Musikplayer… und vieles mehr!  
  
###Wie es in PiFBA installiert wird:  
1. Lade das UniBIOS von hier herunter (Version 3.2): http://unibios.free.fr/download.html  
2. Extrahiere die heruntergeladene Datei und benenne die **_uni-bios.rom_** in **_asia-s3.rom_** um.  
3. Öffne dein eigenes neogeo.zip. Dort sollte sich eine **_asia-s3.rom_**-Datei befinden. Mache davon ein Backup falls nötig.  
4. Ersetze nun diese Datei im neogeo.zip mit der neuen Datei, welche du vorhin umbenannt hast.  
5. Lege das neue neogeo.zip-Archiv wieder zurück in die **_recalbox_** _share_-Ordner _\bios_ und _\finalburnalpha_.  

###Wie es in FBA_libretro installiert wird: 
Starte ein Spiel und öffne das RetroArch-Menü mit **Hotkey + B**.
Navigiere zu  
> Quick Menu > Core Options  
und lege den Neo-Geo-Modus fest:  
> Neo geo mode > unibios  
  
###Benutzung:  
####Für PiFBA
* Starte irgendein NeoGeo Spiel. Du wirst den neuen **UNIVERSE BIOS v3.2**-Startbildschirm bemerken.  
* Während du den Startbildschirm siehst, drücke und halte **BXY** für die Region/Modus-Konfiguration oder **ABX** für das DIP-Schalter-Menü.  
* Um in das In-Game-Menü zu gelangen, müssen **BXY + START** zur gleichen Zeit gedrückt und gehalten werden.  

####Für FBA_libretro
* Starte irgendein NeoGeo Spiel. Du wirst den neuen **UNIVERSE BIOS v3.2**-Startbildschirm bemerken.  
* Während du den Startbildschirm siehst, drücke und halte **CBA (XBA)** für die Region/Modus-Konfiguration. Drücke **C** um zu beenden.  
* Um in das In-Game-Menü zu gelangen, müssen **CBA (XBA) + START** zur gleichen Zeit gedrückt und gehalten werden.  

####Für das DIP-Schalter-Menü in FBA_libretro
Während du den **UNIVERSE BIOS**-Startbildschirm siehst, halte **A+X+Y** gedrückt.  
  
Konfiguration der Soft-DIP-Schalter:  
<a href="http://www.zimagez.com/zimage/retroarch-1108-152444.php" target="_blank" title="Visionner l'image"><img src="http://www.zimagez.com/miniature/retroarch-1108-152444.png" alt="Visionner l'image" /></a>  
  
Für aktiviertes Blut: Region: Japan / Mode: Arcade  
  
Slot Metal Slug  
<a href="http://www.zimagez.com/zimage/retroarch-1108-152450.php" target="_blank" title="Visionner l'image"><img src="http://www.zimagez.com/miniature/retroarch-1108-152450.png" alt="Visionner l'image" /></a>  
  
Blut > aktiv  
<a href="http://www.zimagez.com/zimage/retroarch-1108-152456.php" target="_blank" title="Visionner l'image"><img src="http://www.zimagez.com/miniature/retroarch-1108-152456.png" alt="Visionner l'image" /></a>  
  
Drücke **C** um zu beenden.  
  
###BIOS
 NeoGeo benötigt eine neogeo.zip BIOS-Datei. Diese Datei wird am gleichen Ort wie deine ROMs abgelegt: 

    shell
    /recalbox/share/roms/neogeo
    oder
    /recalbox/share/roms/fba_libreto
    oder
    /recalbox/share/roms/fba  
  
Dies ist der Inhalt einer verifzierten und funktionstüchtigen neogeo.zip BIOS-Datei:  
  
    shell
    000-lo.lo
    asia-s3.rom
    japan-j3.bin
    neo-geo.rom
    ng-lo.rom
    ng-sfix.rom
    ng-sm1.rom
    sfix.sfix
    sm1.sm1
    sp-1v1_3db8c.bin
    sp-45.sp1
    sp-e.sp1
    sp-j2.sp1
    sp-s.sp1
    sp-s2.sp1
    sp-u2.sp1
    sp1.jipan.1024
    uni-bios_1_0.rom
    uni-bios_1_1.rom
    uni-bios_1_2.rom
    uni-bios_1_2o.rom
    uni-bios_1_3.rom
    uni-bios_2_0.rom
    uni-bios_2_1.rom
    uni-bios_2_2.rom
    uni-bios_2_3.rom
    uni-bios_2_3o.rom
    uni-bios_3_0.rom
    uni-bios_3_1.rom
    vs-bios.rom  
  
