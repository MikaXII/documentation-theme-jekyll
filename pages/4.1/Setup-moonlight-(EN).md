---
layout: page
title: Setup moonlight (EN)
wikiPageName: Setup-moonlight-(EN)
menu: wiki
---

#**1. Intro**
Moonlight is an open source version of NVidia's Gamestream technology. If your PC meets the requirements, you can stream most of your games to your Recalbox. On the other side, Recalbox reads the pads configuration from EmulationStation and converts it to Moonlight.

## Moonlight features on Recalbox :
- stream games on your local network or through Internet
- up to 4 players supported
- up to 1080p/60fps
- hardware accelereated H264 decoding on any version of the Raspberry Pi
- supports keyboard and mouse
- up to GFE 2.11

## Requirements
Recalbox and PC requirements to enjoy Moonlight :
- A Controller configured in ES
- Steam Account (optional) or standalone suported games (see https://shield.nvidia.com/game-stream)
- A Nvidia supported GPU (see http://www.geforce.com/geforce-experience/system-requirements)
- An Ethernet connection is strongly recommended, WiFi is not enough reliable

**If you are upgrading from 3.3.0 to 4.0.0, _please read carefully_**

#**2. Moonlight Configuration**
Please check first your recalbox version
## a. Version >= 4.0.0 beta1
Recalbox 4.0.0 introduces new features for Moonlight :
* gamepads auto configuration for moonlight
* easy configuration : you may not need to specify a computer IP
* moonlight parameters can be customised in the `/recalbox/share/sysem/configs/moonlight/moonlight.conf`. Or through the network : \\Recalbox\User Data\system\configs\moonlight\moonlight.conf

**Please note** : 
* Recalbox 4.0.0-beta2 support of moonlight is really much improved compared to 4.0.0-beta1. Make sure your upgraded
* the "configuration-less" setup works reliably only if you have juste 1 PC compatible with gamestream. Otherwise, you'll have to specify the IP address of your gamestream Host in the configuration file
* It can happen IPv6 is used instead of IPv4. Turn off IPv6 on windows
* Always use the latest recalbox version. 4.0.0-beta4 brought GFE 2.11 support
* If you're stuck on pairing : delete /recalbox/share/system/configs/moonlight/keydir, unpair all devices in GFE, log in to you NVidia account, and try pairing again

**Pad configuration** : if your pad doens't respond like expected in moonlight, please remap it in EmulationStation and try again

Now you're ready to setup your Recalbox for gamestreaming :

1. Quit EmulationStation (through SSH or pressing F4)
2. login as root
3. `cd /recalbox/scripts/moonlight`
4. Make sure only your gamestream-capable PC is available on the network
5. run `./Moonlight.sh pair`, and enter the given digit on your computer
6. Once paired, run `./Moonlight.sh init` to create rom links for Emulation Station + scraping data
7. restart EmulationStation and enjoy Moonlight !

```
Using username "root".
# /etc/init.d/S31emulationstation stop
# cd /recalbox/scripts/moonlight
# ./Moonlight.sh pair
Moonlight Embedded 2.2.0 (EMBEDDED;CEC;PI)
Too many options: No such file or directory
Moonlight Embedded 2.2.0 (EMBEDDED;CEC;PI)
Searching for server...
Connect to 192.168.0.28...
Generating certificate...done
NVIDIA GeForce GTX 960M, GFE 2.11.4.0 (protocol version 7)
Please enter the following PIN on the target PC: 3660
1017 / 1017
Succesfully paired
# ./Moonlight.sh init
Fetching games from  ...
Scraping games ...
# /etc/init.d/S31emulationstation start

```


Optional step if you have other compatible moonlight PCs :
* Edit `/recalbox/share/sysem/configs/moonlight/moonlight.conf`
* remove the # in front of `#address =`
* Add your IP. Ex : `address = 192.168.0.12`
* Save your file

Recalbox can only handle 1 gamestream PC for now. Support for several host PCs may arrive in a later release

## b. Version >= 3.3.0 beta15
1. Quit EmulationStation (through SSH or pressing F4) /etc/init.d/S31emulstation stop
2. login as root
3. make sure /recalbox/share/roms/moonlight exists. Otherwise, `mkdir -p /recalbox/share/roms/moonlight`
4. `cd /recalbox/scripts/moonlight`
5. edit Moonlight.sh and set "moonlight_ip=" to the IP you want to stream from. For example, if your PC IP is "192.168.1.1", edit like "moonlight_ip=192.168.1.1", save and quit your text editor
or in SSH , `nano /recalbox/scripts/moonlight/Moonlight.sh`
6. run `./Moonlight.sh pair`, and enter the given digit on your computer
7. Once paired, run `./Moonlight.sh init` to create rom links for Emulation Station + scraping data
8. run `./Moonlight.sh map` to configure your controller (single player pad only supported for now, keyboard + mouse work flawlessly)
9. restart EmulationStation (/etc/init.d/S31emulstation restart) and enjoy Moonlight !

## c. 3.3.0 beta7 <= Version < 3.3.0 beta15 **

Go to //recalbox/roms/moonlight or by ssh in /recalbox/share/roms/moonlight in this folder you have :    
- Moonlight.sh.hide
- Moonlight.conf    
## d. Version < 3.3.0 beta7 :

Get the Moonlight.sh.hide here =>

rename **Moonlight.sh.hide** on **Moonlight.sh** open with notepad ++ or other the Moonlight.sh and replace by this [Moonlight.sh.hide_v2](https://github.com/steak3/recalbox-buildroot/blob/unified/board/recalbox/share/roms/moonlight/Moonlight.sh.hide_v2)

replace to **moonlight_ip=YOUR_IP_HERE** by **moonlight_ip=192.168.x.x** <== it's your PC IP adress

Save and Exit

remove **Moonlight.conf** possible problem here

in SSH on /recalbox/share/roms/moonlight launch command :

- ./Moonlight.sh pair    
if this command sucessfull you have this message :

   **Too many options: No such file or directory    
   Can't open configuration file: hosts/192.168.x.x.conf     
   Generating certificate...done    
   Please enter the following PIN on the target PC: 9958    
   Succesfully paired**      

on your PC you have a Nvidia popup for enter your Pin

Now controller Configuration, launch this command:

- ./Moonlight.sh map
and follow screen information.

reboot your recalbox and play with moonlight.

#**3. ANNEXE**
# v4.0.0 specific
Advanced users only : You can stream from a remote computer on internet. You'll need to edit `/recalbox/scripts/moonlight/Moonlight.sh` to specify the remote host IP, set the same IP in the moonlight.conf, and configure port forwarding according to https://github.com/moonlight-stream/moonlight-android/wiki/Setup-Guide#streaming-over-the-internet

## v3.3.0 specific
you can modify the display configuration on Moonlight

720p in 30fps
1080p in 30fps

720p in 60fps
1080p in 60fps

you must change the Ligne 23 in Moonlight.sh :

cmd="moonlight stream -remote **-1080 -60fps** -keydir ${moonlight_keydir} -mapping ${moonlight_mapping} ${moonlight_ip}" ;;
replace **Bold** parameters according to your need
