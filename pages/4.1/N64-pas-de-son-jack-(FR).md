---
layout: page
title: N64 pas de son jack (FR)
wikiPageName: N64-pas-de-son-jack-(FR)
menu: wiki
---

Si vous utilisez la prise jack de votre rpi comme sortie son, et que le son n'est pas disponible avec l'émulateur N64, veuillez suivre ce qui suit.   

Connectez vous en [accès root](https://github.com/digitalLumberjack/recalbox-os/wiki/acc%C3%A8s-root-sur-Terminal--%28FR%29)   
Editez le fichier de configuration de mupen64plus avec la commande suivante :    

`nano /recalbox/configs/mupen64/mupen64plus.cfg`

Puis modifiez la ligne   

```
# Audio output to go to (0) Analogue jack, (1) HDMI
 OUTPUT_PORT = 1
```

En 

```
# Audio output to go to (0) Analogue jack, (1) HDMI
 OUTPUT_PORT = 0
```

Vous n'avez alors plus qu'à enregistrer le fichier avec `ctrl+x` puis `y` suivi de `entrée`, puis à rebooter votre rpi avec la commande `reboot`.   
Le son devrait être disponible.

Cette modification peut également être faite à partir de [WinSCP](https://github.com/digitalLumberjack/recalbox-os/wiki/acces-via-WinSCP-%28FR%29) si vous êtes allergique au terminal.
