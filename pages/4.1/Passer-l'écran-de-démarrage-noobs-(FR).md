---
layout: page
title: Passer l'écran de démarrage noobs (FR)
wikiPageName: Passer-l'écran-de-démarrage-noobs-(FR)
menu: wiki
---

Vous pouvez gagner quelques secondes au démarrage en forçant noob pour démarrer directement sur la partition `boot`.

Mettez votre carte SD dans votre ordinateur personnel. Ouvrez la partition `RECOVERY` et créer un fichier nommé `autoboot.txt`

Editez le fichier et ajoutez la ligne suivante : 

- Avec une recalbox en version 3.3.0
```
boot_partition=5
```

- Avec une recalbox en version 4.0.0
```
boot_partition=6
```

Cela évitera l'écran de démarrage noobs et vous booterez directement sur recalboxOS.   
Si vous voulez réactiver l'écran de noobs, il suffit de supprimer le fichier `autoboot.txt` 
