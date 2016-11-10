---
layout: page
title: Mausberry Switch Power On off (FR)
wikiPageName: Mausberry-Switch-Power-On-off-(FR)
menu: wiki
---

# Introduction

Les circuits de Mausberry permettent de gérer l'allumage et l'extinction du raspberry pi grâce à un interrupteur. Ce type de circuit peut être utilisé pour utiliser l'interrupteur on/off d'une NES ainsi que son bouton reset par exemple.

**Remarques : **
Ce wiki est dédié à Recalbox V4 sur un Raspberry Pi 2 et 3

**ATTENTION ! **

* Si vous utiliser une version plus récente que le v4.0.0 beta 3 suivre le tuto V4B3.
* Si vous utiliser une version plus ancienne que le v4.0.0 beta 3 suivre le tuto V4B2.

# Tuto V4B3

## Branchements et câblage

Au niveau branchement sur le Pi, il faut utiliser les ports GPIO 23 et 24 (pin16 et 18). Le Mausberry est opérationnel avec OUT = GPIO23 / IN = GPIO24. Vous trouverez en Annexe le schéma correspondant.

## Procédure

### Prérequis

1. Votre Raspberry Pi doit être connecté au réseau
2. Vous devez connaitre l'adresse IP de votre Raspberry Pi. Celle-ci est accessible depuis le menu de Recalbox. L'adresse IP doit ressembler à : `192.168.0.49`
Il est également possible de suivre ce lien : [Know IP reseau (FR)](https://github.com/recalbox/recalbox-os/wiki/Know-IP-reseau-%28FR%29)

### Etapes
1. Connectez-vous à l'interface web de Recalbox depuis votre navigateur > ex : `http://192.168.0.49` 
2. Dirigez-vous vers `Read and edit the Recalbox Configuration file`
3. Dans la section : `A - System Options` décommentez pour obtenir : 

`# ------------ A - System Options ----------- #`
`#    Uncomment the system.power.switch you use`
`system.power.switch=MAUSBERRY           # http://mausberry-circuits.myshopify.com/pages/setup`

4. sauvegardez

# Tuto V4B2

## Branchements et câblage

Au niveau branchement sur le Pi, il faut utiliser les ports GPIO 20 et 21. Le Mausberry est opérationnel avec OUT = GPIO20 / IN = GPIO21. Vous trouverez en Annexe le schéma correspondant.

## Procédure

### Prérequis

1. Votre Raspberry Pi doit être connecté au réseau
2. Vous devez connaitre l'adresse IP de votre Raspberry Pi. Celle-ci est accessible depuis le menu de Recalbox. L'adresse IP doit ressembler à : `192.168.0.49`
Il est également possible de suivre ce lien : [Know IP reseau (FR)](https://github.com/recalbox/recalbox-os/wiki/Know-IP-reseau-%28FR%29)
3. Vous devez pouvoir vous connecter en SSH à votre Recalbox. Sous windows vous pouvez utiliser des logiciels comme [Putty](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html) ou [Kitty](http://www.9bis.net/kitty/?page=Download)

### Etapes

1. Connectez-vous en SSH sur votre Recalbox
2. Positionnez vous dans le répertoire **system** > `cd /recalbox/share/system/`
3. Créez le fichier **setup.sh** > `nano setup.sh`
4. Copiez le contenu de l'annexe **setup.sh**
5. Sauvegardez > `Ctrl + X` 
6. Créez le fichier **S99maus** > `nano S99maus`
7. Copiez le contenu de l'annexe **S99maus**
8. Sauvegardez > `Ctrl + X` 
9. Il faut passer temporairement le système qui est en read-only en read/write. Pour se faire exécuter la commande : `mount -o remount, rw /` Le système redeviendra read-only au prochain reboot
10. Lancez le script setup.sh > `bash setup.sh`
11. Vérifiez la présence du nouveau script > `nano /recalbox/scripts/mausberry.sh` 
12. Copiez le fichier S99maus vers le répertoire /etc/init.d/ > `cp /recalbox/share/system/S99maus /etc/init.d/`
13. Donnez les droits d’exécution au script > `chmod 775 /etc/init.d/S99maus`
14. Lancez le script > `/etc/init.d/S99maus start`
15. Vous obtiendrez un message d'erreur comme celui-ci, mais le Mausberry sera fonctionnel :  bad -o argument ‘command'




# Annexes

## Branchements et câblage
![](http://www.windtopik.fr/wp-content/uploads/2014/11/RPI-GPIO-N-.png)

## Script : setup.sh
```
echo '#!/bin/bash

#this is the GPIO pin connected to the lead on switch labeled OUT
GPIOpin1=20

#this is the GPIO pin connected to the lead on switch labeled IN
GPIOpin2=21

echo "$GPIOpin1" > /sys/class/gpio/export
echo "in" > /sys/class/gpio/gpio$GPIOpin1/direction
echo "$GPIOpin2" > /sys/class/gpio/export
echo "out" > /sys/class/gpio/gpio$GPIOpin2/direction
echo "1" > /sys/class/gpio/gpio$GPIOpin2/value
while [ 1 = 1 ]; do
power=$(cat /sys/class/gpio/gpio$GPIOpin1/value)
if [ $power = 0 ]; then
sleep 1
else
poweroff
fi
done' > /recalbox/scripts/mausberry.sh
chmod 777 /recalbox/scripts/mausberry.sh
```

## Script : S99maus
```
#!/bin/bash
### BEGIN INIT INFO
# Provides: mausberry.sh
# Required-Start: $network $local_fs $remote_fs
# Required-Stop: $network $local_fs $remote_fs
# Default-Start: 2 3 4 5
# Default-Stop: 0 1 6
# Short-Description: switch mausberry init script.
# Description: Starts and stops SwitchDaemon service.
### END INIT INFO

#VAR
RUN="/recalbox/scripts/mausberry.sh"
BTD_PID=$(ps -eo pid,command | grep "/bin/bash $RUN" | grep -v grep | awk '{print $1}')

serviceStatus() {
   if [ ! -z "$BTD_PID" ]; then
      echo -e '33[0mservice mausberry.sh ['$BTD_PID'] [33[33;32m OK 33[0m]'
   else
      echo -e '33[0mservice mausberry.sh [33[33;31m KO 33[0m]'
   fi
}

# Carry out specific functions when asked to by the system
case "$1" in
   start)
      echo "Starting script $RUN ..."
      if [ -z "$BTD_PID" ]; then
         nice -n 19 $RUN&

         if [ $? -eq 0 ]; then
            echo -e "33[0mscript $RUN [33[33;32m STARTED 33[0m]"
         fi
      else
         echo "script $RUN already started ['$BTD_PID']!"
      fi
      #serviceStatus
   ;;
   stop)
      echo "Stopping script $RUN ..."
      if [ ! -z "$BTD_PID" ]; then
         kill $BTD_PID

         if [ $? -eq 0 ]; then
            echo -e "33[0mscript $RUN [33[33;31m STOPPED 33[0m]"
         fi
      fi
      #serviceStatus
   ;;
   status)
      serviceStatus
   ;;
   *)
      echo "Usage: /etc/init.d/S99maus {start | stop | status}"
      exit 1
   ;;
esac

exit 0
```
