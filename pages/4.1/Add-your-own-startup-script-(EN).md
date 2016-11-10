---
layout: page
title: Add your own startup script (EN)
wikiPageName: Add-your-own-startup-script-(EN)
menu: wiki
---

You want to add your own startup script that will be executed on boot, here is what you have to know :   
All startup scripts are located in `/etc/init.d`. They are executed synchronously from the first to the last, in the natural order of their name. So `S31emulationstation` will be executed before `S99yourscript`.

The start method will be executed on boot, and stop method on shutdown.

Follow these steps to create your own :   
- get a [[root access on terminal|Root-access-on-terminal-(EN)]]   
- change directory to `/etc/init.d` with 
```
cd /etc/init.d
```
- execute `ls` to see current scripts
- copy S02serial to your new script :
```
cp S02serial S99myscript
```
- edit the script with vi or nano.
- reboot, or start your script with
```
/etc/init.d/S99myscript start
```
