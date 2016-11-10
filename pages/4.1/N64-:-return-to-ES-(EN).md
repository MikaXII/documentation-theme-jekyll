---
layout: page
title: N64 : return to ES (EN)
wikiPageName: N64-:-return-to-ES-(EN)
menu: wiki
---

Mupen64plus is not auto-configured by recalbox as the other emulators. So you need to do it manually.  

The N64 video mode is set in your [recalbox.conf file](https://github.com/recalbox/recalbox-os/wiki/recalbox.conf-%28EN%29).   
By default, we are using the video mode : `n64.videomode=DMT 9 HDMI`   

This mode display a resolution of **800x600**.   
We defined this resolution by default, because RPI2 can't emulate N64 at a higher resolution with a good framerate.   
So **800x600** is the **resolution max** to use on recalbox.   

But, every screens don't have the same video mode compatibility.   
So, when you try to start a N64 game, you may have a black screen with a return to Emulationstation.   
In this case, you must determine which video modes are compatible with your own screen.   
<br>
<br>
Get [a root access](https://github.com/recalbox/recalbox-os/wiki/Root-access-on-terminal-%28EN%29), then type these 2 commands :   

`tvservice -m DMT`  

and  

`tvservice -m CEA`  

<br>
Commands will return something like that :   
```
[root@RECALBOX ~]# tvservice -m DMT
Group DMT has 16 modes:
           mode 4: 640x480 @ 60Hz 4:3, clock:25MHz progressive 
           mode 5: 640x480 @ 72Hz 4:3, clock:31MHz progressive 
           mode 6: 640x480 @ 75Hz 4:3, clock:31MHz progressive 
           mode 8: 800x600 @ 56Hz 4:3, clock:36MHz progressive 
           mode 9: 800x600 @ 60Hz 4:3, clock:40MHz progressive 
           mode 10: 800x600 @ 72Hz 4:3, clock:50MHz progressive 
           mode 11: 800x600 @ 75Hz 4:3, clock:49MHz progressive 
           mode 16: 1024x768 @ 60Hz 4:3, clock:65MHz progressive 
           mode 17: 1024x768 @ 70Hz 4:3, clock:75MHz progressive 
           mode 18: 1024x768 @ 75Hz 4:3, clock:78MHz progressive 
           mode 21: 1152x864 @ 75Hz 4:3, clock:108MHz progressive 
           mode 32: 1280x960 @ 60Hz 4:3, clock:108MHz progressive 
           mode 35: 1280x1024 @ 60Hz 5:4, clock:108MHz progressive 
           mode 36: 1280x1024 @ 75Hz 5:4, clock:135MHz progressive 
  (prefer) mode 57: 1680x1050 @ 60Hz 16:10, clock:119MHz progressive 
           mode 58: 1680x1050 @ 60Hz 16:10, clock:146MHz progressive 
```
and  
```
[root@RECALBOX ~]# tvservice -m CEA
Group CEA has 5 modes:
           mode 1: 640x480 @ 60Hz 4:3, clock:25MHz progressive 
           mode 2: 720x480 @ 60Hz 4:3, clock:27MHz progressive 
           mode 3: 720x480 @ 60Hz 16:9, clock:27MHz progressive 
  (native) mode 4: 1280x720 @ 60Hz 16:9, clock:74MHz progressive 
           mode 16: 1920x1080 @ 60Hz 16:9, clock:148MHz progressive 
```

Ok now we have all video modes which can be used on this monitor.   
We have to find a video mode, with a resolution **equal or below** to 800x600, then define this mode  in the [recalbox.conf file](https://github.com/recalbox/recalbox-os/wiki/recalbox.conf-%28EN%29).   

If I choose this video mode :   
```
Group CEA has 5 modes:
           mode 1: 640x480 @ 60Hz 4:3, clock:25MHz progressive
```

I'll edit my [recalbox.conf file](https://github.com/recalbox/recalbox-os/wiki/recalbox.conf-%28EN%29) like this :   
- video mode by default : `n64.videomode=DMT 9 HDMI`   
- new video mode : `n64.videomode=CEA 1 HDMI`  

###Particular case : CRT screen  
If you are using a **CRT** screen, you must edit your video mode like this :   
`n64.videomode=default`  
