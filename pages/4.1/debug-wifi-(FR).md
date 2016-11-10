---
layout: page
title: debug wifi (FR)
wikiPageName: debug-wifi-(FR)
menu: wiki
---

comment se connecter en wifi ?

###Pré-requis 

* Vérifier que votre dongle wifi fait parti de la [liste de compatibilité](https://github.com/recalbox/recalbox-os/wiki/Compatibility-%28EN%29)
* Vérifier que votre clé wifi soit en WPA2, ne contienne pas de caractères spéciaux de préférence sinon voir plus bas   
* Vérifier que votre wifi est en mode découverte

###Configuration via emulationstation   

Brancher un clavier   
Se rendre dans le menu d emulationstation (Start)     
Options Réseau > Wifi sur On et entrer les informations SSID, Clé    
Redemarrer recalbox.   


###[Via recalbox.conf](https://github.com/recalbox/recalbox-os/wiki/recalbox.conf-%28FR%29)

* Connecter recalbox via le câble réseau en rj45
* Modifier le fichier recalbox.conf via winscp et notepad++ ou putty en utilisant la commande nano pour l'édition
* Activer le wifi 
* Supprimer les points virgules devant les deux lignes
* Enregistrer , fermer la session et redémarrer recalbox.

```
## Activate wifi (0,1)   
wifi.enabled=1   
## Wifi SSID (string)  
wifi.ssid=new ssid   
## Wifi KEY (string)   
wifi.key=new key   
```  
    
Si caractères spéciaux dans la clé wifi :   
Prenons par exemple 1a4a&9f5g8!41d   
il faut rajouter des anti-slash devant ces caractères dans le fichier recalbox.conf :
   
```
## Wifi KEY (string)   
wifi.key=1a4a\&9f5g8\!41d   
```   

### Dans recalbox directement   
        
Si vous n'avez pas la possibilité de connecter un câble réseau
Brancher un clavier   
Il faut sortir d emulationstation avec les touches suivantes: 

F4 suivi de alt+F2   
   
```
user : root      
mdp : recalboxroot     
```
   
puis éditer recalbox.conf avec la commande nano :

```
nano /recalbox/share/system/recalbox.conf
```

Enregistrer les modifications `cltr+x`  puis `Y` et rebooter.

Si aucune de ses astuces ne fonctionnent ou que votre dongle wifi ne fait pas parti de la liste de compatibilité   
merci de poster un [dmesg complet](https://github.com/recalbox/recalbox-os/wiki/D%C3%A9pannage-dmesg-output--%28FR%29) sur le forum en donnant les informations sur le modèle de votre dongle.   
