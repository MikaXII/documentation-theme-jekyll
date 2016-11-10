---
layout: page
title: Connect your recalbox to a DVI screen (EN)
wikiPageName: Connect-your-recalbox-to-a-DVI-screen-(EN)
menu: wiki
---

You must connect the recalbox on a DVI screen but you have a black screen ?

Just [edit the config.txt file](https://github.com/digitalLumberjack/recalbox-os/wiki/Edit-the-config.txt-file-%28EN%29), and comment the line   
`hdmi_drive=2`  
with a # :  
`#hdmi_drive=2`


On recalbox v4.0.0, `/boot `partition is on **read-only**.   
So before editing your `config.txt`, you must mount your `/boot` partition with read-write rights.  
Go on [root acces](https://github.com/recalbox/recalbox-os/wiki/Root-access-on-terminal-%28EN%29), then type this command : `mount -o remount, rw /boot`
