---
layout: page
title: Change Console entries order in EmulationStation (EN)
wikiPageName: Change-Console-entries-order-in-EmulationStation-(EN)
menu: wiki
---

# Steps
* Login through SSH on your Recalbox
* Go to the EmulationStation folder in share_init directory > `cd /recalbox/share_init/system/.emulationstation`
* Stop EmulationStation > `/etc/init.d/S31emulationstation stop`
* edit the `es_system.cfg` file > `nano es_system.cfg`
* In this file you will see every console entries Recalbox is able to manage. Just change the order of entries like you want them to appear in EmulationStation
* Save you changes
* Start EmulationStation > `/etc/init.d/S31emulationstation start`
* Done !

# Remarks
Unfortunately, it's not possible for now to make the "Favorites" entry at first position.
