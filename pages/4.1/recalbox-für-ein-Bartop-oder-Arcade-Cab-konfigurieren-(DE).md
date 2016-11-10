---
layout: page
title: recalbox für ein Bartop oder Arcade Cab konfigurieren (DE)
wikiPageName: recalbox-für-ein-Bartop-oder-Arcade-Cab-konfigurieren-(DE)
menu: wiki
---

***recalboxOS*** eignet sich hervorragend für eine **Arcade Maschine** oder ein **Bartop**. Im Folgenden wird erklärt, wie du deine ***recalbox*** sehr einfach für deine Bedürfnisse konfigurieren kannst.  
  
### A – GPIO
  
Der ***recalbox*** GPIO-Treiber lässt sich in der [[recalbox.conf|recalbox.conf-(DE)]] konfigurieren. Dieser Treiber erlaubt es dir zwei Controller (Je ein 4-Weg-Joystick sowie 9 Buttons) auf dem System zu erzeugen, welche direkt über die Raspberry Pi GPIO-Pins angeschlossen werden.  
  
Auf diese Weise benötigst du keine Dritt-USB-Controller mehr. Du musst lediglich deine Steuerelemente (Joystick und Buttons) an die GPIO-Pins anschliessen.  
  
Siehe [[GPIO Controller im Mini How-To|GPIO-Controller-(DE)]]  
  
### B – Video-Konfiguration
  
Viele Bartops oder Arcade-Maschinen werden mit alten LCD- oder Röhrenbildschirmen gebaut. 
  
- VGA Bildschirm  
Wenn du einen VGA Bildschirm verwendest, brauchst du einen HDMI-zu-VGA-Konverter (Aktiver Konverter). Dazu brauchst du nicht unbedingt das teuerste Modell. Ein günstiges funktioniert genauso. Wenn du einen 4:3-Bildschirm hast, kannst du zusätzlich noch den Video-Modus aller deiner Spiele auf `default` ändern in der [[recalbox.conf|recalbox.conf-(DE)]]. (`global.videomode=default`).
  
- DVI Bildschirm  
Wenn du einen DVI Bildschirm verwendest, brauchst du einen HDMI-zu-DVI-Konverter (Passiver Konverter). Zusätzlich musst du die **config.txt** ändern. Was du genau ändern musst, kannst du hier nachlesen:  
  
[[Verbinde deine recalbox mit einem DVI Bildschirm|Verbinde-deine-recalbox-mit-einem-DVI-Bildschirm-(DE)]]  
  
- Kathodenstrahlröhre (CRT) Bildschirm  
Wenn du einen Kathodenstrahlröhren-Bildschirm verwendest, brauchst du einen Mini-Klinke(3.5mm)-zu-RCA (Video)-Adapter. RCA sind die Cinch-Stecker Gelb (Komposit-Video) sowie Rot und Weiss (Stereo-Audio). Der Video-Modus aller deiner Spiele muss auf `default` geändert werden in der [[recalbox.conf|recalbox.conf-(DE)]]. (`global.videomode=default`). Zusätzlich musst du noch die **config.txt** ändern. Was du genau ändern musst, kannst du hier nachlesen:  
  
[[Verbinde deine recalbox mit einem CRT (Kathodenstrahlröhrenbildschirm) per Composite|Verbinde-deine-recalbox-mit-einem-CRT-per-Composite-(DE)]].  
  
### C – Audio-Konfiguration
Du kannst den Audio-Ausgang deines Raspberry Pis in der [[recalbox.conf|recalbox.conf-(DE)]] ändern. Benutze `audio.device=jack` wenn du das Audiosignal über die 3.5mm Klinkenbuchse oder `audio.device=hdmi` wenn du es über die HDMI-Buchse ausgeben möchtest. Hast du `audio.device=auto` eingestellt, dann hat der HDMI-Ausgang Vorrang gegenüber dem Klinken-Ausgang.  
  
### D – Menü-Konfiguration
Für dein Bartop oder deine Arcade-Maschine benötigst du Kodi eventuell nicht. Dazu kannst du Kodi über die [[recalbox.conf|recalbox.conf-(DE)]] (`kodi.enabled=0`) deaktivieren. Das führt dazu, das der Kodi-Shortcut auf dem X-Button nicht mehr funktioniert sowie der Eintrag aus dem Hauptmenü verschwindet.
Falls du noch andere Menü-Einstellungen ändern möchtest, kannst du das ebenfalls in der [[recalbox.conf|recalbox.conf-(DE)]] machen: 
  
####Für EmulationStation:
  
- Wenn du den Eintrag `system.es.menu` auf `bartop` einstellst, hast du nur noch Zugriff auf einige wenige Optionen, wenn du das Menü in EmulationStation (START Button) öffnest.  
  
- Wenn du den Eintrag `system.es.menu` auf `none` einstellst, ist das Start Menü (START Button) nicht mehr verfügbar. Lediglich das Menü über den SELECT Button lässt sich noch öffnen (Z.B. in der Spielliste).  
  
####Für Emulatoren:
  
- Wenn du den Eintrag `system.emulators.specialkey` auf `nomenu` einstellst, hast du keinen Zugriff mehr auf das Menü der einzelnen Emulatoren.  
  
- Wenn du den Eintrag `system.emulators.specialkey` auf `none` einstellst, deaktivierst du alle Spezialbefehle (Hotkey Befehle) ausser die Exit-Kombination in allen Spielen.
