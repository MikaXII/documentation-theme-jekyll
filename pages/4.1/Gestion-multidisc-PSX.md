---
layout: page
title: Gestion multidisc PSX
wikiPageName: Gestion-multidisc-PSX
menu: wiki
---

**Avoir un seul fichier pour vos jeux multidisc est possible.** 

/!\ Rappel que vous devez disposez de vos propres images de disques PSX.

Il suffit de créer un fichier eboot contenant vos images iso,bin, img via le logiciel gratuit psx2psp.

**Vérifier que le fichier es_system.cfg uniquement sous version 3.x.x**

Via le terminal rendez vous vers `/root/.emultationstation/es_system.cfg `

Editez-le vérifier que les extensions .pbp .PBP sont présentes

`<extension>.img .IMG .pbp .PBP .bin .BIN .cue .CUE .iso .ISO</extension>`


**Création du fichier eboot**

Trouver sur le net, la version psx2psp v1.42, la télécharger et l’exécuter.
   
<a href="http://www.zimagez.com/zimage/psx2psp0.php" target="_blank" title="Visionner l'image"><img src="http://www.zimagez.com/miniature/psx2psp0.png" alt="Visionner l'image" /></a>   

1. Choisir le mode classic puis sur la partie de gauche charger un à un vos isos.   
2. Choisir votre répertoire d'enregistrement.   
3. Cliquer sur le bouton Convert, patienter.   

Uploader votre dossier ou renommer le fichier eboot créé vers votre recalbox dans le dossier /recalbox/share/roms/psx


**Changement de CD**

Pour changer de CD en cours de jeu il faut activer 2-3 options dans le menu retroarch.

– ouvrir le menu retroarch ingame (par défaut Hotkey + B)

– aller dans settings/general settings et passer l’option configuration save on exit sur on. Attention à partir de ce moment là toutes les modifications que vous effectuerez dans les options seront sauvegardées quand vous quitterez le menu retroarch.

– aller dans settings/input settings et chercher les options portant le nom, disk eject toggle, disk next, disk previous. Il faut alors leur affecter des touches de votre manettes n’ayant pas encore de fonction spéciale attribuée.

– Quitter retroarch et retourner in game.

Quand vous serez à l’écran d’un jeu vous demandant de changer de CD, il vous suffira alors d’éjecter virtuellement le CD (en faisant hotkey + le raccourci attribué à l’option disk eject toggle), de changer de cd, et de refermer virtuellement le lecteur cd. Votre jeu bootera alors automatiquement sur le CD suivant.

sujet sur le forum en cas de problème :    
http://blog.recalbox.com/forums/topic/roms-playstation-et-nombre-de-jeux/   

**Pour changer de cd sur PCSX-reARMed (r22)**   
 
Méthode pour des fichiers .bin    
 
Rentrer dans le menu Retroarch (Hotkey + B)   
Choisir Quick menu, puis core disk option.   
Ejecter le cd virtuel en choisissant disk cycle tray status.   
Puis chercher le repertoire où se trouve le cd que vous voulez charger (logiquement recalbox/roms/psx) avec disk image append.   
