---
layout: page
title: Commandes linux (FR)
wikiPageName: Commandes-linux-(FR)
menu: wiki
---


# 1- Commandes courantes à connaître
Voici une liste de commande linux qui vous seront utiles pour naviguer dans recalboxOS via un terminal ou putty.

**Commande ls**

Son équivalent sous windows est DIR. Elle permet de lister le contenu d'un dossier. 
Consulter les options disponibles sur [cette page](http://pwet.fr/man/linux/commandes/ls)

**Commande cd** 

Son équivalent sous windows est CD. Elle permet de changer de répertoire (CD = Change Directory)
Consulter les options disponibles sur [cette page](http://pwet.fr/man/linux/commandes/posix/cd)

**Commande cp** 

Son équivalent sous windows est COPY. Elle permet de copier des fichiers ou des répertoires
Consulter les options disponibles sur [cette page](http://pwet.fr/man/linux/commandes/cp)

**Commande mv**

Son équivalent sous windows est move ou ren. Elle permet de déplacer ou de renommer un fichier ou répertoire
Consulter les options disponibles sur [cette page](http://pwet.fr/man/linux/commandes/mv)

**Commande mkdir**

Son équivalent sous windows est mkdir ou md. Elle permet de créer un répertoire vide.
Consulter les options disponibles sur [cette page](http://pwet.fr/man/linux/commandes/mkdir)

**Commande rmdir**

Son équivalent sous windows est rmdir ou rd. Elle permet de supprimer un répertoire.
Consulter les options disponibles sur [cette page](http://www.linux-france.org/article/man-fr/man1/rmdir-1.html)

**Commande nano**

Nano est un petit éditeur de texte.
Consulter les options disponibles sur [cette page](http://www.delafond.org/traducmanfr/man/man1/nano.1.html)

**Commande chmod**

Permet de modifier les autorisations d'accès à une fichier

syntaxe :
` chmod 0775 /chemin/fichier`
Consulter les options disponibles sur [cette page](http://pwet.fr/man/linux/commandes/chmod)

**Commande wget**

Permet de télécharger une source disponible sur internet.

# 2 - Commandes spécifiques
## Vérifier la température du processeur du Raspberry
Pour vérifier la température du processeur (CPU), exécutez la commande suivante : 
`cat /sys/class/thermal/thermal_zone0/temp`

Puis divisez le résultat par 1000 pour avoir la température en Celcius.

## Vérifier les paramètres d'overclocking appliqués
Pour vérifier les valeurs d'overclocking appliquées, exécutez la commande suivante : 
`cat /boot/config.txt`

Les paramètres qui vous intéressent sont à la fin du fichier (voir exemple ci-dessous) :<br>
```
arm_freq=1050
core_freq=525
sdram_freq=480
force_turbo=0
over_voltage=4
over_voltage_sdram=2
gpu_freq=350
```

## Eviter de redémarrer le système si l'émulateur N64 (Mupen64) plante
Si vous rencontrez des problèmes de plantages / freeze avec l'émulateur N64 (Mupen64), due notamment à des problèmes de compatibilité avec les ROMs, vous pouvez facilement "tuer" l'émulateur au lieu de redémarrer le Rapsberry. 
Pour cela vous devez identifier l'identifiant du processus Mupen64 avec la commande suivante : `ps aux | grep mupen64`.

Vous devriez obtenir une liste similaire à :
```
**26193** root     mupen64plus --corelib /usr/lib/libmupen64plus.so.2.0.0 --gfx /usr/lib/mupen64plus/mupen64plus-video-gliden64.so --configdir /recalbox/configs/mupen64/ --datadir /recalbox/configs/mupen64/ /recalbox/share/roms/n64/007 - GoldenEye (Europe).n64
26196 root     grep mupen64
```  
Dans le cas présent, l'identiant du processus Mupen64 (PID) est **26193**. Vous pouvez maintenant tuer le processus Mupen64 avec la commande suivante : `kill -1 <votre_PID>` 

Soit pour notre example `kill -1 26193`

Une fois le processus tué, vous retournerez automatiquement sur Emulationstation.

## Arrêter / démarrer emulationstation
Pour mettre à jour la liste des ROMs par exemple ou pour mettre à jour les images des jeux nouvellement scrapés depuis votre PC vous devrez arrêter puis redémarrer Emulationstation:
* Arrêt : `/etc/init.d/S31emulationstation stop`
* Redémarrage / démarrage : `/etc/init.d/S31emulationstation start`
