---
layout: page
title: Testez votre joystick avec jstest (FR)
wikiPageName: Testez-votre-joystick-avec-jstest-(FR)
menu: wiki
---

Afin de  tester les boutons et axes de vos manettes, vous pouvez utiliser l'exécutable `jstest`. Ce soft vous rapportera tous les événements concernant votre manette.   
Dans un premier temps, [connectez vous en root](https://github.com/digitalLumberjack/recalbox-os/wiki/acc%C3%A8s-root-sur-Terminal--%28FR%29)   
  
Pour savoir si vos manettes sont détectées par le système, utilisez la commande suivante :
```
cat /proc/bus/input/devices
```

Une fois que vos manettes sont bien détectées, un fichier spécial devrait avoir été créé pour chaque manette.   
Vous pouvez voir ces fichiers en listant les fichiers présents dans /dev/input :
```
ls /dev/input/js*
```

Maintenant, pour tester vos boutons et axes, collez le chemin du fichier spécial correspondant à votre manette comme argument à jstest.  
Par exemple, pour tester la première manette du système, faites :
```
jstest /dev/input/js0
```

Vous devriez obtenir un retour similaire à cet exemple : 
```
Driver version is 2.1.0.
Joystick (Logitech Logitech Cordless RumblePad 2) has 6 axes (X, Y, Z, Rz, Hat0X, Hat0Y)
and 12 buttons (BtnX, BtnY, BtnZ, BtnTL, BtnTR, BtnTL2, BtnTR2, BtnSelect, BtnStart, BtnMode, BtnThumbL, BtnThumbR).
Testing ... (interrupt to exit)
Axes:  0:     0  1:     0  Buttons:  0:off  1:off  2:off  3:off  4:off  5:off  6:off  7:off  8:off  9:off 10:off 11:off
```

Vous pouvez alors vérifier le comportement de chaque bouton et axe de votre contrôleur.
