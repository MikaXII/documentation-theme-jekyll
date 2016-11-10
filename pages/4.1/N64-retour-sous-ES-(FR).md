---
layout: page
title: N64 retour sous ES (FR)
wikiPageName: N64-retour-sous-ES-(FR)
menu: wiki
---

Mupen64plus n'est pas configuré automatiquement par recalbox comme c'est le cas pour les autres émulateurs. Vous devez donc le faire manuellement.

Le mode vidéo utilisé pour la N64 est configuré dans le fichier [recalbox.conf](https://github.com/recalbox/recalbox-os/wiki/recalbox.conf-%28FR%29). 

Par défaut le mode utilisé est `n64.videomode=DMT 9 HDMI` correspondant à une résolution en **800x600**. Il s'agit de la **résolution maximale** utilisable par un Raspberry Pi 2 car une résolution supérieure ne permet pas d'assurer une fluidité suffisante.

Cependant tous les écrans (TV, moniteur...) ne possèdent pas la même compatibilité envers les modes vidéos. Si vous lancez un jeux N64 et que vous avez un écran noir avant de retourner sous Emulationstation c'est que votre mode vidéo actuel n'est pas compatible avec votre écran. Dans ce cas vous devez déterminer les modes vidéos compatibles pour votre écran.

Pour cela connectez vous en [root](https://github.com/recalbox/recalbox-os/wiki/Root-access-on-terminal-%28FR%29) et exécutez les deux commandes suivantes :

`tvservice -m DMT`  

et

`tvservice -m CEA` 

Vous devriez avoir un résultat comparable à ::
```
[root@RECALBOX ~]# tvservice -m DMT
Group DMT has 16 modes:
           mode 4: 640x480 @ 60Hz 4:3, clock:25MHz progressive 
           mode 5: 640x480 @ 72Hz 4:3, clock:31MHz progressive 
           mode 6: 640x480 @ 75Hz 4:3, clock:31MHz progressive 
           mode 8: 800x600 @ 56Hz 4:3, clock:36MHz progressive 
           mode 9: 800x600 @ 60Hz 4:3, clock:40MHz progressive 
           mode 10: 800x600 @ 72Hz 4:3, clock:50MHz progressive 
           mode 11: 800x600 @ 75Hz 4:3, clock:49MHz progressive 
           mode 16: 1024x768 @ 60Hz 4:3, clock:65MHz progressive 
           mode 17: 1024x768 @ 70Hz 4:3, clock:75MHz progressive 
           mode 18: 1024x768 @ 75Hz 4:3, clock:78MHz progressive 
           mode 21: 1152x864 @ 75Hz 4:3, clock:108MHz progressive 
           mode 32: 1280x960 @ 60Hz 4:3, clock:108MHz progressive 
           mode 35: 1280x1024 @ 60Hz 5:4, clock:108MHz progressive 
           mode 36: 1280x1024 @ 75Hz 5:4, clock:135MHz progressive 
  (prefer) mode 57: 1680x1050 @ 60Hz 16:10, clock:119MHz progressive 
           mode 58: 1680x1050 @ 60Hz 16:10, clock:146MHz progressive 
```
et
```
[root@RECALBOX ~]# tvservice -m CEA
Group CEA has 5 modes:
           mode 1: 640x480 @ 60Hz 4:3, clock:25MHz progressive 
           mode 2: 720x480 @ 60Hz 4:3, clock:27MHz progressive 
           mode 3: 720x480 @ 60Hz 16:9, clock:27MHz progressive 
  (native) mode 4: 1280x720 @ 60Hz 16:9, clock:74MHz progressive 
           mode 16: 1920x1080 @ 60Hz 16:9, clock:148MHz progressive 
```

Identifiez à présent un mode vidéo ayant une résolution **égale** ou **inférieure** à **800x600** pour définir ce nouveau mode comme celui par défaut pour la N64 dans le fichier [recalbox.conf](https://github.com/recalbox/recalbox-os/wiki/recalbox.conf-%28FR%29).

Exemple : Si je choisis le mode 
```
Group CEA has 5 modes:
           mode 1: 640x480 @ 60Hz 4:3, clock:25MHz progressive
```

J'éditerai mon fichier "[recalbox.conf](https://github.com/recalbox/recalbox-os/wiki/recalbox.conf-%28FR%29) tel que : 
* mode vidéo par défaut dans recalbox.conf : `n64.videomode=DMT 9 HDMI`   
* nouveau mode vidéo : `n64.videomode=CEA 1 HDMI`

#### Cas particulier : les écrans CRT
Si vous utilisez un écran **CRT** vous devez définir le mode vidéo de la façon suivante : `n64.videomode=default`  
