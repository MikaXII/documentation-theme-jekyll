---
layout: page
title: How to switch multi disc PS1 games (EN)
wikiPageName: How-to-switch-multi-disc-PS1-games-(EN)
menu: wiki
---

Having a single file for yours multidisc games is possible.

/!\ Remind you must have your own psx discs images  /!\

You only have to create an eboot file containing yours iso, bin, img with the free software psx2psp

Check the es_system_cfg file

Via the terminal, go to ``nano /root/.emulationstation/es_systems.cfg``

Edit it, check if .pbp .PBP are present.

``<extension>.img .IMG .pbp .PBP .bin .BIN .cue .CUE .iso .ISO</extension>``

## eboot file creation

Find on Internet the psx2psp v1.42, download it and launch it.

Choose the classic mode then at the left part, load isos one by one. Click on the "Convert" button, wait.

Upload your folder or rename the eboot file made to your recalbox in the folder  ``/recalbox/share/roms/psx``

## CD swapping

To swap a CD during a game, you have to activate 2 or 3 options in the retroarch menu.

- open the retroarch menu ingame (Hotkey+B by default)

- go to "Settings/general settings" and change option "configuration save on exit" to on.
  Be careful, at this moment, all the changes made in the options will be saved when you quit retroarch.

- Quit retroarch and return to the game.

When you will be at a screen of a game asking you to swap CD, you only have to eject the CD virtually ( Hotkey + shortcut for the disk eject toggle option), change the CD and close the CD player virtually.
Your game will boot to the next CD.

Thread in the forum in case of problems :  [http://blog.recalbox.com/forums/topic/roms-playstation-et-nombre-de-jeux/](http://blog.recalbox.com/forums/topic/roms-playstation-et-nombre-de-jeux/)


## CD swap for PCSX-reARMed (r22)   
 
###  Method with .bin files   
    
* Enter the Retroarch menu (hotkey + B)    
* Choose Quick Menu, then core disk option   
* Eject the virtual cd by choosing disk cycle tray status   
* Look for the file you want (should be in recalbox/roms/psx) by choosing disk image append.   
