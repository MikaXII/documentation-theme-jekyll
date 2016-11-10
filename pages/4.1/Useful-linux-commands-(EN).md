---
layout: page
title: Useful linux commands (EN)
wikiPageName: Useful-linux-commands-(EN)
menu: wiki
---

### Check the CPU temp:
To check the CPU temp execute the following command:
<br>`cat /sys/class/thermal/thermal_zone0/temp`
<br>Then divide the result by 1000 to get the temp in Celcius.

### Check the current overclocking applied values:
To check the overclock values, execute the following command:
`cat /boot/config.txt`
<br>The parameters are at the end of the file.
<br>I.e.:<br>
```
arm_freq=1050
core_freq=525
sdram_freq=480
force_turbo=0
over_voltage=4
over_voltage_sdram=2
gpu_freq=350
```

###Avoid to reboot the system if Mupen 64 (N64 emulator) freezes
If you encounter some freezes with your Mupen 64 emulator due to ROM incompatibilities, you can easily kill the emulator instead of reboot your raspberry:<br>

`ps aux | grep mupen64`   

Identify the process id (PID) related to mupen64 (below it will be 26193):<br>
```
26193 root     mupen64plus --corelib /usr/lib/libmupen64plus.so.2.0.0 --gfx /usr/lib/mupen64plus/mupen64plus-video-gliden64.so --configdir /recalbox/configs/mupen64/ --datadir /recalbox/configs/mupen64/ /recalbox/share/roms/n64/007 - GoldenEye (Europe).n64
26196 root     grep mupen64
```
Execute the following command with the identified PID of Mupen64:<br>

`kill -1 <your_PID>`<br>

Then you will be redirected to the main recalbox interface.

### Stop / Start emulstation
To stop emulstation:<br>
`/etc/init.d/S31emulationstation stop`<br>
<br>
To start emulstation:<br>
`/etc/init.d/S31emulationstation start`
