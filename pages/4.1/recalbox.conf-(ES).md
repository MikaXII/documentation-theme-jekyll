---
layout: page
title: recalbox.conf (ES)
wikiPageName: recalbox.conf-(ES)
menu: wiki
---

## Introducción

Recalbox tiene una herramienta de configuración avanzada llamada `recalbox.conf` y que permite modificar algunas opciones no disponibles en emulationstation.

Puedes editar este archivo :
- Usando las carpetas compartidas de tu recalbox. El archivo destá disponible en el directorio **`system`**
- También puedes [[conectar como root|Root-access-on-terminal-(EN)]] y editar el archivo que se encuentra en `/recalbox/share/system/recalbox.conf`

**Para usuarios de Windows** : Debes usar un editor de texto decente, por ejemplo **Notepad++**. El editor de texto por defecto en windows (Bloc de notas) no mantiene los caracteres de final de linea.

El **;** al principio de una linea indica que está desactivada. Borra el **;** para activarla.

Este archivo no se sobrescribe cuando actualizas la recalbox pero sí `/recalbox/share/system/recalbox.conf.template`. Aquí podrás encontrar todas las nuevas opciones de la actualización. Asegúrate de actualizar tu `recalbox.conf` después de actualizar.

## I - Opciones disponibles

- **A - System Options** (opciones de sistema)
 - activar o desactivar el arranque de recalbox-manager
 - cambiar la pantalla de arranque (para arranques largos cuando /share está en un NAS)
 - cambiar el tema del menú emulationstation
 - ocultar Kodi en emulationstation
 - arrancar Kodi durante el arranque
 - deshabilitar el arranque de Kodi con el botón X
- **B - Network** (red)
 - establecer el nombre del equipo
 - establecer el SSID y la clave WiFi
- **C - Audio** (audio)
 - establecer la salida de audio
 - establecer el volumen del sistema
 - activar o desactivar la música de fondo en emulationstation
- **D - Controllers** (mandos)
 - activar mandos bluetooth
 - seleccionar el controlador PS3
 - activar o desactivar xboxdrv
 - establecer los mandos xboxdrv
 - activar o desactivar mandos GPIO
 - activar o desactivar mandos marqs DB9
 - activar o desactivar mandos marqs gamecon
- **F - Language and keyboard** (idioma y teclado)
 - establecer el idioma
 - establecer la configuración del teclado
 - establecer la zona horaria
- **G - UPDATES** (actualizaciones)
 - activar o desactivar la búsqueda de actualizaciones
- **H - EMULATOR CONFIGURATION - detalles a continuación** (configuración de los emuladores)

### A - Configuración de los emuladores
#### 1 - Configuración global
Puedes ajustar los emuladores recalbox.conf. Las variables globales establecen preferencias para todos los emuladores.

**Variables disponibles :**
* **videomode** : establece el modo de vídeo (utiliza tvservice para obtener los valores disponibles). Utiliza _default_ para desactivar el cambio de modo (para monitores CRT)   
ejemplo : `global.videomode=CEA 4 HDMI`
* **shaderset** : establece el juego de filtros para todos los emuladores (ninguno, retro, scanlines) Más detalles en [[shaders configuration|Shaders-configuration-(EN)]]
ejemplo : `global.shaderset=retro`
* **shaders** : establece la ruta absoluta al filtro o juego de filtros (glsl o glslp)  
ejemplo : `global.shaders=/recalbox/share/shaders/shaders_glsl/scanline.glsl`
* **ratio** : establece el aspecto de los juegos (_16/9_, _4/3_, _16/10_, _auto_ o _custom_)  
ejemplo : `global.ratio=16/9`
* **smooth** : activa o desactiva el suavizado de los juegos (blur)
ejemplo : `global.smooth=0`
* **rewind** : activa o desactiva el rebobinado en los juegos (puede ralentizar la emulación)  
ejemplo : `global.rewind=0`
* **inputdriver** : fuerza el controlador de entrada en retroarch (auto, sdl2, udev)  
ejemplo : `global.inputdriver=auto`

Configuración por defecto : 
```
global.videomode=CEA 4 HDMI
global.shaders=
global.ratio=auto
global.smooth=1
global.rewind=0
global.inputdriver=auto
```
Si quieres activar el suavizado para todos los emuladores utiliza `global.smooth=1`.  
Si quieres activar el filtro scanlines para todos los emuladores utiliza `global.shaders=/recalbox/share/shaders/shaders_glsl/scanline.glsl`.

#### 2 - Configuración específica por emulador
Cada emulador puede ser configurado aquí. Simplemente usa el nombre del sistema y establece las variables.

**Sistemas disponibles :**

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

**Núcleos libretro disponibles :**  

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
* **videomode** : establece el modo de vídeo (utiliza tvservice para obtener los valores disponibles).
ejemplo : `snes.videomode=CEA 4 HDMI`
* **shaders** : establece la ruta absoluta al filtro o juego de filtros (glsl o glslp)  
ejemplo : `snes.shaders=/recalbox/share/shaders/shaders_glsl/snes.glsl`
* **ratio** : establece el aspecto de los juegos (_16/9_, _4/3_, _auto_ o _custom_)  
ejemplo : `snes.ratio=4/3`
* **smooth** : activa o desactiva el suavizado de los juegos (blur)
ejemplo : `snes.smooth=0`
* **rewind** : activa o desactiva el rebobinado en los juegos (puede ralentizar la emulación)  
ejemplo : `snes.rewind=1`
* **core** : selecciona el núcleo de emulación (los libretrocores están en /usr/lib/libretro)
ejemplo : `snes.core=snes9x_next`
* **emulator** : selecciona el emulador a utilizar (los emuladores son retorarch, fba2x y mupen64)
ejemplo : `neogeo.emulator=fba2x`
* **configfile** : fuerza la carga de tu configuración. La recalbox no automatizará la configuración del emulador
ejemplo : `snes.configfile=/path/to/my/configfile.cfg`


## II - recalbox.conf por defecto

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
