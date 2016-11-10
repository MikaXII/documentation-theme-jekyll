---
layout: page
title: Recalbox support  (FR)
wikiPageName: Recalbox-support--(FR)
menu: wiki
---

Dans la version 4.0.0 de recalboxOS, un script nommé recalbox-support.sh a été ajouté afin d'aider les développeurs sur les problèmes que vous pouvez rencontrer avec vos périphériques.

recalbox-support.sh donne les informations suivantes sur  : 

* joytstick   
* kodi   
* lirc   
* system (lsmod, lsusb, tv service, es_settings, recalbox.conf, recalbox.log,config, df, etc...)  

Si vous avez correctement [configurer winscp](https://github.com/recalbox/recalbox-os/wiki/acces-via-WinSCP-%28FR%29)   
Connectez-vous en ssh via putty via winscp  , executer cette commande :    


`/recalbox/scripts/recalbox-support.sh`   

le chemin d'accès de l'archive vous sera indiqué dans la fenêtre  :   

<a href="http://www.zimagez.com/zimage/puttyviawinscp.php" target="_blank" title="Visionner l'image"><img src="http://www.zimagez.com/miniature/puttyviawinscp.png" alt="Visionner l'image" /></a>


Attention le mode console de winscp , donnera un message d'erreur sur lsmod, il faut impérativement utiliser putty.    

<a href="http://www.zimagez.com/zimage/winscp03.php" target="_blank" title="Visionner l'image"><img src="http://www.zimagez.com/miniature/winscp03.png" alt="Visionner l'image" /></a>    

Récupérer l'archive sur votre PC puis l'uploader vers un hébergeur de fichier :   

* [dl.free.fr](http://dl.free.fr/)
* [zippyshare](http://www.zippyshare.com/)   

Poste le lien dans votre sujet en cours sur le forum ou dans l'issue que vous avez ouverte.   
