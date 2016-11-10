---
layout: page
title: Configure recalbox for a Bartop or Arcade Cab (EN)
wikiPageName: Configure-recalbox-for-a-Bartop-or-Arcade-Cab-(EN)
menu: wiki
---

If you want to use a RPI with recalbox to create a **Bartop** or an **Arcade Cab**, you can easily configure recalbox to fit your needs.

### A - GPIO
You can configure the recalbox GPIO driver in the [[recalbox.conf|recalbox.conf-(EN)]]. That driver create two joysticks on the system directly controlled by Raspberry Pi GPIO (the pins).  
That way you will not need any third party usb controller, you just have to connect your controls on the GPIO.    
See [[GPIO controllers Mini How-to|GPIO-controllers-(EN)]]

### B - Video configuration
Many bartops are made with old LCD screens or CRT TVs.

- VGA Screen  
You will need a HDMI to VGA convertor (it's an active convertor). The ~10$ are OK. You might want to change the video mode to `default` for all your games in [[recalbox.conf|recalbox.conf-(EN)]] (`global.videomode=default`) if your are on a 4/3 screen.

- DVI Screen  
You will need a HDMI to DVI adaptor (it's a passive convertor). You will want to change the default hdmi drive in config.txt. See [[Connect your recalbox to a DVI screen|Connect-your-recalbox-to-a-DVI-screen-(EN)]]

- CRT Screen  
You will need a jack to RCA with video cable. You must change the video mode to `default` for all your games in [[recalbox.conf|recalbox.conf-(EN)]] (`global.videomode=default`). You must also change your config.txt according to [[Connect your recalbox to a CRT screen|Connect-your-recalbox-to-a-CRT-with-composite-(EN)]]


### C - Audio configuration
You can select the output audio peripheral in [[recalbox.conf|recalbox.conf-(EN)]]. Use `audio.device=jack` if you want to force the jack audio output or `audio.device=hdmi` to force hdmi audio.

### D - Menu Configuration
You might want to disable kodi in [[recalbox.conf|recalbox.conf-(EN)]] (`kodi.enabled=0`) in order to remove the kody shortcut on X button. That will also remove the Kodi entry in the menu.  
You might also want to change the menu settings, still in [[recalbox.conf|recalbox.conf-(EN)]] :
- For ES : 
 - By setting the `system.es.menu` to `bartop`, you will only have access to few options when you press Start to go to the EmulationStation menu.   
 - By setting the `system.es.menu` to `none`, only the game selection menu (SELECT) will be available.
- For emulators :
 - By setting the `system.emulators.specialkey` to `nomenu` you will disable the access to emulators menus
 - By setting the `system.emulators.specialkey` to `none` you will disable all specials keys in games except the exit combination.

