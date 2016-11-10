---
layout: page
title: Configuration shaders
wikiPageName: Configuration-shaders
menu: wiki
---

Voici comment ajouter un shader ou donne un rendu graphique à votre recalbox.
Merci à ironic pour ses explications et ses captures d'écran

Pour commencer il vous faut le logiciel [winscp](https://github.com/digitalLumberjack/recalbox-os/wiki/acces-via-WinSCP-%28FR%29) pour transférer fichiers et modifier d autres.


Télécharger le fichier scanline.glsl : https://app.box.com/s/10rjdgnc3a4uihxsnhal29rrekt5v17o

Puis le transférer vers un dossier **shaders** , le créer si il n existe pas

exemple : /recalbox/share/system/shaders

Attribuer les droits d’exécutions sur le dossier et le fichier

via winscp : faire un clic droit >propriétés > 0775

Editer le fichier `/recalbox/scripts/config/retroarch/retroarchcustom.cfg` 

Ajouter : 

`video_shader = "/recalbox/share/system/shaders/scanline.glsl"`

`video_shader_dir = "/recalbox/share/system/shaders/"`

`video_shader_enable = "true"`

Enregistrer les modifications.

Redémarrer votre recalbox.

Pour obtenir d autres **shaders** vous pouvez en télécharger sur cette page : https://github.com/gizmo98/common-shaders

il suffit de cliquer sur le bouton en bas à droite **download zip**

Voici des exemples 
Avant - Sans scanline sans lissage : 
![Sans Scanline sans lissage](http://rnc.free.fr/RaspberryPi/FinalFightScanline/5%20-%20pas%20de%20scanline%20+%20pas%20de%20lissage.jpg)


Après
Scanline Avec lissage
![Avec Scanline – Avec Lissage](http://rnc.free.fr/RaspberryPi/FinalFightScanline/1%20-%20scanline%20+%20lissage.jpg)
![Avec Scanline – Avec Lissage](http://rnc.free.fr/RaspberryPi/FinalFightScanline/2%20-%20scanline%20+%20lissage.jpg)

Avec scanline sans lissage
![Avec Scanline – sans Lissage](http://rnc.free.fr/RaspberryPi/FinalFightScanline/3%20-%20scanline%20+%20pas%20de%20lissage.jpg)
![Avec Scanline – sans Lissage](http://rnc.free.fr/RaspberryPi/FinalFightScanline/4%20-%20scanline%20+%20pas%20de%20lissage.jpg)

