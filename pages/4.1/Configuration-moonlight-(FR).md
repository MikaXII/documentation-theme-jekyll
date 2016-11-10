---
layout: page
title: Configuration moonlight (FR)
wikiPageName: Configuration-moonlight-(FR)
menu: wiki
---

###Ce wiki n'est plus à jour, veuillez vous référer à la version anglaise : https://github.com/recalbox/recalbox-os/wiki/Setup-moonlight-%28EN%29

#**1 - Intro**

Ce tutoriel a pour but de paramétrer Moonlight sur la Recalbox

Vous avez besoin de : 
- La manette que vous utilisez
- Le fichier Moonlight.sh.hide 
- Un compte Steam 
- Une carte Nvidia compatible Gamestream 


#**2 - Paramétrage de Moonlight**

**_1-/ Si vous partez d'une fresh install:_**

Aller dans le /recalbox/roms/moonlight ou via ssh dans /recalbox/share/roms/moonlight
dans le répertoire vous devriez avoir : 
- Moonlight.sh.hide
- Moonlight.conf 

**_2-/ Si vous partez d'une beta plus ancienne que la Beta7:_**

Récupérez le fichier **Moonlight.sh.hide** ici => V2 Disponible plus bas  
Renommez **Moonlight.sh.hide** en **Moonlight.sh**  
Ouvrez avec notepad ++ ou autre le script Moonlight.sh  
Supprimez tout et remplacer par ce qui suit 
[Moonlight.sh.hide_v2](https://github.com/steak3/recalbox-buildroot/blob/unified/board/recalbox/share/roms/moonlight/Moonlight.sh.hide_v2)

Remplacez aussi **moonlight_ip=YOUR_IP_HERE** par **moonlight_ip=192.168.x.x** <== Correspond a l'adresse de votre PC

Maintenant sauvegardez votre fichier

Supprimez **Moonlight.conf** il risque de poser problème 


En SSH dans /recalbox/share/roms/moonlight lancez la commande suivante : 
- ./Moonlight.sh pair

Si tout ce passe bien vous aurez le message suivant :

   **Too many options: No such file or directory    
   Can't open configuration file: hosts/192.168.x.x.conf    
   Generating certificate...done    
   Please enter the following PIN on the target PC: 9958    
   Succesfully paired**

Vous aurez alors une fenêtre popup Nvidia où vous devrez rentrer votre pin    

Maintenant la configuration de la manette avec la commande suivante:    
- ./Moonlight.sh map    

Suivez les instructions a l'ecran.    

Rebootez la recalbox et profiter de moonlight.    


#**3 - ANNEXE** 

Vous avez aussi la possibilité de paramétrer l'affichage de votre Moonlight

720p en 30fps    
1080p en 30fps    

720p en 60fps    
1080p en 60fps    

Il faut pour cela modifiez la Ligne 23 du Moonlight.sh comme ceci (uniquement pour la V1 du script, pour la V2 les réglages sont au début du fichier):    

cmd="moonlight stream -remote **-1080 -60fps** -keydir ${moonlight_keydir} -mapping ${moonlight_mapping} ${moonlight_ip}" ;;    
et remplacez les paramètres **en gras** en fonction de la qualité souhaitée


