---
layout: page
title: Audio HiFiBerry (EN)
wikiPageName: Audio-HiFiBerry-(EN)
menu: wiki
---

# General
To get a high-quality audio signal from the Raspberry Pi, a HiFiBerry DAC (Digital - Analog Converter) audio card can be used. The DACs are available in different versions:  

**Raspberry Pi A+, B+, 2 and 3**  
- DAC+ Light
- DAC+ Standard RCA
- DAC+ Standard Phone
- DAC+ Pro

**Raspberry Pi A and B**  
- DAC Standard version with RCA connectors  

The characteristics of the different boards can be compared on **[hifiberry.com](http://www.hifiberry.com)**. The DAC+ boards can be plugged directly onto the GPIO of the Raspberry Pi pins with no additional effort. Those pins that are not required by the DAC+, can still be used for other applications. For this, additional headers must be soldered to the DAC+ Board. In the figure below you see all GPIO pins which are used by the DAC+.

![hifiberry](https://cloud.githubusercontent.com/assets/17233889/16976447/3755fcc8-4e4f-11e6-847b-1233d687ffd7.png)  
 
The DAC version for Raspberry Models A and B must be installed on the P5 header. An 8 - pin header on the board must be soldered additionally to achieve this. 

Once the DAC board is mounted, a few settings in the software must be made to ensure that everything works fine.

# Device tree and config
With Linux 3.18 (or higher) there is a new way to load device drivers. It is called «device tree overlay». This is a big point for the configuration of the HiFiBerry DAC Boards. For this purpose, only the _/boot/config.txt_ has to be edited and the following line (at any point) must be inserted or changed:

**DAC/DAC+ Light**  
- `dtoverlay=hifiberry-dac`

**DAC+ Standard/Pro**  
- `dtoverlay=hifiberry-dacplus`

Then, the *_default_* soundcard must be selected. For this you have to create the file _/etc/asound.conf_ with the following content:

`pcm.!default {`   
`type hw card 0`  
` } `  
`ctl.!default {`  
`type hw card 0`  
` } `

Then, reboot your device.  
  
Now the HiFiBerry should be selected as the default soundcard and you may finally enjoy good stereo sound from your Raspberry Pi audio jack.

**IMPORTANT:** The audio volume **CANNOT** be changed via the EmulationStation menu after that. The only way to do this is via _Alsamixer/Amixer_.

# Alsamixer/Amixer
ALSA-soundcards, like the HiFiBerry, can be controlled via the Alsamixer and Amixer tools. 
While Alsamixer provides the user with a graphical user interface on which the various controls of the soundcard can be accessed quickly and easily, Amixer is a text-based tool which can be used very well to write your own scripts.

Since **alsa-utils** is already installed in Recalbox, the HiFiBerry can be configured without additional effort.

**IMPORTANT:** The DAC+ Light Board as well as the old DAC **DO NOT** have any ALSA mixer controls.

With the command `amixer` the terminal gives you an overview of all available controls of the HiFiBerry board. The best way to change the audio volume is to use the master control (Overall volume).  Depending on the HiFiBerry board the master control is called different: ‘PCM’, ‘Digital’, ‘Master’ (Just try it out or play manually with the Alsamixer controls to find the master control).


The audio volume can be changed as follows via the terminal:

-	`amixer sset ‘Master’ -- 90%` (in percentage, does not work well because the volume scale is logarithmic but the percentages are linear - > not recommended) or
-	`amixer sset ‘Master’ -- -3dB` (in decibel, dB is the most useful unit for audio-> highly recommended) oder
-	`amixer sset ‘Master’ – 2000` (fixed hardware values, every control has limits without units (depending on the control type) which can be used as well -> not recommended)

There are many, many more commands to access the different controls. More information can be found at Google: **amixer**, **alsamixer**.

Here is an example to change the audio volume in a self-made script. Of course there are a lot of other solutions but the following is tested and works.

First of all, import call from subprocess:  
`from subprocess import call`

Then call the following command (in this example dB is used, the master control is «Digital»):  
`call(["amixer", "sset", "Digital", "--", str(YourDesiredVolume)+"dB"])`

This script line can now, for example, be used in conjunction with GPIO inputs for adjusting the volume by pressing a button.

**Below you see a summary of different command for various controls (Command-Line):**

- `amixer sset 'PCM' 70%` (Percentages)
- `amixer sset 'Master' 3dB` (Decibel)
- `amixer sset 'Mic' 4` (Fixed hardware values)
- `amixer sset 'PCM' 10%+` (Relative values with + and - as a suffix to the percentage, dB or hardware values)
- `amixer sset 'Line' cap` (Recording on/off: cap, nocap)
- `amixer sset 'Mic' mute` (Playback on/off: mute, unmute)
- `amixer sset 'Master' off` (On/Off: on/off)
- `amixer sset 'Mic Select' 'Mic1'` (Device name (arises from the items))

See: **[wiki.ubuntuusers.de/amixer](https://wiki.ubuntuusers.de/amixer/)**
