---
layout: page
title: Video configuration detailled (EN)
wikiPageName: Video-configuration-detailled-(EN)
menu: wiki
---

These are the best recommendations to configure the video to fit your screen the right way.  There are three levels of configuration : system, default emulator video mode, emulator specific video mode. Keep in mind that the screen resolution can have quite an impact on the frame rate, especially with CPU intensive emulators i.e. (N64, PSX & others)

Most of this guide will concentrate on the HDMI output, and outlining as often as possible the 3 cases of pure HDMI, HDMI2DVI, HDMI2VGA.

# What video modes are possible ?
First, understand the basics of screen resolution : a number of pixels in width by the number of pixels in height at (@) a given refresh rate in Hertz. For example : 1280x1024@60 which is a common screen resolution of 4x3 19" monitors. Nowadays TVs all display full HD at 1080p as an example, like 1920x1080@60. We won't go through interleave or progressive modes, that's off topic. Please refer to your screen manufacturers manual to know it's native resolution.

There are 2 groups of video modes : CEA and DMT. All those modes are listed [here](http://elinux.org/RPiconfig) or [here](https://www.raspberrypi.org/documentation/configuration/config-txt.md). Make sure to check the mode is compatible with your native screen resolution. A simple rule of thumb : CEA are TV modes, DMT are all other modes.

Most common modes are :
- DMT 4 : 640x480@60
- DMT 9 : 800x600@60
- DMT 16 : 1024x768@60
- DMT 35 : 1280x1024@60
- DMT 57 : 1680x1050@60
- 720p : CEA 4
- 1080p : CEA 16

In this tutorial we will cover 3 cases :
- A regular 1080p TV. Let's call it 1080pTV
- a VGA 720p monitor connected with a HDMI2VGA. Nickname : 720pVGA
- a good old 17" DVI capable of 1280x1024@60. Name it errr ... DVIboy. Don't forget to check the wiki for DVI screens 
https://github.com/recalbox/recalbox-os/wiki/Connect-your-recalbox-to-a-DVI-screen-%28EN%29

With what you already know about screen modes, these settings are most common :
- 1080pTV is CEA 16
- 720pVGA is CEA 4
- DVIboy is DMT 35

# Your system boots
Upon boot, the Pi will ask your monitor it's preferred screen resolution. Your monitor send its _EDID_ and the raspberry will select the screen resolution noted as "preferred". Here is where the very first problem occurs :
* most -if not all- native HDMI screens (TV, monitors) should send the right EDID
* HDMI2DVI should work almost as good
* HDMI2VGA adapters can be a bit tricky and provide an inaccurate EDID ...

Now that you know a bit more of what can happen, here are some examples :
- 1080pTV is a good boy and will have straight away its native 1080p
- 720pVGA has a crappy HDMI2VGA that answers "DMT 16" as preferred mode
- DVIboy sets its DMT 35 flawlessly.

As the screen detected on boot is the one displaying EmulationStation with its preferred resolution, 720pVGA will get an awful display. Hopefully this can be tweaked by editing the `/boot/config.txt`. Here are the lines you want to edit :
```ini
#hdmi_group=1
#hdmi_mode=1
```
**hdmi_group** : 1 for CEA, 2 for DMT

**hdmi_mode** : refer to the links above
so, for our 720pVGA, this is how we edit `/boot/config.txt` :
```ini
hdmi_group=1
hdmi_mode=4
```
Take NOTE :
- # gets removed, the technical term for this is "uncommented".  A line starting with a # is a comment, and not a command
- hdmi_group=1 means CEA
- hdmi_mode=4 means 720p

Now we're done, our 3 screens are set, continuing onward!

# Global video mode for emulators
Now EmulationStation runs in fullscreen, your hand is thrilling to test a game ...The main thing you need to know here, is that the screen resolution is changed before launching an emulator. But to what resolution ? Check your `recalbox.conf` and read the `global.videomode` parameter. It's default value is `CEA 4 HDMI`. That means that the screen resolution will be changed to 720p right before starting the emulator. Time to check some examples :
- 1080pTV can display 720p without a hitch
- 720pVGA can display 720p without a scratch
- DVIboy is ... MIA ... it can't display 720p. So just edit `recalbox.conf` and set global.videomode to its native video mode : `global.videomode=DMT 35 HDMI`

**Pro tip** : Feeling lucky, do you want to spare your monitor from one screen resolution change? Then set `global.videmode=default`, recalbox won't change the screen resolution before launching an emulator. But beware : it can have a massive impact on performance. Stretching a picture from the native emulator resolution to 1080p can be quite CPU intensive and slow down emulation. I don't recommend setting to default if your monitor can display higher than CEA 4

# Per emulator video mode
Last but not least, the video mode can be set especially for whichever emulator you want. For example, if you read through `recalbox.conf`, you will notice `n64.videomode=DMT 9 HDMI` which means we override the global.videomode for N46 emulation.

I hope this guide helped you to understand how screen resolution is managed on the Pi and Recalbox. Feel free to ask your questions on the forum or IRC

# Useful tips
## tvservice
tvservice is a great shell tool to diagnose your output
```
# tvservice --help
Usage: tvservice [OPTION]...
  -p, --preferred                   Power on HDMI with preferred settings
  -e, --explicit="GROUP MODE DRIVE" Power on HDMI with explicit GROUP (CEA, DMT, CEA_3D_SBS, CEA_3D_TB, CEA_3D_FP, CEA_3D_FS)
                                      MODE (see --modes) and DRIVE (HDMI, DVI)
  -t, --ntsc                        Use NTSC frequency for HDMI mode (e.g. 59.94Hz rather than 60Hz)
  -c, --sdtvon="MODE ASPECT"        Power on SDTV with MODE (PAL or NTSC) and ASPECT (4:3 14:9 or 16:9)
  -o, --off                         Power off the display
  -m, --modes=GROUP                 Get supported modes for GROUP (CEA, DMT)
  -M, --monitor                     Monitor HDMI events
  -s, --status                      Get HDMI status
  -a, --audio                       Get supported audio information
  -d, --dumpedid <filename>         Dump EDID information to file
  -j, --json                        Use JSON format for --modes output
  -n, --name                        Print the device ID from EDID
  -h, --help                        Print this information
```
Most commonly used switchs :
- `tvservice -s` get the current display information
- `tvservice -m CEA` or `tvservice -m DMT` : lists supported CEA or DMT modes
