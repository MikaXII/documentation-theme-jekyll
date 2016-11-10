---
layout: page
title: Shader Konfiguration (DE)
wikiPageName: Shader-Konfiguration-(DE)
menu: wiki
---

### I - Einleitung
Shader sind Filter die das Bild während des Spielens verändern. Diese werden oft gebraucht um ein «Retro»-Bild zu erhalten, welches der Optik eines alten Röhrenbildschirms sehr nahe kommt.
Die verschiedenen Dateien in **_recalbox_** sind folgende:
- **glsl**: Der Shader selbst
- **glslp**: Die Shader-Voreinstellung. Kann mehrere Shader miteinander kombinieren.
- `/recalbox/share_init/system/configs/shadersets/xxx.cfg`: Die Konfigurationsdateien für die Shader-Sets.

Die Shader-Set Konfigurationsdatei (**.cfg**) referenziert auf eine Shader–Voreinstellung (**glslp**) für jedes System auf der **_recalbox_**. Jede **glslp** Datei referenziert auf eine, oder mehrere, Shader–Dateien (**glsl**).

### II – Shader-Sets
Mit den Shader-Sets können Shader für alle Systeme mit nur einer einzigen Einstellung konfiguriert werden. Die Sets werden durch die Community erstellt und werden für jede neue **_recalbox_**–Version optimiert.

Verfügbare Sets: 
- **scanlines**: Scanlines für alle Emulatoren aktivieren.
- **retro**: Wählt den «besten» Shader für jedes System, um dem originalen Spielerlebnis am nächsten zu kommen. Diese Shader wurden durch die Community ausgewählt.
- **none**: Keine Shader aktiv.

Das **Shader-Set**, welches aktiviert werden soll, kann im EmulationStation Menü unter **SPIELEINSTELLUNGEN**, oder direkt in der [[recalbox.conf|recalbox.conf-(DE)]] mit `global.shaderset` ausgewählt werden.

### III - Selbstgemachte Shader
Du kannst die Power der **Shader-Sets** mit einer Anpassung der [[recalbox.conf|recalbox.conf-(DE)]] kombinieren.

Das Set `global.shaderset` kann als Basis für jeden Emulator ausgewählt werden. Danach kann die Shader-Voreinstellung von einem System mit der Option `systemname.shader` individuell angepasst werden.
Die Standard Shader-Voreinstellungen sind abgelegt unter `/recalbox/share_init/shaders/`.   

**Beispiel:**
Du willst die "besten" Shader-Einstellungen für alle Emulatoren mit einigen Ausnahmen: 
* Keine Shader für den Gameboy
* eine bereits bestehende Shader-Voreinstellung für den MegaDrive
* eine selbstgemachte Shader–Voreinstellungen für den SNES:   

```
# Retro–Shader für alle Emulatoren aktivieren. Damit wurde die beste Auswahl getroffen.
global.shaderset=retro
# Der Gameboy jedoch erscheint visuell besser ohne aktivierte Shader
gb.shaders=
# Wir benutzen den bereits existierende **4xbr_retro.glslp** Shader für den MegaDrive
megadrive.shaders=/recalbox/share_init/shaders/4xbr_retro.glslp
# Und ich will meine eigene (custom) Shader-Voreinstellung für das SNES aktivieren.
snes.shaders=/recalbox/share/shaders/custom/snes.glslp
```   
   
Die Shader können auch während des Spiels über den Controller gewechselt werden. Dazu werden die [Spezialfunktionen] (https://github.com/recalbox/recalbox-os/wiki/Manual-%28DE%29#duringgame-special) **Hotkey + R2**, oder **Hotkey + L2** benutzt, um den nächsten, oder den vorherigen Shader zu aktivieren.

### IV - Screenshots
Kein Shader:  
![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/shaders/nes-no-filter.png) 

Mit aktiviertem Retro Shader-Set:  
![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/shaders/nes-caligari-115.png)
