---
layout: page
title: Check md5 checksum (FR)
wikiPageName: Check-md5-checksum-(FR)
menu: wiki
---

Pour vérifier la signature d'un fichier autrement dit son MD5 checksum.   

###Sous Windows :     
    

Téléchargez <a href="http://www.winmd5.com/download/winmd5free.zip">winmd5free</a>
Installez-le puis   
cliquer sur le bouton browse pour sélectionner votre fichier   
Entrer le checksum recommandé sur cette page (<a href="https://github.com/digitalLumberjack/recalbox-os/wiki/Ajoutez-des-bios-%28FR%29">Voir ajouter des bios</a>) en le mettant dans la zone Original file MD5 puis cliquer sur Verify   


EXEMPLE :  **gba_bios.bin**   
   
<a href="http://www.zimagez.com/zimage/winmd5freev1200.php" target="_blank" title="Visionner l'image"><img src="http://www.zimagez.com/miniature/winmd5freev1200.png" alt="Visionner l'image" /></a>   





### Linux / MacOSX : 
Utilisez la commande `md5sum`.
Dans terminal, pour vérifier le checksum des fichiers bios, utilisez la commande shasum suivie du nom du fichier.
