---
layout: page
title: Remapping controller FBA
wikiPageName: Remapping-controller-FBA
menu: wiki
---

Only for 3.2.11 and previous revision.

4 boutons on X Y B et A 

Si vous souhaitez changer le mapping des boutons pour FBA il faut éditer ce fichier 

`recalbox/scripts/generateEmuConfigs/createFBAConfig.sh`

Modifier cette partie:  




        fbabtn['a']='Y'

        fbabtn['b']='X'

        fbabtn['x']='B'

        fbabtn['y']='A'

        fbabtn['pageup']='L'

        fbabtn['pagedown']='R'
