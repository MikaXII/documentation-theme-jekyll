---
layout: page
title: PS3 controllers drivers (FR)
wikiPageName: PS3-controllers-drivers-(FR)
menu: wiki
---

Il existe différentes version de manettes PS3 _sixaxis_ et _dualshock3_ sur le marché.

Recalbox les supporte par défaut les manettes officielles. Mais si vous possédez un clone GASIA ou Shanwan vous devez modifier le pilote dans [[recalbox.conf|recalbox.conf-(FR)]] en modifiant la ligne:

`controllers.ps3.driver=official`

| Modèle | Pilote  |
| :------------ | :------------------- | 
| Sixaxis       | `official`           |
| Dualshock3    | `official`           |
| US Sixaxis    | `shanwan` :question: |
| Shanwan       | `shanwan`            |
| Gasia         | `gasia`              |

<br>
<br>
Pour déterminer quel type de clone vous possédez (GASIA ou SHANWAN), vous pouvez brancher en USB votre manette, puis utiliser la [commande dmesg](https://github.com/recalbox/recalbox-os/wiki/D%C3%A9pannage-dmesg-output--%28FR%29).   
Vous devriez alors voir le type de manette que vous possèdez.
