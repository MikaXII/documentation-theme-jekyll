---
layout: page
title: Custom controller mapping for specific system (EN)
wikiPageName: Custom-controller-mapping-for-specific-system-(EN)
menu: wiki
---

There are two ways to customize the controller configuration for specific systems:

## Changing the assignment of RetroPad buttons to the system's controller buttons

This method may only work since Recalbox 4 (to be verified).

This method is the easiest one. It will allow you to re-use the buttons you already configured in EmulationStation but just change their assignment.

* Start by loading any game for the system.
* Open the libretro menu by using *Hotkey + B*.
* Go in *Quick Menu > Controls*.
* Here you can assign different buttons for the system's controls.
* When you have finished don't forget to select *Save Core Remap File* or your configuration will be lost when you quit this game. You can also choose to save a game-specific remap file if you want to.

## Changing the complete libretro controller configuration

If you want to configure the controller mapping for a libretro core, you can create a configuration file directly with retroarch and use the [[recalbox.conf|recalbox.conf-(EN)]] `[system].configfile=/path/to/my/configfile.cfg` option.

That means that the system will have its own configuration file, and the recalbox configgen feature will not work anymore for this system.

1) start a game in the system you want to configure,

2) open the menu (hotkey +b) and go in « Settings », and « Input user 1 binds »

3) reconfigure all buttons, keep a keyboard with you in case the controller doesn't respond during the configuration ("w" to validate and "x" to cancel)

4) go to "Input hotkey binds" and configure hotkeys combination

5) go back to the main retroarch menu and select « Save new config » (it will save the new configuration under the name [system]_libretro.cfg)

6) [[connect as root|Root-access-on-terminal-(EN)]], and modify the configuration file name to something you can remember, for example for neogeo :  
```
mv /recalbox/configs/retroarch/fba_libretro.cfg /recalbox/configs/retroarch/inputs/neogeocustom.cfg
```

7) modifiy recalbox.conf by adding the next line, that will override the default configuration for the system by the new one. This will override all configuration (shader, cheats, rewind, etc) :

`neogeo.configfile=/recalbox/configs/retroarch/inputs/neogeocustom.cfg`
