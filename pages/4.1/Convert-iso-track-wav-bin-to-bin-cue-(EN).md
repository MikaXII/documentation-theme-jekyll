---
layout: page
title: Convert iso track wav bin to bin cue (EN)
wikiPageName: Convert-iso-track-wav-bin-to-bin-cue-(EN)
menu: wiki
---

SegaCD or PSX games may be with differents extensions :   
    
* iso+cue a with tracks files like  wav, bin extensions.
* iso   
* bin+cue   
* ccd+img+sub   
* bin only 

Example :    
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

Here is a technique to convert iso + cue with wav files for those who do not want to create folders to hold all the files in one game.      
    

this technique is valid for PSX, SEGACD.   
   

1. Download <a href="http://eu-uk7.disk-tools.com/request?p=a6574b3d8017942f37e77e7611a397e3/DTLiteInstaller.exe">daemons tools Lite (freeware)</a>   
Install software.   
Choose  image disk and clic + sign  
Choose *.CUE file.   
And but ENTER button or right clic choose mount to create virtual drive.
   
<a href="http://www.zimagez.com/zimage/016019fe576eac96b7407f56bb49a612c9.php" target="_blank" title="monter une image"><img src="http://www.zimagez.com/miniature/016019fe576eac96b7407f56bb49a612c9.png" alt="monter une image" /></a>

2. Download <a href="http://www.digital-digest.com/software/download.php?sid=470&amp;ssid=0&amp;did=1">Imgburn </a>   
Install software.    
Choose Create image from disc   
   
<a href="http://www.zimagez.com/zimage/024d744099a60824eb8efb29c454e97d53.php" target="_blank" title="create image from disque"><img src="http://www.zimagez.com/miniature/024d744099a60824eb8efb29c454e97d53.png" alt="create image from disque" /></a>    
   

Choose virtual drive as source(1)   
Choose a destination folder for the creation of BIN et CUE. (2)   
Click on  read button (3)  
Wait  
   

<a href="http://www.zimagez.com/zimage/0341d13848c6947322b21e7f6f0da45306.php" target="_blank" title="create"><img src="http://www.zimagez.com/miniature/0341d13848c6947322b21e7f6f0da45306.png" alt="create" /></a>   
   

After conversion finished, you can unmount the drive virutel (right click on the icon in daemon tools and then unmount) 

### Astuce   

Create a missing cue file for bin file only.

Exemple : r-type.bin   
    
Open notepad++   
La 1st line must have  BINARY   
     
`FILE "nom.bin" BINARY`   
   
The 2nde  tracks always in MODE2/2352 
      
`TRACK 01 MODE2/2352`   

La 3rd index  01 line   
    
`INDEX 01 00:00:00`   
   
You get a few things like this should work. 
  
```
FILE "r-type.bin" BINARY
  TRACK 01 MODE2/2352
    INDEX 01 00:00:00
```
  
Save cue file as same name of bin file : `r-type.cue`   

