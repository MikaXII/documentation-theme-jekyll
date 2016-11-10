---
layout: page
title: Cave Story (EN)
wikiPageName: Cave-Story-(EN)
menu: wiki
---

Cave story is a freeware platform-adventure video game released in 2004 for the PC,see [http://www.cavestory.org/](http://www.cavestory.org/) for more informations.  

##For the 3.2.11  
####Firstly :  
you have to edit emulatorlauncher.sh :  
```
nano /recalbox/scripts/emulatorlauncher.sh  
```  
and add to the end :  
```  
if [[ "$emulator" == "nxengine" ]]; then  
	/recalbox/scripts/runcommand.sh 2 "$retroarchbin -L $retroarchcores/nxengine_libretro.so --config /recalbox/configs/retroarch/retroarchcustom.cfg \"$1\""  
fi  
```
####Secondly :  
you have to edit es_system.cfg  
```  
nano /root/.emulationstation/es_systems.cfg  
```  
and add just before the   ```</systemList>```
```
<system>  
        <name>Ports</name>  
        <fullname>Ports</fullname>  
        <path>/recalbox/share/roms/ports/</path>  
        <extension>.exe .EXE .sh .SH</extension>  
        <command>/recalbox/scripts/emulatorlauncher.sh %ROM% "nxengine"</command>  
        <platform>ports</platform>  
        <theme>ports</theme>  
</system>  
```
####Thirdly:  
add the cave story data directory in the ports directory by scp ou winscp to do so :  
1) go to [http://www.cavestory.org/](http://www.cavestory.org/)  
2) download the windows version english (pre-patched) zip only (french version: not working)  
3) extract the zip file to a directory named something like cave_story or so  
4) rename the doconf.exe to doconf.exe.old or so  
5) upload the entire directory to your recalbox in /recalbox/share/roms/ports/ (maybe you have to create the ports directory first)  
6) reboot your recalbox and voilà!  

##For the 3.3.0
Add the cave story data directory in the share partition by scp ou winscp to do so :  
1) go to [http://www.cavestory.org/](http://www.cavestory.org/)  
2) download the windows version english (pre-patched) zip only (french version: not working)  
3) extract the zip file to a directory named something like cave_story or so  
4) rename the DoConfig.exe to DoConfig.exe.old or so  
5) upload the entire directory to your recalbox in /recalbox/share/roms/cavestory/  
`` with winscp under windows  ``  
``          scp cave_story root@RECALBOXIP:/recalbox/share/roms/cavestory/ (for example under linux)  
``  
6) reboot your recalbox and voilà!  
