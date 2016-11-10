---
layout: page
title: Connectez votre recalbox à un CRT avec composite  (FR)
wikiPageName: Connectez-votre-recalbox-à-un-CRT-avec-composite--(FR)
menu: wiki
---

Si vous souhaitez connecter votre recalbox sur un CRT, vous aurez besoin d'un mini-jack vers RCA comme celui-ci
![](https://cms-assets.tutsplus.com/uploads/users/31/posts/21821/image/4poleAV2.png)

Attention, sur les câbles de camescopes, la sortie vidéo pourrait être sur la prise audio droite (rouge).

De plus, le type de câble nécessaire n'étant  pas vraiment  répandu, il est préférable de tester au Multimétre que le câble utilisé correspond bien au schéma proposé ci-dessus ( Une inversion du Ground et de la vidéo sur le jack entraine une image noir & Blanc sautillante, signe d'un câble inadapté).

Attention pour recalbox 4.0.0 vous [devez passer la partition en écriture](https://github.com/recalbox/recalbox-os/wiki/partition-en-ecriture-%28FR%29)

Modifiez le fichier /boot/config.txt en **commentant toutes les lignes commençant par `hdmi_`** avec le symbole `#`, et ajoutant le sdtv_mode supporté:
```
sdtv_mode=0    Normal NTSC   
sdtv_mode=1    Japanese version of NTSC – no pedestal  
sdtv_mode=2    Normal PAL   
sdtv_mode=3    Brazilian version of PAL – 525/60 rather than 625/50, different subcarrier
``` 

Finalement, ajoutez ``` hdmi_ignore_hotplug=1``` pour forcer le composite.

Votre config.txt devrait ressembler à ça :
```
sdtv_mode=2
hdmi_ignore_hotplug=1
```

Ensuite éditez [[recalbox.conf|recalbox.conf-(FR)]] et réglez `global.videomode` à `default`:  
```
global.videomode=default
```
Si vous utilisez l'emulateur n64 pensez aussi à commenter cette ligne : 
```
n64.videomode=DMT 9 HDMI
```
et décommenter celle-ci :
```
n64.videomode=default
```
Pour finir, désactivez le lissage des jeux et tous les shaders dans le menu ES (START -> OPTIONS DES JEUX) ce qui vous permettra d'avoir le rendu original sur tous les systèmes !

Enjoy !
