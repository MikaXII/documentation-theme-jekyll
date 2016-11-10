---
layout: page
title: Configuration Retroachievements (FR)
wikiPageName: Configuration-Retroachievements-(FR)
menu: wiki
---

### **Challenge/Succès avec retroarch :**

Le site internet [retroachievements.org](http://www.retroachievements.org) propose des challenges/succès/trophées sur les plateformes tels NES, SNES, GB, GBC, GBA, Megadrive/Genenis, PCengine.  
Cette fonctionnalité de challenge a été ajouté il y a peu à retroarch.

### **Création d'un compte** :  
Vous devez [créer un compte](http://retroachievements.org/createaccount.php) sur le site [retroachievements.org](http://www.retroachivements.org).

Noter votre pseudonyme (Username) et votre mot de passe (password) dans un coin car ils vont servir à configurer retroachivements dans retroarch.

### **Activation du compte dans Emulationstation sous recalboxOS 4.0.0** 

Brancher votre clavier   
Ouvrir le menu d'emulationstation (bouton start)

Aller dans   

`Options Jeux> Options de Retroachievements`   

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/menu_es_retroachievements1.png)

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/menu_es_retroachievements2.png)   

`Retroachievements > ON`   
`Nom Utilisateur > mettre votre pseudonyme`    
`Mot de passe > votre mot de passe`  

### **Activation du compte manuellement sous recalboxOS 4.0.0** 

### **Editer le fichier recalbox.conf**

via ssh avec putty et le commande nano

`nano /recalbox/share/system/recalbox.conf`  
ou  
[winscp avec l'éditeur Notepad++](https://github.com/recalbox/recalbox-os/wiki/acces-via-WinSCP-%28FR%29)  

Ajout ses 3 lignes en remplaçant pseudonyme et motdepasse par ceux créer lors de votre inscription.  

`## Enable retroarchievements (0,1)`   
`## Set your www.retroachievements.org username/password`   
`global.retroachievements=1`   
`global.retroachievements.username=pseudonyme`   
`global.retroachievements.password=motdepasse`   

Sauvegarder votre recalbox.conf, rebooter votre recalbox.  


### **Configuration des émulateurs/core compatible avec retroachievements.**

Tous les cores libretro ne sont pas compatibles avec retroachievements. 

Voici la liste des emulateurs/core qui fonctionnent avec retroarch/retoachievements

Afficher le menu d'emulationstation ( bouton start)

Options jeux > advanced >  
* NES > EMULATEUR LIBRETRO > CORES QUICKNES / FCEUMM  
* SNES > EMULATEUR LIBRETRO > CORE SNES9X_NEXT  
* GB/GBC/GBA > DEFAULT 
* MEGADRIVE > DEFAULT (picodrive) 
* PCENGINE >DEFAULT (pour le moment ce n'est pas supporté par le core libretro)

Voici à quoi peut ressembler votre page sur retroachievements, ou vous trouvez les challenges à obtenir.

<a href="http://www.zimagez.com/zimage/retroachivement.php" target="_blank" title="Visionner l'image"><img src="http://www.zimagez.com/miniature/retroachivement.png" alt="Visionner l'image" /></a>


Pour visionner les challenges/trophées dans retroach , il suffit d'activer le menu retroarch (hotkey+B)  
Quick Menu > Achievements list

Vous trouverez la liste des jeux compatibles sur [cette page](http://retroachievements.org/gameList.php) 
