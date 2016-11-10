---
layout: page
title: How to use custom config for emulators (EN)
wikiPageName: How-to-use-custom-config-for-emulators-(EN)
menu: wiki
---

You have the possibility to create your custom configuration for each emulator on the recalbox.

### I - Retroarch
The retroarch configration can be created by hand, basing your configuration on the standard [retroarch.cfg](https://github.com/libretro/RetroArch/blob/master/retroarch.cfg) or edited in the retroarch gui menu. You will have to create a new configuration, and configure the new config file to be loaded for your emulator in [[recalbox.conf|recalbox.conf-(EN)]]

#### Using retroarch menu 

Let's say we want to create a special configuration file for the **neogeo** system.

**1)** Launch a game of the emulator you want to modify (neogeo here) 

**2)** Enter the retroarch menu (_hotkey_ + _b_)

**3)** modify every configuration you want

**4)** go back to the first retroarch menu, then do ***Save new config*** (the name of the configuration file will be something like _fba_libretro.cfg_, with the name of the core you are running)

**5)** [[Get a root access|Root-access-on-terminal-(EN)]] :  
modify the name of the config file for something more easier to recall  
`mv /recalbox/share/system/configs/retroarch/fba_libretro.cfg /recalbox/share/system/configs/retroarch/inputs/neogeo_custom.cfg`  

**6)** add the next line to [[recalbox.conf|recalbox.conf-(EN)]] :  
`neogeo.configfile=/recalbox/share/system/configs/retroarch/inputs/neogeo_custom.cfg`  

##### Inputs

[See this page.](Custom controller mapping for specific system)

### II - piFBA

