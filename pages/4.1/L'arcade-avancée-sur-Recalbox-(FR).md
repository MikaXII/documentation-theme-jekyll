---
layout: page
title: L'arcade avancée sur Recalbox (FR)
wikiPageName: L'arcade-avancée-sur-Recalbox-(FR)
menu: wiki
---

Cette page est la suite de [[L'arcade facile pour Recalbox|L'arcade facile sur Recalbox (FR)]]

## BestArcade4Recalbox
Vous pouvez trouver ici la liste des jeux mame les plus importants et leur état de fonctionnement sur mame et fba_libretro :
[BestArcade4Recalbox](https://docs.google.com/spreadsheets/d/1F5tBguhRxpj1AQcnDWF6AVSx4av_Gm3cDQedQB7IECk/edit#gid=131171669&vpid=A179)

## ClrMamePro

Pour vérifier la compatibilité de vos jeux, vous pouvez utiliser clrmamepro et le [[tutoriel correspondant|Vérifier la version de vos roms avec clrmamepro (FR)]].


## Tous les émulateurs arcades sur la Recalbox
> Vous pouvez maintenant utiliser jusqu'à quatre émulateurs arcade différents dans la dernière version de Recalbox (mame, imame4all, piFba, fba libretro) and émulateur "simulé" Neogeo. Vous pouvez choisir le core que vous souhaitez utiliser dans [recalbox.conf](https://github.com/recalbox/recalbox-os/wiki/recalbox.conf-%28FR%29)


#### piFBA
_Recalbox (toutes les versions)_
* piFBA est le mieux optimisé des émulateurs FBA sur la RecalBox
* Il utilise le romset MAME version: **FBA 0.2.96.71** qui est basé sur le set MAME 0.114 (Avril 2007)
 * Poids : 3.62GB
 * Romsets émulées : 684 (Pas de clone dans ce set)
* _répertoire des roms :_ fba
* Vous pouvez trouver la liste des jeux compatibles sur la RecalBox à l'emplacement suivant [/recalbox/share/roms/fba/clrmamepro/piFBA_gamelist.txt](https://raw.githubusercontent.com/recalbox/recalbox-buildroot/rb-4.0.X/board/recalbox/fsoverlay/recalbox/share_init/roms/fba/clrmamepro/piFBA_gamelist.txt)
* Vous trouverez le fichier .dat pour vérifier les roms avec clrmamepro à l'emplacement suivant [/recalbox/share/roms/fba/clrmamepro/fba_029671_od_release_10_working_roms.dat](https://raw.githubusercontent.com/recalbox/recalbox-buildroot/rb-4.0.X/board/recalbox/fsoverlay/recalbox/share_init/roms/fba/clrmamepro/fba_029671_od_release_10_working_roms.dat)

#### imame4all
_Recalbox (toutes les versions)_
* imame4all est recommandé pour les vieux jeux qui ne fonctionnent pas avec piFBA
* Il utilise le romset MAME version: **0.37b5** (Juillet 2000)
 * Poids : 1.86GB
 * Romsets émulées : 2 270 (inclu clones etc...)
 * Active Sets 2241/2241
 * ·Parents 560/560
 * ·Clones 990/990
 * ·Others 690/690
 * ·BIOS 1/1
 * _(Si un jeu ne marche pas dans le romset 0.37b5, vous pouvez essayer avec le jeu du romset mame 0.81)_
* _répertoire des roms :_ mame
* Vous pouvez trouver la liste des jeux compatibles sur la RecalBox à l'emplacement suivant [/recalbox/board/recalbox/share/roms/mame/clrmamepro/imame4all_gamelist.txt](https://raw.githubusercontent.com/recalbox/recalbox-buildroot/rb-4.0.X/board/recalbox/fsoverlay/recalbox/share_init/roms/mame/clrmamepro/imame4all/imame4all_gamelist.txt)
* Vous trouverez le fichier .dat pour vérifier les roms avec clrmamepro à l'emplacement suivant [/recalbox/share/roms/mame/clrmamepro/imame4all.dat](https://raw.githubusercontent.com/recalbox/recalbox-buildroot/rb-4.0.X/board/recalbox/fsoverlay/recalbox/share_init/roms/mame/clrmamepro/imame4all/imame4all.dat)

####lr-mame2003
_Recalbox ( depuis la v3.3.0-beta-11)_
* lr-mame2003 est un emulateur plus récent que imame4all. Beaucoup plus de jeux sont fonctionnels mais cet émulateur n'est disponible que sur RPI2 et RPI3.
* mame romset version : **0.78** (December 2003)
 * Taille : 1.86GB
 * Romsets emulés : 4 705 (includes clones etc...)
 * Active Sets 4705/4705
 * ·Parents 1042/1042
 * ·Clones 2039/2039
 * ·Others 1624/1624
 * ·BIOS 1/1
* _répertoire des roms :_ mame
* Vous pouvez trouver la liste des jeux compatibles sur la RecalBox à l'emplacement suivant _(bientôt)_
* Vous trouverez le fichier .dat pour vérifier les roms avec clrmamepro à l'emplacement suivant [/recalbox/recalbox-os/master/wiki/dat/mame2003.dat](https://raw.githubusercontent.com/recalbox/recalbox-buildroot/rb-4.0.X/board/recalbox/fsoverlay/recalbox/share_init/roms/mame/clrmamepro/mame2003/mame2003.dat)

#### libretro FBA
* libretro FBA est un core de libretro basé sur FBA, il est le seul a faire tourner certains systèmes (CPS3 par exemple) mais est moins rapide que piFBA

_Recalbox (v3.2.11)_ 
* Il utilise le romset FBA version: **FBA 0.2.97.30** qui est basé sur le set MAME 0.154 (Juillet 2014)
 * Poids : 9.15GB
 * Romsets émulés : 3 369 (inclu clones etc...)
 * Active Sets 3369/3369
 * ·Parents 710/710
 * ·Clones 2146/2146
 * ·Others 508/508
 * ·BIOS 5/5
* _répertoire des roms :_ fba_libretro


_Recalbox (depuis la v3.3.0-b7)_
* Il utilise le set de rom FBA version : *FBA 0.2.97.36* qui est basé sur le set MAME 0.161(April 2015)
 * Romsets émulés : 3 743 (includes clones etc...)
 * Active Sets 3743/3743
 * ·Parents 802/802
 * ·Clones 2408/2408
 * ·Others 533/533
 * ·BIOS 6/6  

_Recalbox (depuis la v3.3.0-b15)_
* Il utilise le set de rom FBA version : *FBA 0.2.97.37* qui est basé sur le set MAME 0.167
* Vous pouvez trouver le changelog de FBA à l'emplacement suivant [fbalpha changelog](http://www.fbalpha.com/view/227/)
* Vous pouvez trouver la liste des jeux compatibles sur la RecalBox [/libretro/libretro-fba/blob/master/gamelist.txt](https://raw.githubusercontent.com/recalbox/recalbox-buildroot/rb-4.0.X/board/recalbox/fsoverlay/recalbox/share_init/roms/fba_libretro/fba_libretro_gamelist.txt)
* Vous trouverez le fichier .dat pour vérifier les roms avec clrmamepro à l'emplacement suivant [/recalbox/recalbox-os/master/wiki/dat/fba_0.2.97.37.dat](https://raw.githubusercontent.com/recalbox/recalbox-buildroot/rb-4.0.X/board/recalbox/fsoverlay/recalbox/share_init/roms/fba_libretro/fba_0.2.97.37.dat)


##### Neogeo (simulé)    
Le système Neogeo n'est pas un émulateur en soit.   
Il permet d'isoler séparément les jeux neogeo des autres jeux d'arcade, ils apparaîtront alors comme un système dédié dans EmulationStation.   
    
   
_Recalbox 3.3.X_   
Vous devez configurer le core que vous utiliserez dans [recalbox.conf](https://github.com/recalbox/recalbox-os/wiki/recalbox.conf-%28FR%29). 

_Recalbox 4.x.x_   
vous pouvez configurer le core directement dans Emulationstation.
Bouton start > Options jeux > emulateurs 
