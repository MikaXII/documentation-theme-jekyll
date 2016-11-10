---
layout: page
title: recalbox.conf (DE)
wikiPageName: recalbox.conf-(DE)
menu: wiki
---

## Einleitung 

Das recalboxOS hat ein fortgeschrittenes Konfigurations-Werkzeug names `recalbox.conf` und erlaubt Dir einige Einstellungen zu verändern, die sonst nicht in EmulationStation verfügabr sind.  

Du kannst diese Datei bearbeiten : 
- Benutze die network shared Ordner von recalbox. Die Datei befindet sich im Verzeichnis **`system`** dieses beinhaltet **`recalbox.conf`**
- Du kannst Dich [[als root Benutzer verbinden|Root-access-on-terminal-(DE)]] und die Datei im System bearbeiten in `/recalbox/share/system/recalbox.conf` 

**Windows Benutzer** : Du musst eine richtiges Textbearbeitungs-Programm benutzen, wie z.B. **NotePad++**. Der Standard Windows Text Editor würde ungültige Zeichen in die Datei einfügen. 

Das **;** bei Zeilenbeginn bedeutet, das diese Zeile deaktiviert ist. Lösche **;** um die Zeile zu aktivieren.

Diese Datei wird bei einer racalbox Aktualisierung nicht überschrieben. Aber recalbox.conf.template wird überschrieben, so kann es möglich sein, das Du nach einer Aktualisierung dort neue Einstellungen findest.

## I - Verfügbare Einstellungen

- **A - Kodi**
 - hide kodi in emulationstation (Kodi in EmulationStation verstecken)
 - start kodi on system startup (Kodi beim Systemstart starten)
 - avoid x button to start kodi (vermeide den X Button um Kodi zu starten)
- **B - Network**
 - set hostname (Netzwerknamen festlegen)
 - set wifi ssid and key (Wifi (SSID) und Passwort (Schlüssel) festlegen)
- **C - Audio**
 - set output device (Ausgangsgerät festlegen)
 - set audio volume (Audio Lautstärke einstellen)
 - enable / disable background music in es (Hintergrundmusik in EmulationStation einschalten / ausschalten)
- **D - Controllers**
 - select ps3 driver (PS3 Treiber auswählen)
 - enable / disable xboxdrv (xboxdrv einschalten / ausschalten)
 - set xboxdrv controllers (xboxdrv Controller einstellen)
 - enable / disable controllers on gpio (Controller an GPIO einschalten / ausschalten)
 - enable / disable controllers on marqs DB9 (Controller an Marqs DB9 einschalten / ausschalten)
 - enable / disable controllers on marqs gamecon (Controller an Marqs gamecon einschalten / ausschalten)
- **F - Language and keyboard**
 - set language (Sprache festlegen)
 - set keyboard layout (Tastatur Layout festlegen)
 - set time zone (Zeitzone einstellen)
- **G - UPDATES**
 - enable / disable update checking (Prüfung auf Aktualisierungen einschalten / ausschalten)
- **H - EMULATOR CONFIGURATION - detailed below**

### A - Emulator configuration
#### 1 - Global configuration
You can fine tune emulators in recalbox.conf. The global variable set the preferences for all emulators.

**Available variables :**
* **videomode** : set videomode (use tvservice to get compatible values). Use _default_ to disable videomode switch (for crt)   
example : `global.videomode=CEA 4 HDMI`
* **shaders** : set the absolute path to the shader or shader preset (glsl or glslp)  
example : `global.shaders=/recalbox/share/shaders/shaders_glsl/scanline.glsl`
* **ratio** : set the ratio for games (_16/9_, _4/3_, _16/10_, _auto_ or _custom_)  
example : `global.ratio=16/9`
* **smooth** : smooth games  
example : `global.smooth=0`
* **rewind** : enable rewind in games (can slow down emulators)  
example : `global.rewind=0`
* **inputdriver** : force input drivers for retroarch (auto, sdl2, udev)  
example : `global.inputdriver=auto`

The default configuration : 
```
global.videomode=CEA 4 HDMI
global.shaders=
global.ratio=auto
global.smooth=1
global.rewind=0
global.inputdriver=auto
```
If you want to enable smoothing for all emulators, set `global.smooth=1`.  
If you want to add a scanline shader for all all emulators, set `global.shaders=/recalbox/share/shaders/shaders_glsl/scanline.glsl`.


#### 2 - Specific emulator configuration
Each emulator can be configured here. Just use the name of the system and set variables.

**Available systems :**

_snes_
_, nes_
_, n64_
_, gba_
_, gb_
_, gbc_
_, fds_
_, virtualboy_
_, sg1000_
_, mastersystem_
_, megadrive_
_, gamegear_
_, sega32x_
_, segacd_
_, neogeo_
_, mame_
_, fba_
_, fbalibretro_
_, ngp_
_, gw_
_, vectrex_
_, lynx_
_, lutro_
_, wswan_
_, pcengine_
_, atari2600_
_, atari7800_
_, msx_
_, prboom_
_, psx_

**Available libretro cores :**  

* **snes :** pocketsnes - snes9x_next - catsfc  
* **nes / fds :** fceumm - fceunext - nestopia  
* **n64 :** mupen64plus  
* **gb/gbc :** gambatte - tgbdual  
* **virtualboy :** vb  
* **megadrive / mastersystem / gamegear / sega32x / segacd / sg1000 :** genesisplusgx - picodrive  
* **neogeo :** imame4all - fba  
* **mame :** imame4all  
* **fbalibretro :** fba  
* **ngp :** mednafen_ngp  
* **gw :** gw  
* **vectrex :** vecx  
* **lynx :** mednafen_lynx  
* **lutro :** lutro  
* **wswan :** mednafen_wswan  
* **pcengine :** mednafen_supergrafx - pce  
* **atari2600 :** stella  
* **atari7800 :** prosystem  
* **msx :** fmsx - bluemsx  
* **prboom :** prboom  
* **psx :** pcsx_rearmed  
* **cavestory :** nxengine  

**Available variables :**
* **videomode** : set videomode (use tvservice to get compatible values).  
example : `snes.videomode=CEA 4 HDMI`
* **shaders** : set the absolute path to the shaderor shader preset (glsl or glslp)  
example : `snes.shaders=/recalbox/share/shaders/shaders_glsl/snes.glsl`
* **ratio** : set the ratio for games (_16/9_, _4/3_, _auto_or _custom_)  
example : `snes.ratio=4/3`
* **smooth** : smooth games  
example : `snes.smooth=0`
* **rewind** : enable rewind in games (can slow down emulators)  
example : `snes.rewind=1`
* **core** : select the core for the emulation (libretrocores are located in /usr/lib/libretro)
example : `snes.core=snes9x_next`
* **emulator** : select the emulator for the emulation (emulators are retorarch, fba2x, mupen64)
example : `neogeo.emulator=fba2x`
* **configfile** : force your own configuration file to be loaded. The recalbox will not automatize emulator configuration
example : `snes.configfile=/path/to/my/configfile.cfg`



## II - The default recalbox.conf

```
# System Variable
# You can configure your recalbox from here
# To set a variable, remove the first ; on the line


# ------------ A - Kodi ----------- #
## Show or hide kodi in emulationstation (0,1)
kodi.enabled=1
## Start kodi at launch (0,1)
kodi.atstartup=0
## set x button shortcut (0,1)
kodi.xbutton=1



# ------------ B - Network ------------ #
## Set system hostname
system.hostname=RECALBOX
## Activate wifi (0,1)
wifi.enabled=0
## Wifi SSID (string)
;wifi.ssid=new ssid
## Wifi KEY (string)
;wifi.key=new key



# ------------ C - Audio ------------ #
## Set the audio device (auto, hdmi, jack)
audio.device=auto
## Set system volume (0..100)
audio.volume=90
## Enable or disable system sounds in ES (0,1)
audio.bgmusic=1



# -------------- D - Controllers ----------------- #
## Please enable only one of these

# -------------- D1 - PS3 Controllers ------------ #
##Enable PS3 controllers support
controllers.ps3.enabled=1
## Choose an driver beetween official, shanwan and gasia if you have dualshock clones (official,shanwan,gasia)
controllers.ps3.driver=official


# ------------ D2 - XBOX Controllers ------------ #
## Xbox controllers are already supported, but xboxdrv can solve some compatibility issues 
## Enable xboxdrv driver, disable this if you enabled ps3 controllers (0,1)
controllers.xboxdrv.enabled=0
## Set the amount of controllers to use with xboxdrv (0..4)
controllers.xboxdrv.nbcontrols=2


# ------------ D3 - GPIO Controllers ------------ #
## GPIO Controllers
## enable controllers on GPIO with mk_arcarde_joystick_rpi (0,1)
controllers.gpio.enabled=0
## mk_gpio arguments, map=1 for one controller, map=1,2 for 2 (map=1,map=1,2)
controllers.gpio.args=map=1,2


## DB9 Controllers
## Enable DB9 drivers for atari, megadrive, amiga controllers (0,1)
controllers.db9.enabled=0
## db9 arguments
controllers.db9.args=map=1

## Gamecon controllers
## Enable gamecon controllers, for nes, snes psx (0,1) 
controllers.gamecon.enabled=0
## gamecon_args
controllers.gamecon.args=map=1



# ------------ F - Language and keyboard ------------ #
## Set the language of the system (fr_FR,en_US,en_GB,de_DE,pt_BR,es_ES)
system.language=en_US
## set the keyboard layout (fr,en,de,us,es)
;system.kblayout=us
## Set you local time
## Select your timezone from : ls /usr/share/zoneinfo/ (string)
;system.timezone=Europe/Paris



# ------------ G - UPDATES ------------ #
## Automatically check for updates at start (0,1)
updates.enabled=1



# ------------ H - HERE IT IS - GLOBAL EMULATOR CONFIGURATION ------------ #
## The global value will be used for all emulators, exept if the value
## is redifined in the emulator

## Set game resolution for emulators
## select your mode from the command : tvservice -m [MODE]
## CEA 5 HDMI : 1920x1080 @ 60Hz 16:9, clock:74MHz interlaced 
## CEA 4 HDMI : 1280x720 @ 60Hz 16:9, clock:74MHz progressive
## use 'default' for using the default resolution
## (string)
global.videomode=CEA 4 HDMI

## Set gpslp shader for all emulators. Absolute path (string)
global.shaders=

## Set ratio for all emulators (auto,4/3,16/9,16/10,custom)
global.ratio=auto

## Set smooth for all emulators (0,1)
global.smooth=1

## Set rewind for all emulators (0,1)
global.rewind=0

## Set retroarch input driver (auto, udev, sdl2)
## If you don't have issues with your controllers, let auto
global.inputdriver=auto

## If you do not want recalboxOS to generate the configuration for all emulators (string)
;global.configfile=/path/to/my/configfile.cfg

# ------------ I - EMULATORS CHOICES ----------- #
## You can override the global configuration here
## Here is the snes example
;snes.videomode=CEA 4 HDMI
;snes.core=snes9x_next
;snes.shaders=/recalbox/share/shaders/shaders_glsl/mysnesshader.gplsp
;snes.ratio=16/9
;snes.smooth=0
;snes.rewind=1
;snes.emulator=libretro
## If you do not want recalboxOS to generate the configuration for the emulator : 
;snes.configfile=/path/to/my/configfile.cfg


## use pifba (recommended for rpi1), fbalibretro or imame
neogeo.emulator=fba2x
fba.emulator=fba2x

## N64 core (n64,rice)
## The recommanded plugin is n64, but if your game don't start, try rice (example Zelda Ocarina of Time, Banjo Kazooie, ...)
n64.core=n64
n64.videomode=CEA 4 HDMI

## If you use rice core, set mode 480p as below
;n64.core=rice
;n64.videomode=CEA 3 HDMI


```
