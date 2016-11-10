---
layout: page
title: Manual IP settings (EN)
wikiPageName: Manual-IP-settings-(EN)
menu: wiki
---

In order to select a fixed ip for your recalbox, you will have to edit the file `/etc/network/interfaces`. 
  
[Get a root access](https://github.com/digitalLumberjack/recalbox-os/wiki/Root-access-on-terminal-%28EN%29) and edit the file with : 
`nano /etc/network/interfaces`

For a permanently solution you must edit the interfaces.base file. And before you can edit this file you must remount the file system as rw. So try this commands:
`mount -o remount,rw /`
`nano /etc/network/interfaces.base`


Search the line containing the interface you want to modify (ethX for ethernet, wlanX for wifi) : 
```
auto eth0
iface eth0 inet dhcp
```

So let us modify eth0 ip.  
Replace with the static ip settings : 
```
auto eth0
iface eth0 inet static
     address 192.168.1.10
     network 192.168.1.0
     netmask 255.255.255.0
     broadcast 192.168.1.255
     gateway 192.168.1.254
```

By switching to a static IP address, you will lose the configuration of your DNS server(s) in the process.
In order to get name resolution working, you will have to create a file names /etc/resolv.conf. By default, this files points to an auto-generated file located at /tmp/resolv.conf, so in order to do it once and for all, run the following commands:

```
rm /etc/revolv.conf
nano /etc/revolv.conf
```

Enter the following lines, which corresponds to DNS servers of the OpenDNS project:
```
nameserver 208.67.222.222
nameserver 208.67.220.220
```

Save the file.

Now reload the settings with : `ifdown eth0 && ifup eth0`

THESE EDITS WILL BE OVERWRITTEN WITH EACH NEW UPDATE - You will have to repeat these tasks after each update.
