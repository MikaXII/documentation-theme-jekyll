---
layout: page
title: N64 : no sound jack output (EN)
wikiPageName: N64-:-no-sound-jack-output-(EN)
menu: wiki
---

If you are using the raspberry's jack output, and you don't have sound, follow these instructions.   

Connect to recalbox [with a root access](https://github.com/digitalLumberjack/recalbox-os/wiki/Root-access-on-terminal-%28EN%29).   
Edit your mupen64plus configuration file using this command :    

`nano /recalbox/configs/mupen64/mupen64plus.cfg`

Then change this line   

```
# Audio output to go to (0) Analogue jack, (1) HDMI
 OUTPUT_PORT = 1
```

With

```
# Audio output to go to (0) Analogue jack, (1) HDMI
 OUTPUT_PORT = 0
```

Now you need to do `ctrl+x` then `y` and `enter` to save the file, and reboot you recalbox.   
Sound should now be ok after reboot.

This modification can be also do using [WinSCP](https://github.com/digitalLumberjack/recalbox-os/wiki/Network-access-with-WinSCP-%28EN%29) software if you are phobic about using terminal.
