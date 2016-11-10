---
layout: page
title: recalbox.conf 3.2.x (EN)
wikiPageName: recalbox.conf-3.2.x-(EN)
menu: wiki
---

The recalbox share on the network a directory named `system` that contains a file named `recalbox.conf`

The file is located on the system at /recalbox/share/system/recalbox.conf

This file allows you to modify some options not available in emulationstation. 

What is available : 
- hide kodi in emulationstation
- start kodi on system startup
- avoid x button to start kodi
- enable GPIO joystick drivers as mk_arcade, marqs DB9 and gamecon.
- set wifi ssid and key
- set audio output
- set language (override es settings)
- set keyboard layout
- set time zone
- enable xboxdrv replacing the kernel driver
- disable update checking
- change ingame resolution

Just remove the ; on the options you want to enable, and change the value corresponding to what you need.

Here is the default file : 

```
# WARNING - THOSES VARIABLE OVERRIDE EMULATIONSTATION SETTINGS. 

# System Variable
# You can configure your recalbox from here
# To set a variable, remove the first ; on the line


# ------------ A - Kodi ----------- #
## Show or hide kodi in emulationstation
;enable_kodi=1
## Start kodi at launch
;kodi_at_start=0
## set x button shortcut (enabled by default)
;kodi_by_xbutton=1



# ------------ B - Wifi ------------ #
## Set direclty your wifi key and ssid here
;wifi_ssid=new ssid
;wifi_key=new key



# ------------ C - Audio ------------ #
## Set the audio output 
## select between auto, hdmi, jack
;audio_output=jack



# ------------ D - XBOX Controllers ------------ #
## Xbox controllers are already supported, but xboxdrv can solve some compatibility issues 
## Disable this if you use ps3 controllers
;enable_xbox_drv=0
## set the amount of controllers to use with xboxdrv
;xboxdrv_nb_controls=2



# ------------ E - GPIO Controllers ------------ #
## If one of the enable_[controller] is set to 1, set the other to 0

## GPIO Controllers
## enable controllers on GPIO (mk_arcard_joystick_rpi)
;enable_mk_gpio=0
## mk_gpio arguments (map=1 for only one gpio controller)
;mk_gpio_args=map=1,2


## DB9 Controllers
## enable db9 drivers
;enable_db9=0
## db9 arguments
;db9_args=map=1

## gamecon controllers
## enable gamecon controllers, 
;enable_gamecon=0
## gamecon_args
;gamecon_args=map=1



# ------------ F - Language and keyboard ------------ #
## Set the language of the system : fr_FR, en_US, en_GB, de_DE, pt_BR, es_ES
;language=en_US
## set the keyboard layout : fr, en, de, us, es
;kb_layout=us
## Set you local time
## select your timezone from : ls /usr/share/zoneinfo/
;time_zone=Europe/Paris



# ------------ G - UPDATES ------------ #
## automatically check for updates at start
;enable_updates_check=1



# ------------ H - GAMES RESOLUTION ------------ #
## set game resolution for emulators
## select your mode from the command : tvservice -m CEA
## mode 5: 1920x1080 @ 60Hz 16:9, clock:74MHz interlaced 
## mode 4: 1280x720 @ 60Hz 16:9, clock:74MHz progressive
;game_hdmi_mode=5



# ------------ I - EMULATORS CHOICES ----------- #
## If two emulators are available for a platform you can switch here
## SNES : use pocketsnes (recommended for rpi1), catsfc or snes9x
;snes_emulator=pocketsnes

```


