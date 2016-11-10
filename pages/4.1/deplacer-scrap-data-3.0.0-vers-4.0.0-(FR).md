---
layout: page
title: deplacer scrap data 3.0.0 vers 4.0.0 (FR)
wikiPageName: deplacer-scrap-data-3.0.0-vers-4.0.0-(FR)
menu: wiki
---

La structure des dossiers de scrap a été modifié dans la version 4.0.0 de recalboxOS.     
    
Si vous souhaitez migrer vos données de scrap (gamelist.xml et downloaded_images)      
voici comment procéder ?     

En version 3.3.0, les données de scrap étaient placés dans ses différents dossiers :    

```
/root/.emulationstation/gamelists/dossier_emulateur   
/root/.emulationstation/downloaded_images/dossier_emulateur  
```   
    
Dans la version 4.0.0 les dossiers de scrap ont été placés dans le dossier de chaques emulateurs  
      
`/recalbox/share/roms/dossier_emulateur`   
   
ainsi on retrouvera cette structure :     
   
`/recalbox/share/roms/dossier_emulateur/gamelist.xml`     
`/recalbox/share/roms/dossier_emulateur/images`     
    


**Exemple SNES GAMELIST.XML de recalbox 3.0.0***

```
<game id="1046" source="theGamesDB.net">    
          <path>./ActRaiser (USA).zip</path>   
          <name>ActRaiser (USA)</name>    
          <desc>During game play the player fills the role of the 'Master', a powerful being awakened from a long sleep to find the civilizations of his former world in shambles. Through a combination of side-scrolling action stages and overhead-view &#034;god&#034; simulation mode the Master slowly rebuilds his world and regains his followers and powers. He is not referred to as a deity of any kind, and it is stated in the manual that he is mortal, and this is the reason he hid away from the demons he was fighting when he had just enough power to seal himself away and wait them out.</desc>    
          <image>~/.emulationstation/downloaded_images/snes/ActRaiser (USA)-image.jpg</image>   
          <rating>0.6</rating>   
          <releasedate>19911101T000000</releasedate>  
          <developer>Quintet</developer>   
          <publisher>Enix</publisher> 
          <genre>Action</genre>   
          <players>1</players>
```   



chemin du dossier images pour la snes : 
`<image>~/.emulationstation/downloaded_images/snes/ActRaiser (USA)-image.jpg</image>`

Dans recalbox v4.0.0   
le chemin du dossier devient :    
   
    `<image>./images/ActRaiser (USA)-image.jpg</image>`    
ou       
`<image>./downloaded_images/ActRaiser (USA)-image.jpg</image>`   
comme vous voulez.   
   
   

``` 
<game id="1046" source="theGamesDB.net">    
          <path>./ActRaiser (USA).zip</path>   
          <name>ActRaiser (USA)</name>   
          <desc>During game play the player fills the role of the 'Master', a powerful being awakened from a long sleep to find the civilizations of his former world in shambles. Through a combination of side-scrolling action stages and overhead-view &#034;god&#034; simulation mode the Master slowly rebuilds his world and regains his followers and powers. He is not referred to as a deity of any kind, and it is stated in the manual that he is mortal, and this is the reason he hid away from the demons he was fighting when he had just enough power to seal himself away and wait them out.</desc>
          <image>./images/ActRaiser (USA)-image.jpg</image>   
          <rating>0.6</rating>  
          <releasedate>19911101T000000</releasedate>   
          <developer>Quintet</developer>   
          <publisher>Enix</publisher>   
          <genre>Action</genre>  
          <players>1</players>
```


```
/recalbox/share/roms/snes/gamelist.xml   
/recalbox/share/roms/snes/images
```   
ou
`/recalbox/share/roms/snes/downloaded_images`   

