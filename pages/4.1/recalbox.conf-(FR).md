---
layout: page
title: recalbox.conf (FR)
wikiPageName: recalbox.conf-(FR)
menu: wiki
---

## Introduction 

Recalbox possède un outil de configuration avancée nommé `recalbox.conf`qui vous permet de modifier des options qui ne sont pas disponibles dans emulationstation.

Pour l'éditer vous pouvez utiliser soit : 
- Les dossiers de recalbox partagés sur le réseau local. Le fichier **`recalbox.conf`** est disponible dans le répertoire nommé **`system`**.
- Un [[accès root|accès-root-sur-Terminal--(FR)]] et éditer le fichier présent dans le système à l'emplacement `/recalbox/share/system/recalbox.conf`.

**Pour les utilisateurs de Windows** : Vous devez utiliser un vrai éditeur de texte, comme **NotePad++**. L'éditeur de texte présent par défaut dans Windows insert de mauvais caractères dans le fichier, le rendant illisible par le système.

Le **;** au début d'une ligne, signifie que celle-ci est désactivée. Retirez le **;** pour activer l'option associée à la ligne.

Ce fichier n'est pas écrasé lors des mises à jour de recalbox, mais le fichier `/recalbox/share/system/recalbox.conf.template`, lui l'est. Vous trouverez, après une mise à jour, les nouvelles options dans ce fichier. Pensez donc à mettre à jour votre `recalbox.conf` après une mise à jour du système.

## I - Options disponibles

- **A - Options Système**
 - activer / désactiver le démarrage automatique de recalbox-manager
 - activer / désactiver un pré-écran de chargement (à utiliser dans le cadre d'un montage de /share sur un NAS)
 - défini le style de menu pour emulationstation
 - cacher kodi dans emulationstation
 - lancer kodi au démarrage du système
 - attribuer le bouton X au démarrage de kodi
- **B - Réseau**
 - définir le "hostname"
 - saisir la clé et SSID du wifi
- **C - Audio**
 - définir la sortie audio
 - définir le volume audio
 - activer / désactiver les musiques en arrière plan de es
- **D - Manettes**
 - activer / désactiver les contrôleurs bluetooth
 - sélectionner le pilote PS3 
 - activer / désactiver xboxdrv
 - définir le nombre de manettes utilisant xboxdrv
 - activer / désactiver les contrôleurs sur gpio
 - activer / désactiver les contrôleurs via le pilote DB9 de marqs
 - activer / désactiver les contrôleurs via le pilote gamecon de marqs
- **F - Langue et clavier**
 - définir la langue
 - définir l'agencement du clavier
 - définir le fuseau horaire
- **G - Mises à jour**
 - activer / désactiver de contrôle de présence des mises à jour
- **H - Configuration des émulateurs - détaillée ci-dessous**

### A - Configuration des émulateurs
#### 1 - Configuration globale

**Variables disponibles :**
* **videomode** : défini le mode vidéo (utilisez tvservice pour obtenir les valeurs compatibles). Utilisez _default_ pour désactiver le switch videomode (pour les écrans crt)   
exemple : `global.videomode=CEA 4 HDMI`
* **shaders** : défini le chemin vers le "shader" ou le "shader preset" (glsl ou glslp)  
exemple : `global.shaders=/recalbox/share/shaders/shaders_glsl/scanline.glsl`
* **ratio** : défini le ratio utilisé pour les jeux (_16/9_, _4/3_, _16/10_, _auto_ ou _custom_)  
exemple : `global.ratio=16/9`
* **smooth** : lissage des jeux  
exemple : `global.smooth=0`
* **rewind** : active / désactive le rembobinage en jeu (peut ralentir l'émulation)  
exemple : `global.rewind=0`
* **inputdriver** : force le pilote "input" utilisé dans retroarch (auto, sdl2, udev)  
exemple : `global.inputdriver=auto`

La configuration par défaut : 
```
global.videomode=CEA 4 HDMI
global.shaders=
global.ratio=auto
global.smooth=1
global.rewind=0
global.inputdriver=auto
```
Si vous souhaitez activer le lissage des jeux pour tous les émulateurs, définissez `global.smooth=1`.  
Si vous souhaitez ajouter des scanlines pour tous les émulateurs, définissez `global.shaders=/recalbox/share/shaders/shaders_glsl/scanline.glsl`.


#### 2 - Configuration spécifique pour chaque émulateur
Chaque émulateur peut être configuré de manière indépendante. Utilisez le nom du système et définissez les variables.

**Systèmes disponibles :**

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

**Liste des cores libretro de chaque système :**  

* **snes :** pocketsnes - snes9x_next - catsfc  
* **nes / fds :** fceumm - fceunext - nestopia  
* **n64 :** mupen64plus  
* **gb/gbc :** gambatte - tgbdual  
* **gba :** gpsp - mgba - meteor   
* **virtualboy :** vb  
* **megadrive / mastersystem / gamegear / sega32x / segacd / sg1000 :** genesisplusgx - picodrive  
* **neogeo :** imame4all - fba  
* **mame :** imame4all - mame2003
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

**Variables disponibles :**
* **videomode** : défini le mode vidéo (utilisez tvservice pour obtenir les valeurs compatibles).  
exemple : `snes.videomode=CEA 4 HDMI`
* **shaders** : défini le chemin vers le "shader" ou le "shader preset" (glsl ou glslp)  
exemple : `snes.shaders=/recalbox/share/shaders/shaders_glsl/snes.glsl`
* **ratio** : défini le ratio utilisé pour les jeux (_16/9_, _4/3_, _16/10_, _auto_ ou _custom_)  
exemple : `snes.ratio=4/3`
* **smooth** : lissage des jeux  
exemple : `snes.smooth=0`
* **rewind** : active / désactive le rembobinage en jeu (peut ralentir l'émulation)  
exemple : `snes.rewind=1`
* **core** : défini le core utilisé pour l'émulation (les cores libretro sont localisés dans /usr/lib/libretro)  
exemple : `snes.core=snes9x_next`
* **emulator** : défini l'émulateur utilisé pour l'émulation (les émulateurs sont : retorarch, fba2x, mupen64)  
exemple : `neogeo.emulator=fba2x`
* **configfile** : force le chargement de votre propre fichier de configuration. Recalbox n'automatisera pas la configuration de l'émulateur.  
exemple : `snes.configfile=/path/to/my/configfile.cfg`



## II - Le fichier recalbox.conf par défaut pour rpi2

```
# System Variable
# You can configure your recalbox from here
# To set a variable, remove the first ; on the line



# ------------ A - System Options ----------- #
#    Uncomment the system.power.switch you use
;system.power.switch=ATX_RASPI_R2_6      # http://lowpowerlab.com/atxraspi/#installation
;system.power.switch=MAUSBERRY           # http://mausberry-circuits.myshopify.com/pages/setup
;system.power.switch=REMOTEPIBOARD_2003  # http://www.msldigital.com/pages/support-for-remotepi-board-2013
;system.power.switch=REMOTEPIBOARD_2005  # http://www.msldigital.com/pages/support-for-remotepi-board-plus-2015
;system.power.switch=PIN56ONOFF          # https://github.com/recalbox/recalbox-os/wiki/Add-a-start-stop-button-to-your-recalbox-(EN)
;system.power.switch=PIN56PUSH           # https://github.com/recalbox/recalbox-os/wiki/Add-a-start-stop-button-to-your-recalbox-(EN)
;system.power.switch=PIN356ONOFFRESET    # https://github.com/recalbox/recalbox-os/wiki/Add-a-start-stop-button-to-your-recalbox-(EN)

## Recalbox Manager (http manager)
system.manager.enabled=1

## Recalbox API (REST)
system.api.enabled=0

## EmulationStation menu style 
## default -> default all options menu
## none -> no menu except the game search menu
## bartop -> less menu, only needed for bartops
system.es.menu=default

## Emulator special keys
## default -> default all special keys
## nomenu -> cannot popup the emulator menu
## none -> no special keys in emulators
system.emulators.specialkeys=default

## Show or hide kodi in emulationstation (0,1)
kodi.enabled=1
## Start kodi at launch (0,1)
kodi.atstartup=0
## set x button shortcut (0,1)
kodi.xbutton=1

## Kodi can wait for a network component before starting
## waithost is the ip or hostname that must answer to a ping to validate the availability
## waittime is the maximum time waited when kodi boots
## if waitmode is required, kodi will not start if the component is not available
## if waitmode is wish, kodi will start if the component is not available
## if waitmode is not set or has another value, kodi will start immediately
;kodi.network.waitmode=required
;kodi.network.waittime=10
;kodi.network.waithost=192.168.0.50

# ------------ B - Network ------------ #
## Set system hostname
system.hostname=RECALBOX
## Activate wifi (0,1)
wifi.enabled=0
## Wifi SSID (string)
;wifi.ssid=new ssid
## Wifi KEY (string)
## Escape your special chars (# ; $) with a backslash : $ => \$
;wifi.key=new key
## Samba share
system.samba.enabled=1
### Virtual Gamepads
system.virtual-gamepads.enabled=1
### SSH
system.ssh.enabled=1

# ------------ C - Audio ------------ #
## Set the audio device (auto, hdmi, jack)
audio.device=auto
## Set system volume (0..100)
audio.volume=90
## Enable or disable system sounds in ES (0,1)
audio.bgmusic=1



# -------------- D - Controllers ----------------- #
# Enable support for standard bluetooth controllers
controllers.bluetooth.enabled=1


## Please enable only one of these
# -------------- D1 - PS3 Controllers ------------ #
##Enable PS3 controllers support
controllers.ps3.enabled=1
## Choose an driver between official, shanwan and gasia if you have dualshock clones (official,shanwan,gasia)
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

## XGaming's XArcade Tankstik and other compatible devices
controllers.xarcade.enabled=1



# ------------ F - Language and keyboard ------------ #
## Set the language of the system (fr_FR,en_US,en_GB,de_DE,pt_BR,es_ES,it_IT,eu_ES,tr_TR,zh_CN)
system.language=en_US
## set the keyboard layout (fr,en,de,us,es)
;system.kblayout=us
## Set you local time
## Select your timezone from : ls /usr/share/zoneinfo/ (string)
;system.timezone=Europe/Paris



# ------------ G - UPDATES ------------ #
## Automatically check for updates at start (0,1)
updates.enabled=1
# default : stable ; set to beta to get the next version currently being tested. set to unstable at your own risk to get the development version.
updates.type=stable


# ------------ H - HERE IT IS - GLOBAL EMULATOR CONFIGURATION ------------ #
## The global value will be used for all emulators, except if the value
## is redefined in the emulator

## Set game resolution for emulators
## select your mode from the command : tvservice -m [MODE]
## CEA 5 HDMI : 1920x1080 @ 60Hz 16:9, clock:74MHz interlaced 
## CEA 4 HDMI : 1280x720 @ 60Hz 16:9, clock:74MHz progressive
## use 'default' for using the default resolution
## (string)
global.videomode=CEA 4 HDMI

## Shader set 
## Automatically select shaders for all systems
## (none, retro, scanlines)
global.shaderset=none

## Once enabled, your screen will be cropped, and you will have a pixel perfect image (0,1)
global.integerscale=0

## Set gpslp shader for all emulators (prefer shadersets above). Absolute path (string)
global.shaders=

## Set ratio for all emulators (auto,4/3,16/9,16/10,custom)
global.ratio=auto

## Set smooth for all emulators (0,1)
global.smooth=1

## Set rewind for all emulators (0,1)
global.rewind=1

## Set autosave/load savestate for all emulators (0,1)
global.autosave=0

## Enable retroarchievements (0,1)
## Set your www.retroachievements.org username/password
## Escape your special chars (# ; $) with a backslash : $ => \$
global.retroachievements=0
global.retroachievements.username=
global.retroachievements.password=

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
;snes.autosave=0
;snes.emulator=libretro
;snes.integerscale=0
## If you do not want recalboxOS to generate the configuration for the emulator : 
;snes.configfile=/path/to/my/configfile.cfg

## Default cores for RPi2
snes.core=snes9x_next
gba.core=mgba
mame.core=mame078
nes.core=fceunext

## NeoGeo emulator 
## You can use pifba or a libretro core (fba2x,libretro)
neogeo.emulator=libretro
## If you set libretro as neogeo.emulator, the line below sets the retroarch core (fba,imame4all)
neogeo.core=fba

## N64 emulator is configured to display a screen with a 640x480 resolution (native n64 resolution)
## So you must use one of these video modes (DMT 4 HDMI,CEA 1 HDMI).
## If your screen is not compatible with one of these video modes, please check the recalbox's wiki.
n64.videomode=DMT 4 HDMI
## If you are using a CRT screen, please change the setting above with this one : 
# n64.videomode=default

## Configurations generated by Recalbox

```
