---
layout: page
title: Tester votre joystick avec jstest (FR)
wikiPageName: Tester-votre-joystick-avec-jstest-(FR)
menu: wiki
---

Pour tester les boutons et joysticks de vos manettes, vous pouvez utiliser la commande `jstest` qui permet
de lister des informations concernant vos manettes.
Premièrement vous devez avoir un [accès root via votre terminal] (https://github.com/digitalLumberjack/recalbox-os/wiki/acc%C3%A8s-root-sur-Terminal--%28FR%29)

Pour savoir si vos manettes sont détectées par le système utiliser la commande suivante : 

```
cat /proc/bus/input/devices
```

Une fois vos manettes détectés, un évenement spécial est créé pour chacun d'eux dans  /dev/input, 
vous pouvez les voir en les listant avec cette commande :
```
ls /dev/input/js*
```

Maintenant vous pouvez lancer une commande spécial pour tester les boutons et axes de votre manette.
Par exemple pour tester votre première manette sur le système : 
```
jstest /dev/input/js0
```

Vous devriez voir la sortie suivante : 
```
Driver version is 2.1.0.
Joystick (Logitech Logitech Cordless RumblePad 2) has 6 axes (X, Y, Z, Rz, Hat0X, Hat0Y)
and 12 buttons (BtnX, BtnY, BtnZ, BtnTL, BtnTR, BtnTL2, BtnTR2, BtnSelect, BtnStart, BtnMode, BtnThumbL, BtnThumbR).
Testing ... (interrupt to exit)
Axes:  0:     0  1:     0  Buttons:  0:off  1:off  2:off  3:off  4:off  5:off  6:off  7:off  8:off  9:off 10:off 11:off
```

Et maintenant vous pouvez regarder la réponse de chaque bouton et axe de votre manettes.
