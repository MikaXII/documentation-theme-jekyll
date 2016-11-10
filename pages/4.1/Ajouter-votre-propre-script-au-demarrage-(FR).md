---
layout: page
title: Ajouter votre propre script au demarrage (FR)
wikiPageName: Ajouter-votre-propre-script-au-demarrage-(FR)
menu: wiki
---

Vous voulez ajouter votre propre script de démarrage, voici se que vous devez savoir:
Tous les scripts de démarrage sont placés dans `/etc/init.d/`. Ils sont executés du premier au dernier par ordre alphabétique. Donc, `S31emulationstation` sera executé avant `S99yourscript`.

La méthode Start sera executé au démarrage, et la méthode Stop à l'extinction.

Suivez ces instructions pour créer votre propre script de démarrage :
- obtenez un [[accès root|Root-access-on-terminal-(EN)]] dans votre terminal 
- naviguez dans le répertoire `/etc/init.d` avec la commande
```
cd /etc/init.d
```
- executez `ls` pour voir les scripts présent
- copiez S02serial pour en faire votre nouveau script :
```
cp S02serial S99myscript
```
- editez le script avec `vi` ou `nano`
- redémarrer, ou lancez votre script avec
```
/etc/init.d/S99myscript start
```
