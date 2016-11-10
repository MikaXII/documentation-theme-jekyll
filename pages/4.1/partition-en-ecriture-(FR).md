---
layout: page
title: partition en ecriture (FR)
wikiPageName: partition-en-ecriture-(FR)
menu: wiki
---

Depuis la version 4.0.0, le système de partition a été modifié pour limiter la corruption de votre microsd.   
De ce fait, les partitions suivantes sont accessible uniquement en lecture :    


Vous pouvez être amené à modifier des fichiers dans 2 partitions de recalboxOS   
Partition de boot  `/boot`    
Partition du système  `/  `  

`mount -o remount,rw /boot`   
ou   
`mount -o remount,rw /`   
suivant les modifications que vous souhaitez apporter.  
   
Une fois les modifications réalisées, la partition sera remise en lecture au prochaine redémarrage du système.   


###Winscp en utilisant la console

Cliquer sur l'icone Console puis saisir la commande pour mettre la partition en écriture.   
<a href="http://www.zimagez.com/zimage/winscp01.php" target="_blank" title="Visionner l'image"><img src="http://www.zimagez.com/miniature/winscp01.png" alt="Visionner l'image" /></a>   
   



