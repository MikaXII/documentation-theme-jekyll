---
layout: page
title: Play with two GameBoy (EN)
wikiPageName: Play-with-two-GameBoy-(EN)
menu: wiki
---

It is possible to play two players games on GameBoy by emulating two GameBoy with Recalbox.  

Edit the [[recalbox.conf|recalbox.conf-(EN)]] file to replace the GameBoy emulator by `tgbdual`
```
# ------------ I - EMULATORS CHOICES ----------- #
## You can override the global configuration here
## For GameBoy
gb.core=tgbdual
gb.ratio=custom
## For GameBoyColor
gbc.core=tgbdual
gbc.ratio=custom
```
Save, then restart your Recabox.

Launch a GameBoy game, like Ballon Kid for instance. Open the Retroarch menu with the Hotkey button and the B button. Cahnge the following parameters:
```
Setting / Configuration / Save Configuration On Exit : ON
Quick menu / Core Options / GB Link Enable (restart) : enabled
Quick menu / Core Options / Screen placement (restart) : horizontal
Quick menu / Core Options / Switch player screens : normal ; player 1 to the left player two to the right
Quick menu / Core Options / Show player screens : both players
Settings / Video / Aspect Ratio Index : 20:9 (1:1 PAR) ; 100% conforme GB ratio 
Quick menu / Restart Content
```
You can set back Save Configuration On Exit to OFF when you relaunch the game.

Think that if your TV is not set to 16/9 - if the Recalbox menu doesn't fit all the screen- then the ratio will be wrong.
Note also that  the one-player games will be split too. Two GB side by side, good for a speed run battle, useless otherwise.
To avoid too much manipulation, you can apply these settings only GB or GBC.
