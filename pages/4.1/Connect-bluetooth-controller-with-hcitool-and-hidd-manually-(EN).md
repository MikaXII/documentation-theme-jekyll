---
layout: page
title: Connect bluetooth controller with hcitool and hidd manually (EN)
wikiPageName: Connect-bluetooth-controller-with-hcitool-and-hidd-manually-(EN)
menu: wiki
---

You can connect your bluetooth controller manually. 

You will need to [get a root access](https://github.com/digitalLumberjack/recalbox-os/wiki/Root-access-on-terminal-%28EN%29)

Put your bluetooth controller in association mode, and type :   
`hcitool scan`

That will return the mac address of the controller :  
`aa:bb:cc:dd:ee:ff               Name:Bluetooth HID`

Then create the connection to the controller :  
`hidd --connect aa:bb:cc:dd:ee:ff`

And restart emulationstation :  
`/etc/init.d/S31emulationstation start`
