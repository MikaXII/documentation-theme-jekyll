---
layout: page
title: Connect your recalbox to a CRT with composite (EN)
wikiPageName: Connect-your-recalbox-to-a-CRT-with-composite-(EN)
menu: wiki
---

If you want to connect your recalbox on a CRT, you will need a mini-jack to RCA like this one :
![](https://cms-assets.tutsplus.com/uploads/users/31/posts/21821/image/4poleAV2.png)

Be aware that on camcorders cables Video output might be on Right Audio plug (red).

Make rw partition    
   
`mount -o remount,rw /boot`    
    

Then edit the [[/boot/config.txt|Edit-the-config.txt-file-(EN)]] file and **comment all lines begining with `hdmi_`**, and add one of the sdtv_mode supported : 
```
sdtv_mode=0    Normal NTSC   
sdtv_mode=1    Japanese version of NTSC – no pedestal  
sdtv_mode=2    Normal PAL   
sdtv_mode=3    Brazilian version of PAL – 525/60 rather than 625/50, different subcarrier
``` 

and finally add ``` hdmi_ignore_hotplug=1``` to force composite

If you are on Recalbox OS 4.0 or higher the filesystem is read only. You will need to use Noobs to edit the configuration file.  Plug an usb keyboard and press Shift (Maj en français) on bootup to access recovery menu. Then press "e" to get the edition menu, and make your changes here. You can switch the language and keyboard mapping by pressing "l" and "k".
https://github.com/recalbox/recalbox-os/wiki/Edit-the-config.txt-file-%28EN%29

Your [[config.txt|Edit-the-config.txt-file-(EN)]] should looks like : 
```
sdtv_mode=2
hdmi_ignore_hotplug=1
```

Then edit [[recalbox.conf|recalbox.conf-(EN)]] and set the _global.videomode_ to default :  
```
global.videomode=default
```

The last but not the least, disable the smooth filter and all shaders on games from the ES menu (START -> GAME MENU) to get the original image from all systems ! 

Enjoy !
