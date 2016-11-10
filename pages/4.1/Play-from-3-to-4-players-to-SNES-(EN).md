---
layout: page
title: Play from 3 to 4 players to SNES (EN)
wikiPageName: Play-from-3-to-4-players-to-SNES-(EN)
menu: wiki
---

It is possible to play SNES up to 4 players with Recalbox.  
If you want to, you'll need one controler per player, configurated.

Edit the [[recalbox.conf|recalbox.conf-(EN)]] file to replace the SNES emulator by `snes9x_next`
```
# ------------ I - EMULATORS CHOICES ----------- #
## You can override the global configuration here
snes.core=snes9x_next
```

Save, then restart your Recabox.

Launch a SNES game, like Micro Machines for instance. Open the Retroarch menu with the Hotkey button and the B button. Cahnge the following parameters:
```
Setting / Configuration / Save Configuration On Exit : ON
Setting / Input / User 2 Device Type / Multitap
Quick menu / Restart Content
```
You can set back Save Configuration On Exit to OFF when you relaunch the game.

And voila. The game is working, and you're the king of the party !
