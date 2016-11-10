---
layout: page
title: Overscan settings (FR)
wikiPageName: Overscan-settings-(FR)
menu: wiki
---

L'option _overscan_ peut être activée si vous avez vous avez un contour noir sur votre image ou si celle-ci est rognée. Pour activer l'_overscan_, aller le menu de l'interface et réglez sur **on** l'option **Overscan** située dans le menu **OPTIONS INTERFACE**.  
Vous devez redémarrer votre rpi après avoir modifié cette option.  

Les réglages de l'overscan sont définis par Noobs lors de la première installation. S'ils ne correspondent pas à votre écran, vous pouvez modifier le réglage de chaque bordure dans votre fichier [[config.txt|Editer-le-fichier-config.txt-(FR)]] : 
``` 
disable_overscan=0
overscan_left=24
overscan_right=24
overscan_top=24
overscan_bottom=24
``` 
Ces valeurs définissent le nombre de pixels à ne pas prendre en compte pour l'affichage de l'image, à partir du bord de l'écran. **Augmenter** ces valeurs va _décaler_ l'image vers le centre, créant progressivement une bordure noire; **diminuer** ces valeurs va _rapporcher_ l'image vers le bord de l'écran, diminuant la bordure noire présente entre le bords de l'écran et l'image.

Si ces réglages d'overscan ne s'appliquent pas dans certains émulateurs ou sur emulationstation rajoutez ceci: 
``` 
overscan_scale=1
``` 
