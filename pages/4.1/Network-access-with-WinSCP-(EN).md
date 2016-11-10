---
layout: page
title: Network access with WinSCP (EN)
wikiPageName: Network-access-with-WinSCP-(EN)
menu: wiki
---

### Prerequisites
* Be sure your recalbox is running and connected to your local network via an ethernet cable or a wifi dongle.

> You are not sure and you have an Internet access? It is simple, go to the recalbox menu then choose "Update the system". If a pop up display the message "an update is available" or "no update available" then your recalbox have an access to the Internet and so, to your local network. If the message "please plug a network cable" is displayed, either you have not access to the Internet, that is not a problem, or a problem with your routeur configuration, a faulty cable or a faulty wifi dongle.

* Download and install WinSCP
 - [Windows](http://winscp.net/)
 - [Mac OSX](http://www.mediafire.com/download/w5d794zbnwv3dkj/WinSCP.zip) _(:warning: Be careful, this is not an offical version. It is a port of the 2011 windows version for OSX. The commercial software [rbrowser](http://www.rbrowser.com/) is an alternate solution)_

* Optional : Know your recalbox ip adress. Follow [[Identify your recalbox's IP on your network|Identify your recalbox's IP on your network (EN)]] if you don't know how to do it.

### Configuration 
* Launch 'WinSCP'
* Click on 'New site'
* Fill the following informations :
 - File protocol 'SCP'
 - Hostname 'recalbox' or the ip adress you have found previously _(the configuration must be modified  everytime you reboot the recalbox if you have entered the ip adress)_
 - Port number '22'
 - Login 'root'
 - Password 'recalboxroot'
 - Save the changes
 - Fill the following informations : 
 - Save the session with : 'Recalbox' for example
 - Check the box "Save the password (not recommended) then click 'OK'
* Your software is now configured

* Go to your favorites (left column)  and double click on recalbox
* Pop up open, telling that the connexion is in progress
* Another pop up can occur asking you to 'Continue connecting to an unknown server and add its host key to a cache?' then click on 'Yes'
* You are connected

*Go to "Preferences" (CTRL+ALT+P) then 'Panels' and check the box 'Show hidden files'. This will be usefull to access to the folder .emulationstation, to modify the theme for example.

### Usage

Using WinSCP is intuitive . By default, you will find your computer to the left and your recalbox to the right.
Some tips : 
* To go back to the upper folder or to the root of your recalbox, you only have to click on the first folder with a symbol back up and identified as '...'
* You can deposit folders with a simple drag and drop to the right column or from the righ column.
* You can change file permission with a right click on it then "Properties"
* Find the path to the usefull files and folders in [[FAQ|FAQ]]
