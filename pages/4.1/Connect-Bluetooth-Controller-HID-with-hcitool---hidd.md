---
layout: page
title: Connect Bluetooth Controller HID with hcitool   hidd
wikiPageName: Connect-Bluetooth-Controller-HID-with-hcitool---hidd
menu: wiki
---

On keyboard

Tape F4 

ALT+F2

Need root access : LOGIN(root) Password (recalboxroot)

`hcitool scan`

`aa:bb:cc:dd:ee:ff               Name:Bluetooth HID`

`hidd --connect aa:bb:cc:dd:ee:ff`
`/etc/init.d/S31emulationstation start`
