---
layout: page
title: Configuration controleurs n64 (FR)
wikiPageName: Configuration-controleurs-n64-(FR)
menu: wiki
---

Mupen64plus n'est pas auto-configuré par Recalbox comme les autres émulateurs. Vous devez le faire manuellement.  

_Pour information : Le bouton **Hotkey** sera automatiquement assigné à la fonction exit de l'émulateur._

### A - Ajoutez la configuration de votre manette au système :  

Pour configurer votre manette, vous avez besoin d'informations à son sujet.

Allez à [[Accès root|https://github.com/recalbox/recalbox-os/wiki/acc%C3%A8s-root-sur-Terminal--%28FR%29]] et utilisez [[Commande jstest|https://github.com/recalbox/recalbox-os/wiki/Testez-votre-joystick-avec-jstest-%28FR%29]] :  

`jstest /dev/input/js0`

Dans mon cas, j'obtiens :  
```
Joystick (Broadcom Bluetooth Wireless  Joystick                        ) has 6 axes (X, Y, Z, Rz, Hat0X, Hat0Y)
and 12 buttons (Trigger, ThumbBtn, ThumbBtn2, TopBtn, TopBtn2, PinkieBtn, BaseBtn, BaseBtn2, BaseBtn3, BaseBtn4, BaseBtn5, BaseBtn6).
```

Une fois que le nom de la manette et que chaque bouton sont identifiés, vous devez éditer ce fichier `/usr/share/mupen64plus/InputAutoCfg.ini`

Utilisez cette commande :  

`nano  /usr/share/mupen64plus/InputAutoCfg.ini`

Maintenant, à la fin du fichier, ajoutez les informations de configuration, comme ceci :  

_Ceci est un exemple, avec des informations provenant de ma manette (nom de la manette, numéro de bouton etc...). Vous devez l'adapter avec les paramètres de votre manette_

```
[Broadcom Bluetooth Wireless  Joystick                        ]
plugged = True
plugin = 2
mouse = False
AnalogDeadzone = 4096,4096
AnalogPeak = 32768,32768
DPad R = hat(0 Right)
DPad L = hat(0 Left)
DPad D = hat(0 Down)
DPad U = hat(0 Up)
Start = button(9)
Z Trig = button(7)
B Button = button(2)
A Button = button(1)
C Button R = axis(3+)
C Button L = axis(3-)
C Button D = axis(2+)
C Button U = axis(2-)
R Trig = button(5)
L Trig = button(4)
Mempak switch = button(6)
Rumblepak switch = 
X Axis = axis(0-,0+)
Y Axis = axis(1-,1+)
```
  
Une fois que votre configuration est finie, faites `Ctrl+x` pour sortir de nano, acceptez de modifier le fichier avec `y` et appuyez sur `Entrée` pour sortir.  
Vous pouvez maintenant démarrer un jeu N64 et tester votre configuration.  

Votre configuration est bonne, vous l'aimez?? Parfait ^^  
Mais il y a un "problème". Quand vous mettez à jour votre Recalbox, tous ces fichiers de configuration sont mis à jour également.  
Il y aura donc une remise à zéro.   
Si vous ne voulez pas que cela se produise à chaque mise à jour, faites une sauvegarde de votre fichier `InputAutoCfg.ini`  
Vous pouvez aussi ajouter votre configuration au projet Recalbox. Vous devez aller à [cette issue](https://github.com/digitalLumberjack/recalbox-os/issues/437) et poster votre propre configuration comme commentaire.  
Ensuite nous l'ajouterons au système dans une prochaine mise à jour de Recalbox.  

### B - Ajouter des commandes spéciales


Mupen64plus ne supporte pas la combinaison de boutons, comme les émulateurs Retroarch, pour lancer des commandes spéciales.  
Mais vous pouvez affecter des boutons inutilisés à des commandes spécifiques, comme _sauvegarder/charger une sauvegarde, basculer un slot de sauvegarde, etc..._  

Pour cela, dans un 1er temps, vous devez identifier tous les boutons inutilisés dans votre configuration.  
Comme on l'a vu auparavant allez à [[Accès root|https://github.com/recalbox/recalbox-os/wiki/acc%C3%A8s-root-sur-Terminal--%28FR%29]] et utilisez [[Commande jstest|https://github.com/recalbox/recalbox-os/wiki/Testez-votre-joystick-avec-jstest-%28FR%29]] , ensuite notez les codes de vos boutons inutilisés.  

Maintenant, toujours en accès root, éditez votre fichier 'mupen64plus.cfg' avec cette commande :  

`nano /recalbox/configs/mupen64/mupen64plus.cfg`   

Ensuite allez vers la section appelée `[CoreEvents]` . La partie utile est :  
```
# Joystick event string for stopping the emulator
Joy Mapping Stop = ""
# Joystick event string for switching between fullscreen/windowed modes
Joy Mapping Fullscreen = ""
# Joystick event string for saving the emulator state
Joy Mapping Save State = ""
# Joystick event string for loading the emulator state
Joy Mapping Load State = ""
# Joystick event string for advancing the save state slot
Joy Mapping Increment Slot = ""
# Joystick event string for taking a screenshot
Joy Mapping Screenshot = ""
# Joystick event string for pausing the emulator
Joy Mapping Pause = ""
# Joystick event string for muting/unmuting the sound
Joy Mapping Mute = ""
# Joystick event string for increasing the volume
Joy Mapping Increase Volume = ""
# Joystick event string for decreasing the volume
Joy Mapping Decrease Volume = ""
# Joystick event string for fast-forward
Joy Mapping Fast Forward = ""
# Joystick event string for pressing the game shark button
Joy Mapping Gameshark = ""
```

Vous devez garder à l'esprit que Mupen64plus identifie le joueur 1 comme 'J0' le joueur 2 comme 'J1' etc...   
Donc par exemple, si vous voulez ajouter le bouton no 10 au joueur 1, pour la commande _"save savestates"_ , vous devez éditer le fichier comme ceci :  
`Joy Mapping Save State = "J0B10"`  
   
Et si vous voulez ajouter le bouton 5 du joueur 2 à la commande _"load savestates"_ vous éditerez votre fichier comme ceci :  
`Joy Mapping Load State = "J1B5"`   

Une fois la configuration faite, appuyez sur `Ctrl+x` pour sortir de nano, acceptez de modifier le fichier avec `y` et appuyez sur `Entrée` pour sortir.
