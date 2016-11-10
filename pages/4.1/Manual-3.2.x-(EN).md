---
layout: page
title: Manual 3.2.x (EN)
wikiPageName: Manual-3.2.x-(EN)
menu: wiki
---

# recalbox 3.2.0
## Manual v1

![](http://blog.recalbox.com/wp-content/uploads/2015/01/retrobox-etiquette.png)

http://www.recalbox.fr

- I - [First use](#first-use)
- II - Configuration
 - A - Controllers
   - 1 - PS3 controllers
    - 2 - XBox 360 controllers
    - 3 - Add an usb controller
    - 4 - Buttons mapping
    - 5 - Keyboard mapping
    - 6 - GPIO controllers
    - 7 - Configure Retroarch
 - B - System settings
 - C - Sound settings
 - D - Network settings
- III - EmulationStation
- IV - During the game
 - A - Saves
 - B - Special commands
- V - Updates
- VI - Network features
 - A - Add your games
 - B - Scummvm Games
 - C - Screenshots
 - D - Save your saves
- VII - Kodi Media Center
- VIII - Troubleshooting
 - A - Controllers
 - B - Other
 - C - Hard reset
 - D - Root Access
- IX - recalbox.conf


### Introduction
The recalbox is a system that will allow you to play retro games easily.

It runs on a mini computer called the RaspberryPi, and uses a batch of optimized emulators.

### <a name='first-use'></a>I - First use
The necessary package :
- A raspberry PI 1 or 2
- 8GB or more SD/microSD card
- HDMI cable
- a micro USB power cable > 1.5AMP
- USB or PS3 controller

After the [[Installation|Installation-(EN)]], the first thing you have to do is to connect the recalbox to the TV with the HDMI cable.

To power on the recalbox, just plug the micro USB power cable in.

If you want to configure directly an USB controller, plug in a USB keyboard and see [Add an usb controller](#d---add-an-usb-controller)

To shut down the system : push on the start button and choose “QUIT” and “SHUTDOWN SYSTEM”.  
You can then unplug the power cable.

### II - Configuration

#### A - Controllers
PS3 dualshock and Xbox controllers are supported wireless.

##### 1 - PS3 controllers
You must have a bluetooth dongle to use a PS3 wireless controller.
You must charge controllers directly on the usb power.  
Plug the controller on the recalbox only to associate your controller with your recalbox.  
In order to associate a PS3 controller, plug the controller on the recalbox and wait 10 seconds. You can now unplug the controller and press the Home button.


##### 2 - XBox 360 controllers
If you have a XBox 360 wired or wireless, activate the [xboxdrv in recalbox.conf](https://github.com/digitalLumberjack/recalbox-os/wiki/recalbox.conf-%28EN%29) to have the best support possible.

Then reboot with your controller plugged, and play.

You must have a wireless adapter to play with XBOX 360 wireless controllers.

##### 3 - Add an usb controller
You can add USB controllers on the recalbox.

Most of models are compatible.

After you plug your usb controller, press START with an already configured controller (or ENTER on the keyboard) and select "Configure Inputs".

Then follow instructions. **If you don't have a button you can use as the HotKey, map it to Select.**

Buttons names are based on the Super Nintendo controller :  
![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/snes-controller.jpg)

 
Back on the configuration screen, you can assign the controller to a player. Your controller is now configured !


##### 4 - Buttons mapping

For 6 buttons controllers (snes, psx, arcade etc) the buttons are mapped to corresponding buttons on the original controller.   
For 2 buttons controllers (nes, pcengine, gameboy etc) the mapped buttons are B and A.

##### 5 - Keyboard mapping
If you totally failed at the controller configuration, you can wire an usb keyboard to the recalbox.
Enter is START, Space is SELECT, Q is BACK, S is OK

##### 6 - GPIO controllers
You can connect your arcade joysticks and buttons directly on raspberry GPIOs. Activate the GPIO controllers with the [[recalbox.conf|recalbox.conf-(EN)]] file.

![](https://github.com/DigitalLumberjack/mk_arcade_joystick_rpi/raw/master/wiki/images/mk_joystick_arcade_GPIOsb+.png)

More info on https://github.com/DigitalLumberjack/mk_arcade_joystick_rpi

Marqs DB9 and gamecon drivers are supported too. See [[recalbox.conf|recalbox.conf-(EN)]]

##### 7 - Configure Retroarch
You can access retroarch configuration menu with *Hotkey* + *B*
If you want to configure retroarch and save the config, you can select the "Save Settings on Exit" in the retroarch menu. After that, all configuration you make in rgui will be saved.

#### B - System Settings
By pressing start and selecting the first entry, you will be able to change some system settings.  
You can set the **overscan** *on* and *off*, to avoid black borders or image loss on some tv.  
You can set the **smooth** setting to *on* or *off*. All games are impacted.  

You can change the overclock of your RPi1. The overclock speed order is *NONE* < *HIGH* < *TURBO* < *EXTREM*.  Extrem may void your warranty but is **the only one** that will give you really good perf on all emulators.  
You can select the ratio of games (*16/9* or *4/3* or *auto*).


#### C - Sound settings
You can select the **System volume** and the **Output Device** (*auto*, *jack* or *hdmi*) in the sound settings. Select jack to force analog output.  
You can also disable background sounds in EmulationStation.

#### D - Network settings
You can active the wifi and set your network configuration in the network settings.  
Type the SSID of your network and the network key with a keyboard.  
Once you validate, the wifi is activated.  
A known bug is you cannot enter all the character you need for the SSID or the Key. 
Configure dictly your wifi from [[recalbox.conf|recalbox.conf-(EN)]]

### III - EmulationStation

When you start the recalbox system, the frontend emulationstation shows up.
You can select your systems and launch your games from here.

The first screen is the system screen : 

![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/emulationstation.jpg)


It shows all systems available.

When you select a system with A, the screen change and show all available games.

When the game is running, go to the section *During the game* to see how you can go back to the frontend.


**Frontend commands :**

A → Select  
B → Back  
Y → Switch Favorite  
X → Launch Kodi  
Start → Menu  
Select → Options  
R → Next Page   
L → Previous Page  


### IV - During the game

#### A - Saves 
Emulators allow save state. A saved state is a quick save of the game, and allows you to reload the game at this point.

With save states, you will never have to seek for a savepoint again !

You can save more than one state per game if you change the save slot.


#### B - Special commands
When you are in game, special commands are available.  

Press **Hotkey** on the controller and one of the following: 

Y → Save State  
X → Load State  
Start → Quit  
B → Menu  
Up → Save Slot -1  
Down → Save Slot +1  
L1 → Screenshot  
Right → Speedup game  


In FBA and Mame, press Select to add a credit.
In Mame, if you Hotkey is Select, you will have to quit with R1 + Start (in order to have select as coin)

### V - Updates
The recalbox update can be done in the frontend menu. Configure the wifi or plug an ethernet cable on the recalbox, press Start and select "UPDATE" with A.

After the update, the system will reboot.


### VI - Network features
If you configured the wifi or plugged an ethernet cable on the recalbox, it shares files on your local network. On your computer, got to Network on Windows explorer, and select the recalbox :

![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/partagereseau-recalbox.jpg)



You can access all recalbox shared folders :

![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/partagereseau.jpg)



#### A - Add your games
Just copy the files in the corresponding folder. You can use either *.zip* files or uncompressed roms.

Don’t hesitate to share your favorite games in the recalbox forum !
http://blog.recalbox.fr/forums/

#### B - Scummvm games
When you add a Scummvm game, it must be an uncompressed folder. In this folder, you will have to add a single file, named [gameshortname].scummvm

You can find shortnames for all supported games at http://scummvm.org/compatibility/

For example, if you copied the folder "Broken Sword 1" in the scummvm directory. In this folder create a file nammed sword1.scummvm

Your game will appear in the frontend, and you will be able to change it's metadata if you want to display a good name. 

#### C - Screenshots
Press Hotkey + L1 in emulators to take a screenshot. The png file is saved in the "screenshots" directory, you can access on the network.  
Share your best screenshots with us on http://blog.recalbox.com/forums/

#### D - Save your saves
The *sauvegardes* folder share contains all saves and saved states. You can copy all the files if you want to secure them.

### VII - Kodi Media Center
By pressing X button on your controller, you can launch Kodi Media Center, aka XBMC. You can also access Kodi by pressing start and launching it from the menu.

To quit Kodi, select "QUIT" in the program, and you will come back to recalboxOS.

### VIII - Troubleshooting

#### A - Controllers :

- The PS3 controller is blinking but does not associate   
Plug a controller on the recalbox and wait 10 seconds. You can now unplug the controller and press the Home button.

- The PS3 controller seems dead  
You must reset the controller by pressing a little button behind the controller in a little hole, with a paperclip.

#### B - Other

- Black border, image too big  
Use your tv remote to find the image menu, and set the image size to *1:1 pixel* or *full*.  
If it doesn't work, try to activate the overscan in the recalbox menu **System Settings**.

- Black screen on PC monitor
If you have a black screen on PC monitor (hdmi or dvi) edit the config.txt file (MAJ at start) and remove the line hdmi_drive=2


#### C - Hard reset
- If you want to reset the system, plug an usb keyboard and press Shift at startup. You can reinstall recalboxOS from here. All your data will be erased.

#### D - Root Access
- Use the username `root` and the password `recalboxroot` 
- You can connect through ssh to the recalbox. 
- You can access a terminal by quitting emulationstation with F4 and then press ALT+F2.  

### IX - recalbox.conf
The file `recalbox.conf` shared in the samba `system` directory is used to modify other settings that will not appear in the frontend.
See [[recalbox.conf|recalbox.conf-(EN)]]
