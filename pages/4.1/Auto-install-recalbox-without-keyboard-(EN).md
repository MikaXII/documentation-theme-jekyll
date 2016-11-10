---
layout: page
title: Auto install recalbox without keyboard (EN)
wikiPageName: Auto-install-recalbox-without-keyboard-(EN)
menu: wiki
---

You can automatically install recalboxOS on your raspberryPi without having to use an usb keyboard.

Follow these steps:

1. Download and unzip the last release of recalboxOS

2. Delete the folder in `os` that does not correspond to your RPi. If you are on RPi1 remove `recalboxOS-rpi2`, if you are on RPi2 remove `recalboxOS-rpi` 

3. Edit the `recovery.cmdline` file and append `silentinstall` to the arguments list :  
`runinstaller quiet vt.cur_default=1 elevator=deadline`  
becomes  
`runinstaller quiet vt.cur_default=1 elevator=deadline silentinstall`

When you now boot your Pi using an SD card containing the modified version of recalbox that you just created, it will automatically install recalboxOS boot into it after the installation has finished.
