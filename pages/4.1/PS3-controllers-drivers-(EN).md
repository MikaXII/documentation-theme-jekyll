---
layout: page
title: PS3 controllers drivers (EN)
wikiPageName: PS3-controllers-drivers-(EN)
menu: wiki
---

There are several version of the PS3 _sixaxis_ and _dualshock3_ available.

The recalbox support the official controllers by default. But if you have a GASIA on a Shanwan clone, you must change the driver in [[recalbox.conf|recalbox.conf-(EN)]] by modifying the line : 
`controllers.ps3.driver=official`

| Model  | Driver  |
| :------------ | :------------------- | 
| Sixaxis       | `official`           |
| Dualshock3    | `official`           |
| US Sixaxis    | `shanwan` :question: |
| Shanwan       | `shanwan`            |
| Gasia         | `gasia`              |

<br>
<br>
To determine what kind of clone you have (GASIA or SHANWAN), you can plug in USB your controller then use [dmesg command](https://github.com/recalbox/recalbox-os/wiki/Troubleshooting-dmesg-output-%28EN%29).  
You should see the controller's name.
