---
layout: page
title: Convertir iso track wav bin en bin cue (FR)
wikiPageName: Convertir-iso-track-wav-bin-en-bin-cue-(FR)
menu: wiki
---

Les jeux SegaCD ou PSX peuvent être sous différents formats : 

* iso+cue accompagné par des fichiers tracks au format wav, bin
* iso   
* bin+cue   
* ccd+img+sub   
* bin seul  

Exemple :    
```   
Wonder Dog (1993)(Sega)(PAL)(Track 01 of 21)[!].iso
Wonder Dog (1993)(Sega)(PAL)(Track 02 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 03 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 04 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 05 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 06 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 07 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 08 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 09 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 10 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 11 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 12 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 13 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 14 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 15 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 16 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 17 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 18 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 19 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 20 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 21 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)[!].cue   
    
Rockman 8 - Metal Heroes (Japan) (Track 1).bin   
Rockman 8 - Metal Heroes (Japan) (Track 2).bin   
Rockman 8 - Metal Heroes (Japan) (Track 3).bin   
Rockman 8 - Metal Heroes (Japan) (Track 4).bin   
Rockman 8 - Metal Heroes (Japan).cue  
     

```

Voici une technique pour convertir les iso+cue avec fichiers wav pour ceux qui ne veulent pas créer de dossiers pour contenir tous les fichiers d'un jeu.   
    

Cette technique est valable pour PSX, SEGACD.   
   

1. Télécharger <a href="http://eu-uk7.disk-tools.com/request?p=a6574b3d8017942f37e77e7611a397e3/DTLiteInstaller.exe">daemons tools Lite (gratuit)</a>   
Installer le logiciel.   
Choisir images disques puis cliquer le signe +   
Selectionner le fichier *.CUE   
Puis appuyer sur ENTER OU clic droit choisir monter pour créer le lecteur virtuel.   
   
<a href="http://www.zimagez.com/zimage/016019fe576eac96b7407f56bb49a612c9.php" target="_blank" title="monter une image"><img src="http://www.zimagez.com/miniature/016019fe576eac96b7407f56bb49a612c9.png" alt="monter une image" /></a>

2. Télécharger <a href="http://www.digital-digest.com/software/download.php?sid=470&amp;ssid=0&amp;did=1">Imgburn </a>
Técharger le fichier de langue en français en cliquant sur <a href="http://download.imgburn.com/translations/french.zip">le lien</a>   
Installer le logiciel   
Dézipper le fichier de langue et le placer dans le dossier Programes Files(x86)/imgburn/languages   
Exécuter le logiciel il sera en français.   
Choisir Create image from disc/Créer une image à partir du disque   
   
<a href="http://www.zimagez.com/zimage/024d744099a60824eb8efb29c454e97d53.php" target="_blank" title="create image from disque"><img src="http://www.zimagez.com/miniature/024d744099a60824eb8efb29c454e97d53.png" alt="create image from disque" /></a>    
   

Choisir le lecteur virtuel comme source(1)   
Choisir un dossier de destination pour la création du BIN et CUE. (2)   
Cliquer sur le bouton read/lire (3)  
Patientez.   
   

<a href="http://www.zimagez.com/zimage/0341d13848c6947322b21e7f6f0da45306.php" target="_blank" title="create"><img src="http://www.zimagez.com/miniature/0341d13848c6947322b21e7f6f0da45306.png" alt="create" /></a>   
   

Une fois la conversion terminée, tu peux démonter le lecteur virutel (clic droit sur l icone dans daemon tools puis démonter)   

### Astuce   

Créer une fichier cue manquant pour votre unique fichier bin

Exemple : r-type.bin   
    
Ouvrir notepad++   
La 1ère ligne doit contenir le BINARY   
     
`FILE "nom.bin" BINARY`   
   
La 2nde les pistes toujours en MODE2/2352 
      
`TRACK 01 MODE2/2352`   

La 3ème l index  01   
    
`INDEX 01 00:00:00`   
   
Vous obtenez quelques choses comme ceci qui devrait fonctionner.   
  
```
FILE "r-type.bin" BINARY
  TRACK 01 MODE2/2352
    INDEX 01 00:00:00
```
  
Enregistrer avec l'extension cue : `r-type.cue`   
Il reste plus qu'à transférer votre bin et votre cue.
