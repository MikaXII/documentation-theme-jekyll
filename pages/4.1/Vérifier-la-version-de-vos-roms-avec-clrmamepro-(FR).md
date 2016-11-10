---
layout: page
title: Vérifier la version de vos roms avec clrmamepro (FR)
wikiPageName: Vérifier-la-version-de-vos-roms-avec-clrmamepro-(FR)
menu: wiki
---

iFBA, libretro_fba et iMame4all acceptent tous des versions de roms différentes.
Pour savoir si vos roms sont compatibles, vous pouvez utiliser clrmamepro.

Ce logiciel va utiliser un fichier .dat qui contient les informations des roms pour une version donnée, et va vérifier si vos roms correspondent. Il utilise crc sur tous les fichiers dans des archives .zip, et vous dira quels sont les fichiers manquants ou ne correspondants pas.

Premièrement récupérez le fichier .dat correspondant à l'émulateur que vous souhaitez utiliser :

- piFBA : https://raw.githubusercontent.com/digitalLumberjack/recalbox-os/master/wiki/dat/fba_029671_od_release_10_working_roms.dat
- iMame4All : https://raw.githubusercontent.com/digitalLumberjack/recalbox-os/master/wiki/dat/imame4all.dat    
- Fba 0.2.97.37 : https://raw.githubusercontent.com/recalbox/recalbox-buildroot/rb-4.0.X/board/recalbox/fsoverlay/recalbox/share_init/roms/fba_libretro/fba_0.2.97.37.dat   
- Mame 2003 : https://raw.githubusercontent.com/recalbox/recalbox-buildroot/rb-4.0.X/board/recalbox/fsoverlay/recalbox/share_init/roms/mame/clrmamepro/mame2003/mame2003.dat   

Télécharger ClrmamePro : 
Utilisateur windows : http://mamedev.emulab.it/clrmamepro/ (fonctionne dans wine pour les utilisateurs linux)   
Utilisateur MacOS X : http://www.emulab.it/, une version en beta est disponible.   
    
Chargez votre fichier .dat dans la section « **Profiler** ».

Allez dans **Settings** et définissez le « rom path » vers votre répertoire contenant vos roms.

Finalement, utilisez le **Scanner** pour scanner votre répertoires de roms, et vérifiez les logs pour voir quels sont les fichiers manquants.
