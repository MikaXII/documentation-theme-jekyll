---
layout: page
title: N64: Springt zurück zu ES (DE)
wikiPageName: N64:-Springt-zurück-zu-ES-(DE)
menu: wiki
---

Wenn beim Starten eines N64 Spiels nur ein schwarzer Bildschirm zu sehen ist und kurze Zeit später die Rückkehr in EmulationStation erfolgt, kann das zwei Ursachen haben.

1. Der Controller wurde nicht vollständig konfiguriert
2. Der Video-Modus ist nicht korrekt eingestellt


## 1. Controller konfigurieren:

Bei der Controller-Konfiguration ist es wichtig, dass die "L" Tasten belegt werden. Eine kleine, aber wichtige Konfiguration.   

 
## 2. Video-Modus einstellen:

Mupen64plus wird von _**recalbox**_ nicht automatisch konfiguriert, so wie das der Fall bei den anderen Emulatoren ist. Das muss manuell erledigt werden.

Der N64 Video-Modus wird in der [recalbox.conf](https://github.com/recalbox/recalbox-os/wiki/recalbox.conf-%28DE%29) definiert. 
Als Standard ist `n64.videomode=DMT 9 HDMI` gesetzt.   

Dieser Modus zeigt eine Auflösung von **800x600**.   
Diese Auflösung wurde als Standard definiert, da der RPi2 es sonst nicht schafft, N64 mit einer höheren Auflösung und einer guten Framerate zu emulieren.  
Damit ist **800x600** die **maximale Auflösung** welche in _**recalbox**_ genutzt werden kann.   

Aber nicht alle Bildschirme/TV Geräte sind kompatibel mit dem Video-Modus.   
So kann es passieren, dass beim Starten eines N64 Spiels nur ein schwarzer Bildschirm zu sehen ist und kurze Zeit später die Rückkehr in EmulationStation erfolgt.
In diesem Fall musst Du bestimmen, welche Videomodi mit deinem Bildschirm/TV Gerät kompatibel sind.    

Du benötigst [Root-Zugriff auf dem Terminal](https://github.com/recalbox/recalbox-os/wiki/Root-Zugriff-auf-dem-Terminal-%28DE%29), dann benutze folgende Befehle:  

`tvservice -m DMT`  

und    

`tvservice -m CEA`  

<br>
Nach der Eingabe wird in etwa folgendes erscheinen:   
```
[root@RECALBOX ~]# tvservice -m DMT
Group DMT has 16 modes:
           mode 4: 640x480 @ 60Hz 4:3, clock:25MHz progressive 
           mode 5: 640x480 @ 72Hz 4:3, clock:31MHz progressive 
           mode 6: 640x480 @ 75Hz 4:3, clock:31MHz progressive 
           mode 8: 800x600 @ 56Hz 4:3, clock:36MHz progressive 
           mode 9: 800x600 @ 60Hz 4:3, clock:40MHz progressive 
           mode 10: 800x600 @ 72Hz 4:3, clock:50MHz progressive 
           mode 11: 800x600 @ 75Hz 4:3, clock:49MHz progressive 
           mode 16: 1024x768 @ 60Hz 4:3, clock:65MHz progressive 
           mode 17: 1024x768 @ 70Hz 4:3, clock:75MHz progressive 
           mode 18: 1024x768 @ 75Hz 4:3, clock:78MHz progressive 
           mode 21: 1152x864 @ 75Hz 4:3, clock:108MHz progressive 
           mode 32: 1280x960 @ 60Hz 4:3, clock:108MHz progressive 
           mode 35: 1280x1024 @ 60Hz 5:4, clock:108MHz progressive 
           mode 36: 1280x1024 @ 75Hz 5:4, clock:135MHz progressive 
  (prefer) mode 57: 1680x1050 @ 60Hz 16:10, clock:119MHz progressive 
           mode 58: 1680x1050 @ 60Hz 16:10, clock:146MHz progressive 
```
und    
```
[root@RECALBOX ~]# tvservice -m CEA
Group CEA has 5 modes:
           mode 1: 640x480 @ 60Hz 4:3, clock:25MHz progressive 
           mode 2: 720x480 @ 60Hz 4:3, clock:27MHz progressive 
           mode 3: 720x480 @ 60Hz 16:9, clock:27MHz progressive 
  (native) mode 4: 1280x720 @ 60Hz 16:9, clock:74MHz progressive 
           mode 16: 1920x1080 @ 60Hz 16:9, clock:148MHz progressive 
```

Jetzt hast Du alle Video-Modi, die auf deinem Bildschirm/TV Gerät verwendet werden können.   
Du musst einen Videomodus mit einer Auflösung ** gleich oder kleiner ** bis 800x600 finden, dann definierst Du diesen Modus in der [recalbox.conf](https://github.com/recalbox/recalbox-os/wiki/recalbox.conf-%28DE%29) 

Wenn Ich zum Beispiel diesen Video-Modus wähle:  
 
```
Group CEA has 5 modes:
           mode 1: 640x480 @ 60Hz 4:3, clock:25MHz progressive
```

Editiere Ich meine [recalbox.conf](https://github.com/recalbox/recalbox-os/wiki/recalbox.conf-%28DE%29) etwa so:   
- Standard Video-Modus : `n64.videomode=DMT 9 HDMI`   
- Neuer Video-Modus : `n64.videomode=CEA 1 HDMI`  

###Besondere Fälle : CRT Monitor  
Wenn Du einen ** CRT ** -Bildschirm verwendest, bearbeite den Video-Modus wie folgt:

`n64.videomode=default`  
