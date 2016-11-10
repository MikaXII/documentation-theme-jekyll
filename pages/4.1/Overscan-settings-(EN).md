---
layout: page
title: Overscan settings (EN)
wikiPageName: Overscan-settings-(EN)
menu: wiki
---

The _overscan_ option can be enabled if you have black border on the image or if your image is cropped. You can enable _overscan_ in the frontend by setting the **Overscan** option in **UI SETTINGS** to on.  
You need to reboot the rpi after changing this option. 

The overscan options are set by Noobs on first installation. If it does not correspond to your screen, you can change each border settings in your [[config.txt|Edit-the-config.txt-file-(EN)]] file : 
``` 
disable_overscan=0
overscan_left=24
overscan_right=24
overscan_top=24
overscan_bottom=24
``` 

The value specifies the number of pixels to skip on the edge of the screen. **Increase** this value if the image _flows off_ the edge of the screen; **decrease** it if there's a _black border_ between the edge of the screen and the image.
