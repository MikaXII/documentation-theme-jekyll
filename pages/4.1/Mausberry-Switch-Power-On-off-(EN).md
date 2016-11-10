---
layout: page
title: Mausberry Switch Power On off (EN)
wikiPageName: Mausberry-Switch-Power-On-off-(EN)
menu: wiki
---

# Introduction

Mausberry circuits manage Raspberry Pi on/off switching with a switch. This type of circuit can be used to use the on/off switch of a NES and its reset button for example.

**Note**
This wiki is dedicated to Recalbox V4 on a Raspberry Pi 2 and 3

**WARNING ! **

* If you use a newer version than v4.0.0 beta 3 follow tuto V4B3.
* If you use an older version than v4.0.0 beta 3 follow tuto V4B2.

# Tuto V4B3

## Connections and wiring

For connections on the Pi, use the GPIO ports 23 and 24 (pin 16 and 18). The Mausberry is operational with GPIO23 = OUT / IN = GPIO24 . You will find in Annex the figure.

## Procedure

### Prerequisites

1. Your Raspberry Pi needs to be connected to the network
2. You must know the IP address of your Raspberry Pi. This one is accessible from Recalbox menu. The IP address should look like: `192.168.0.49`
You can also follow this link: [Know IP network (EN)] (https://github.com/recalbox/recalbox-os/wiki/Identify-your-recalbox%27s-IP-on-your-network-%28EN%29)

### Steps

1. Go on Recalbox web interface from your internet browser > ex : `http://192.168.0.49` 
2. click on `Read and edit the Recalbox Configuration file`
3. In section : `A - System Options` uncomment to obtain : 

`# ------------ A - System Options ----------- #`
`#    Uncomment the system.power.switch you use`
`system.power.switch=MAUSBERRY           # http://mausberry-circuits.myshopify.com/pages/setup`

4. sauve

# Tuto V4B2

## Connections and wiring

For connections on the Pi, use the GPIO ports 20 and 21. The Mausberry is operational with GPIO20 = OUT / IN = GPIO21 . You will find in Annex the figure.

## Procedure

### Prerequisites

1. Your Raspberry Pi needs to be connected to the network
2. You must know the IP address of your Raspberry Pi. This one is accessible from Recalbox menu. The IP address should look like: `192.168.0.49`
You can also follow this link: [Know IP network (EN)] (https://github.com/recalbox/recalbox-os/wiki/Identify-your-recalbox%27s-IP-on-your-network-%28EN%29)
3. You must be able to connect through SSH into your Recalbox. On Windows you can use software such as [Putty](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html) or [Kitty](http://www.9bis.net/kitty/?page=Download)

## Steps

1. Login through SSH on your Recalbox
2. Go to the **system** directory > `cd /recalbox/share/system/`
3. Create a **setup.sh** file > `nano setup.sh`
4. Copy the contents of the **setup.sh** annex 
5. Save your work > `Ctrl + X` 
6. Create a **S99maus** file > `nano S99maus`
7. Copy the contents of the **setup.sh** annex > `nano S99maus`
8. Save your work > `Ctrl + X` 
9. You have to temporaliy switch the system that is in read-only mode in read/write mode. To perform this, execute the following command : `mount -o remount, rw /` The system will return in read-only mode at the next reboot
10. Run the setup.sh script > `bash setup.sh`
11. Look for the new script > `nano /recalbox/scripts/mausberry.sh`
12. Copy the S99maus file to the directory /etc/init.d/ > `cp /recalbox/share/system/S99maus /etc/init.d/`
13. Give execution rights to the script > `chmod 775 /etc/init.d/S99maus`
14. Run the script > `/etc/init.d/S99maus start`
15. You will get an error message like this, but the Mausberry will be functional : bad -o argument ‘command'

# Annex

## Connections and wiring
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
