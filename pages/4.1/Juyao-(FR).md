---
layout: page
title: Juyao (FR)
wikiPageName: Juyao-(FR)
menu: wiki
---

### Pinout   
La carte est l'une de celle qui permet de raccorder le plus de boutons et gère deux joueurs.  
Suivez le câblage suivant :  
![Juyao mapping keys](http://image.dhgate.com/0x0/f2/albu/g2/M00/F2/A5/rBVaGlZhCQWAUlMrAAD1xDQpwYk580.jpg)  
   
Sur certaines cartes, J1 et J2 sont inversés, nous vous conseillons de tester vos stick avant de tout raccorder.  
Le risque serait que votre J1 soit à droite, votre J2 à gauche.  
  
### Paramétrage   
Les interfaces USB Juyao nécessitent quelques paramétrages avant d'être reconnues par Recalbox 4.0.0  
_Dans la version 4.1, les configurations suivantes seront obsolètes._  
  
1. Commencez par vous connecter en SSH avec WINSCP et PuTTY, comme indiqué ici :    https://github.com/recalbox/recalbox-os/wiki/acces-via-WinSCP-%28FR%29  
2. Passez votre partition en écriture en suivant le guide suivant :  
https://github.com/recalbox/recalbox-os/wiki/partition-en-ecriture-%28FR%29  
`mount -o remount,rw /boot`  
3. Editez ensuite le fichier situé dans `/boot/cmdline.txt` avec notepad++ sous windows ou en ssh `nano /boot/cmdline.txt`  
Ajoutez en fin de ligne avec un espace après les derniers mots  
`usbhid.quirks=0x314:0x328:0x040`   
Enregistrez la modification (cltr+x sous nano puis Y pour sortir, ou simplement ctrl+s puis alt+F4)  
4. Redémarrez le rpi via l'interface du rpi ou via ssh avec la commande `reboot`  
5. Rendez-vous dans l'interface de EmulationStation puis configurez uniquement le joueur 1 "options manettes" avec le schéma d'un pad Snes.  
Attribuez le J1  
6. Lancez un jeu 2 joueurs et testez vos joysticks et boutons. (exemple : via Street Fighter)  
  
  
### Configuration 
  
Nous insistons sur le fait qu'il suffit de faire ***seulement*** la configuration du joueur 1 directement dans Emulationstation.  
La configuration du joueur 2 devrait fonctionner si le mappage est bien le même.   
N’essayez pas configurer le joueur 2, cela écraserait la configuration du joueur 1.  
