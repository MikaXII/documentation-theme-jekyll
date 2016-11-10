---
layout: page
title: Configure RetroAchievements (EN)
wikiPageName: Configure-RetroAchievements-(EN)
menu: wiki
---

### **Challenges/Achievements with RetroArch**

The website [retroachievements.org] (http://www.retroachievements.org) proposes challenges/achievements/trophies on platforms like NES, SNES, GB, GBC, GBA, Genesis/Megadrive, TurboGrafx16/PCEngine.
This challenge functionality has been added little by little to RetroArch.

### **Creating an account**
You must [register] (http://retroachievements.org/createaccount.php) on [retroachievements.org] (http://www.retroachivements.org).

Write down your nickname (Username) and password (Password) because they will be used to configure RetroAchivements in Retroarch.

### **Account Activation in EmulationStation under Recalbox 4.0.0**
 
`Options Jeux> Options de Retroachievements`

Connect your keyboard
Open the EmulationStation Menu (Start button)
Go to
`Game Options> Retroachievements Options`   

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/menu_es_retroachievements1.png)

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/menu_es_retroachievements2.png)   

`RetroAchievements > ON`   
`Username > introduce your username`    
`Password > your password`  

### **Account Activation (manually) under Recalbox 4.0.0** 

### **Edit the file recalbox.conf**

via ssh with PuTTY and the command nano

`nano /recalbox/share/system/recalbox.conf`  
or  
[WinSCP with the text editor Notepad++](https://github.com/recalbox/recalbox-os/wiki/Network-access-with-WinSCP-(EN))  

Add the following lines and replace username and password with the ones you choose during the registration.  

`## Enable retroarchievements (0,1)`   
`## Set your www.retroachievements.org username/password`   
`global.retroachievements=1`   
`global.retroachievements.username=username`   
`global.retroachievements.password=password`   

Save your recalbox.conf, reboot your Recalbox.  


### **Configuration of compatible emulators/cores with RetroAchievements.**

Not every libretro core is compatible with RetroAchievements.

Here is the list of emulators/cores operating with RetroArch/RetoAchievements 

Display the menu of Emulationstation (Start button)

Game options > Advanced >  
* NES > EMULATOR LIBRETRO > CORE QUICKNES  
* SNES > EMULATOR LIBRETRO > CORE SNES9X_NEXT  
* GB/GBC/GBA > DEFAULT 
* MEGADRIVE > DEFAULT (picodrive) 
* PCENGINE >DEFAULT (currently this is not supported by the libretro core)

Here is what it may look like on your RetroAchievements page, or you can find the challenges to achieve.

<a href="http://www.zimagez.com/zimage/retroachivement.php" target="_blank" title="Visionner l'image"><img src="http://www.zimagez.com/miniature/retroachivement.png" alt="Visionner l'image" /></a>

To view the challenges/trophies in RetroArch, simply activate the RetroArch menu (Hotkey + B)
Quick Menu> Achievements list

For a list of compatible games see [this page] (http://retroachievements.org/gameList.php) 
