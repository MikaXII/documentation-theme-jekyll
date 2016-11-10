---
layout: page
title: Xin mo (EN)
wikiPageName: Xin-mo-(EN)
menu: wiki
---

USB Xin-Mo interfaces works natively on Recalbox.   
You can use the 2 players interface version **only since recalbox v3.3.0**.   

### Pinout ###
In this example, we are using a bartop with a 6 buttons panel + stick + 1 credit / insert coins (select) + 1 start button.   
This layout is the same for the 2 players :    

     ↑   Ⓨ Ⓧ Ⓛ  
    ← →	 Ⓑ Ⓐ Ⓡ    ($) (1P)
     ↓  

We recommend too, to add at this panel a dedicated hotkey button:   
Ⓗ

If you don't do that, you'll have problems with arcades games. Indeed you won't be able to insert coins with some arcade games.   

Ok so now than your panel is ok, one more thing to say.   
You ***must*** wire the 2 players to your Xin-Mo interface in the same way. Look this example :   

![XinMo pinout](https://github.com/digitalLumberjack/recalbox-os/wiki/images/XinMo_Arcade_Recalbox.jpg)

### Configuration ###

Ok so, panel is ok, wiring is ok, so now you have to map your controllers on recalbox using Emulationstation.   
You ***must only*** map the player 1 in input options of Emulationstation. Recalbox will automatically use this configuration with player 1 and player 2.   
That is why you must using the same wiring with the player 1 and player 2.   
Don't try to map the player 2, this will overwrite the player 1's configuration, and you'll obtain an incomplete configuration.
