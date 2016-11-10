---
layout: page
title: keyboard encoder configuration (EN))
wikiPageName: keyboard-encoder-configuration-(EN))
menu: wiki
---

# Introduction
This tutorial is for Recalbox 4.0.0 Beta 2 or later

Xarcade2jstick has been patched to support keyboard encoders. You may have to reconfigure a few keys of your encoder as, sadly, x-gaming Xarcade devices didn't mapped as usual mame controllers

# Adding your own keyboard encoder
As for now, only the 1st generation of IPAC has been included. If you have a different keyboard encoder, follow these steps :
* login to your recalbox locally or through SSH
* find your encoder's device name with `ls /dev/input/by-id`. Usually, there is a trailing kbd in the event name. For example : _usb-Ultimarc_IPAC_2_Ultimarc_IPAC_2_9-if01-event-kbd_
* Now remount / as read-write `mount -o remount,rw /`
* Create an empty file that has the same name of your keyboard device found 2 steps above `touch /recalbox/share_init/system/configs/xarcade2jstick/devicename`. With the previous example : `touch /recalbox/share_init/system/configs/xarcade2jstick/usb-Ultimarc_IPAC_2_Ultimarc_IPAC_2_9-if01-event-kbd`
* Edit recalbox.conf and set `controllers.xarcade.enabled=1`
* Reboot by typing `reboot`

Recalbox is already configured for the devices

# Key mapping
## v4.0.0-beta4:
Key | Player 1 | Player 2
----|----------|---------
Up | KEY_UP or KP_8 | KEY_R
Down | KEY_DOWN or KP_2 | KEY_F
Left | KEY_LEFT or KP_4 | KEY_D
Right | KEY_RIGHT or KP_6 | KEY_G
A | KEY_Z | KEY_E
B | LEFT_SHIFT | KEY_W
X | LEFT_ALT | KEY_S
Y | LEFT_CTRL | KEY_A
START | KEY_1 | KEY_2
SELECT | KEY_5 | KEY_6
L1 | KEY_SPACE | KEY_Q
R1 | KEY_X | [ or KEY_K
HOTKEY | KEY_3 or KEY_V | KEY_4 or KEY_L

## v4.0.0-beta2:
Key | Player 1 | Player 2
----|----------|---------
Up | KEY_UP or KP_8 | KEY_R
Down | KEY_DOWN or KP_2 | KEY_F
Left | KEY_LEFT or KP_4 | KEY_D
Right | KEY_RIGHT or KP_6 | KEY_G
A | KEY_Z | KEY_E
B | LEFT_SHIFT | KEY_W
X | LEFT_ALT | KEY_S
Y | LEFT_CTRL | KEY_A
START | KEY_1 | KEY_2
SELECT | KEY_3 | KEY_4
L1 | KEY_SPACE | KEY_Q
R1 | KEY_X | [
HOTKEY | KEY_C | ]
