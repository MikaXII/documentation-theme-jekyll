---
layout: page
title: Scrape your games with your PC (EN)
wikiPageName: Scrape-your-games-with-your-PC-(EN)
menu: wiki
---

**Outdated wiki, needs overhaul!**  
Take a look at [[BATCH] Scrape your roms on your PC](https://forum.recalbox.com/topic/2594/batch-scrape-your-roms-on-your-pc-fastscraper/)

First, thanks to [NeB](http://blog.recalbox.com/forums/users/neb/) for this how-to!   
You'll find his french version on the [forum](http://blog.recalbox.com/forums/topic/tuto-scraper-ses-jeux-depuis-son-pc-plus-efficacement/).   
<br><br>
You can scrape your games using your computer. This method check the hashes signature of your roms and not their names. So it is really more efficient and faster.

What do you need : 
- a computer
- the binairies precompiled for your OS : https://github.com/sselph/scraper/releases

This how-to was written for PC and MAC. But you can easily adapt it for linux.

**First step (the same step for PC an MAC):**

If you want to scrape your snes roms, create a folder called `snes` in your computer and add it to your roms (format .smc or zip). Add it the file `scraper.exe` for PC or `scraper`for MAC (UNIX) downloaded previously.
Now you are ready to scrape your snes roms.

**Second step :**

For PC:

Do shift+right click in your snes folder and choose “open a command window here” (I used a Windows in french, so the text is maybe not exactly the same).   
Once in cmd.exe type :   

`scraper.exe -image_path="~/.emulationstation/downloaded_images/SYSTEM_NAME" -no_thumb=true -max_width=375`   
<br>
(replaced “SYSTEM_NAME” by the system's name than you are scrapping, snes, nes, mastersystem, etc...)   
Now press enter, and wait...
<br>
<br>
<br>
If you want to scrape arcade roms (**MAME** or **FBA** including **NEOGEO**) use this command :

`scraper.exe -mame -mame_img "m,t,s" -image_path="~/.emulationstation/downloaded_images/mame_or_fba_o_neogeo" -no_thumb=true -max_width=375` 
<br>  
(as previously, replaced “mame_or_fba_or_neogeo” by mame or fab or neogeo)

For MAC, 2 solutions:
- Open a terminal window (Applications/Utilities) and drag/drop the folder snes you created previously in the terminal.

or

- Enable the option « new terminal to the folder » (I used a Macintosh in french, so the text is maybe not exactly the same). You find this option in the Keyboard preferences in " Keyboard shortcuts " and in the left column, stand on "Services" , scroll down to find the line " new terminal to the folder. » Check the box above this line. Now, right click in your snes folder and choose « new terminal to the folder ».

Once in the terminal window type : 
`./scraper -image_path="~/.emulationstation/downloaded_images/SYSTEM_NAME" -no_thumb=true -max_width=375` 
<br>
(replaced “SYSTEM_NAME” by the system's name than you are scrapping, snes, nes, mastersystem, etc...)   
Now press enter, and wait...
<br>
<br>
<br>
If you want to scrape arcade roms (**MAME** or **FBA** including **NEOGEO**) use this command :

`scraper -mame -mame_img "m,t,s" -image_path="~/.emulationstation/downloaded_images/mame_or_fba_or_neogeo" -no_thumb=true -max_width=375` 
<br>  
(as previously, replaced “mame_or_fba_or_neogeo” by mame or fba or neogeo)

**Third step (the same step for PC an MAC):**

Well, now you have your roms set... you have the scrape files corresponding... So you have to copy them in your recalbox.
But before starting to add files, you need to close emulationstation.
So poweron your recalbox, and press alt + F4 if you have a keyboard connected to your recalbox. Or go in [root acces](https://github.com/digitalLumberjack/recalbox-os/wiki/Root-access-on-terminal-%28EN%29) and shutdown the emulationstation service, with the command ``` /etc/init.d/S31emulationstation stop ```.<br><br>
 Now, to copy your files, go in the folder `system` shared on your network create a folder called `backup_scrape` and paste the folders `downloaded_images` and `gamelists`.<br><br>
Now you can follow instructions of this [mini-how-to - section "restore "](https://github.com/digitalLumberjack/recalbox-os/wiki/Backup-your-scrape-%28EN%29). <br><br>
Once Finished, do not forget to restart emulationstation by executing the following command ``` /etc/init.d/S31emulationstation start ```.
