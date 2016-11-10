---
layout: page
title: Manual (EN)
wikiPageName: Manual-(EN)
menu: wiki
---

# recalbox 4.X
## Manual v1.4.0

![](http://blog.recalbox.com/wp-content/uploads/2015/01/retrobox-etiquette.png)

http://www.recalbox.com

- I - [First use](#first-use)
- II - [Configuration](#configuration)
 - A - [Controllers](#controllers)
   - 1 - [PS3 controllers](#ps3controllers)
    - 2 - [XBox 360 controllers](#xboxcontrollers)
    - 3 - [Add an bluetooth controller](#btcontrollers)
    - 4 - [Configure a controller](#configurecontrollers)
    - 5 - [Buttons mapping](#btnmapping)
    - 6 - [Keyboard mapping](#keyboardmapping)
    - 7 - [GPIO controllers](#gpiocontrollers)
    - 8 - [Virtual Gamepads](#virtualgamepads)
 - B - [System settings](#system-settings)
- III - [EmulationStation](#es)
 - A - [Presentation](#es-pres)
 - B - [Settings](#es-settings)
   - 1 - [System settings](#es-settings-sys)
    - 2 - [Game settings](#es-settings-games)
    - 3 - [Controller settings](#es-settings-controllers)
    - 4 - [UI settings](#es-settings-ui)
    - 5 - [Sound settings](#es-settings-sound)
    - 6 - [Network settings](#es-settings-network)
 - C - [Controls](#controls)
 - D - [Favorites](#favorites)
 - E - [Scraper](#scrapper)
- IV - [During the game](#duringgame)
 - A - [Saves](#duringgame-saves)
 - B - [Special commands](#duringgame-special)
- V - [Updates](#updates)
- VI - [Network features](#network)
 - A - [Add your games](#network-add)
 - B - [Arcade Games](#network-arcade)
 - C - [Scummvm Games](#network-scummvm)
 - D - [Screenshots](#network-screenshots)
 - E - [Save your saves](#saves)
- VII - [Kodi Media Center](#kodi)
- VIII - [Troubleshooting](#trouble)
 - A - [Controllers](#trouble-controllers)
 - B - [Other](#trouble-other)
 - C - [Hard reset](#hard-reset)
 - D - [Root Access](#root-access)
- IX - [recalbox.conf](#recalbox.conf)


## Introduction
The recalbox is a system that will allow you to play retro games easily.

It runs on a micro computer called the Raspberry Pi, and uses a batch of optimized emulators.

## <a name='first-use'></a>I - First use
The necessary package :
- A raspberry PI 1, 2 or 3
- 16GB or more SD/microSD card
- HDMI cable
- a micro USB power cable **> 1.5AMP**
- a USB or a Bluetooth* controller (*_and Bluetooth>USB dongle_)

See **[recalbox.com/diy](http://www.recalbox.com/diyrecalbox)** for more information on the first install.

After the [[Installation|Installation-(EN)]], the first thing you have to do is to connect the recalbox to the TV with the HDMI cable.

To power on the recalbox, just plug the micro USB power cable in.

Many controllers work out of the box, but if you want to configure directly an USB controller, plug in a USB keyboard and see [Add an usb controller](#configurecontrollers)

To shut down the system : push on the start button and choose “QUIT” and “SHUTDOWN SYSTEM”. _(Shortcut: Press "Select" for shut down only menu)_  

You can then unplug the power cable. _(Best Practice: wait for green/orange light on PI to stop flashing)_

## <a name='configuration'></a>II - Configuration

### <a name='controllers'></a>A - Controllers
Wired and wireless _PS3 Dualshock_ and _Xbox 360_ controllers are supported. Many **USB** and **Bluetooth** controllers are supported too. For more information see the [peripheral compatibility list](https://github.com/digitalLumberjack/recalbox-os/wiki/Compatibility-%28EN%29) 

**Note:** By default the PS3 controller is selected in the config. If you are using other controllers it may be necessary to de-select the PS3 controller, select the controller you are using, save the config & reboot. Find your controller below for more specifics. 

#### <a name='ps3controllers'></a>1 - PS3 controllers
You must have a bluetooth dongle to use a PS3 wireless controller.
You cannot charge the sisaxis on the RPi, you must charge controllers directly on the usb power.  
Plug the controller on the recalbox **only** to associate your controller with your recalbox.  
In order to associate a _PS3 controller_, plug the controller on the recalbox and **wait 10 seconds**. You can now unplug the controller and press the Home button.

For asian copies of the PS3 dualshock 3 (aka GASIA or SHANWAN) see [[PS3 controllers drivers|PS3-controllers-drivers-(EN)]]

Remember that the configuration of the controllers in recalbox is based on the SNES buttons assignment : 

| ps3 pad | snes pad |
| :--------------: | :--------------: |
| x | B |
| ◯ | A |
| ⬜ | Y |
| △ | X |

**Note:** The default **HOTKEY** button is the **PS** button. The one in the middle of your controller. 

For more info about HOTKEY actions like saving/loading see the [Special commands](https://github.com/recalbox/recalbox-os/wiki/Manual-%28EN%29#duringgame-special) section.

#### <a name='xboxcontrollers'></a>2 - XBox 360 controllers

**Note:** XBox 360 Wireless controllers need specific wireless receiver hardware.  

If you have a XBox 360 wired or wireless controller, please activate the `xboxdrv` option in [recalbox.conf](https://github.com/digitalLumberjack/recalbox-os/wiki/recalbox.conf-%28EN%29) to have the best out-of-box-support for your controller. 

The easiest way to adjust the recalbox.conf file is to navigate to the recalbox web frontend via a webbrowser (f.e. http://192.168.1.100) and make the following changes in the configuration tab:

* First de-select the PS3 controller(default) change `controllers.ps3.enabled=1` to `controllers.ps3.enabled=0`
* Then change the xBox settings from `controllers.xboxdrv.enabled=0` to `controllers.xboxdrv.enabled=1`

Then reboot with your controller or wireless receiver plugged in. (It is recommended to "wake up" the controllers before starting the PI")

Remember that the configuration of the controllers in recalbox is based on the SNES buttons assignment : 

| xbox pad | snes pad |
| :--------------: | :--------------: |
| A | B |
| B | A |
| X | Y |
| Y | X |

**Note:** The default **HOTKEY** button is the **HOME** button. The big one in the middle of your controller.

For more info about HOTKEY actions like saving/loading see the [Special commands](https://github.com/recalbox/recalbox-os/wiki/Manual-%28EN%29#duringgame-special) section.

#### <a name='btcontrollers'></a>3 - Add a bluetooth controller
To add a bluetooth controller, set your controller in pairing mode.  
Then go to the menu with start button or a keyboard and select **Controller Settings**. 

Select **Pair a bluetooth Controller**:  
[![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/bluetooth-pair-350px.jpg)](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/bluetooth-pair.jpg)

A list of detected controllers appears, just select yours and now the controller is paired! Now you can configure it if it's not already a supported controller!

For **8bitdo** users, see [[8bitdo on recalbox|8bitdo-on-recalbox-(EN)]]. 


#### <a name='configurecontrollers'></a>4 - Configure a controller
You can add USB controllers on the recalbox.

Most models are compatible, see the [compatibility list](https://github.com/digitalLumberjack/recalbox-os/wiki/Compatibility-%28EN%29)


After plugging your usb controller or pairing your bluetooth controller, press START with an already configured controller (or ENTER on the keyboard) and select "CONFIGURE INPUTS".

Then follow instructions. 

The last button, the **HOTKEY** is a button that will activate buttons combination (see [Special commands](#duringgame-special)). For xbox 360 and PS3 gamepads, the default hotkey button is **HOME** or **PS**. It is recommended to use **L3** (the joystick click on dualshock) or _**SELECT**_  

Buttons assignment is based on the Super Nintendo controller :  
![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/snes-controller.jpg)

The L and R buttons (with L2 R2 L3 R3) are based on Playstation controllers.


Pass any buttons you don't have by pressing a button for 2 seconds.


Back on the configuration screen, you can assign the controller to a player. _Your controller is now configured !_


#### <a name='btnmapping'></a>5 - Buttons mapping

For 6 buttons controllers (snes, psx, arcade etc) the buttons are mapped to corresponding buttons on the original controller.   
For 2 buttons controllers (nes, pcengine, gameboy etc) the mapped buttons are B and A.

#### <a name='keyboardmapping'></a>6 - Keyboard mapping
If you totally failed at the controller configuration or just want to configure a controller, you can attach a wired USB keyboard to the recalbox.
Enter is **START**, Space is **SELECT**, S is **BACK**, A is **OK**

#### <a name='gpiocontrollers'></a>7 - GPIO controllers
You can connect your arcade joysticks and buttons directly on the raspberry GPIOs. See [[GPIO controllers|GPIO-controllers-(EN)]]

You can connect original controllers from PSOne, Nes, Snes, Megradrive and other. See [[DB9 and Gamecon controllers|DB9-and-Gamecon-controllers-(EN)]]


#### <a name='virtualgamepads'></a>8 - Virtual Gamepads
With Miroof's [Virtual Gamepads](https://github.com/miroof/node-virtual-gamepads) you can add up to 4 controllers with your phones ! 
Just start your Internet Navigator on your phone, and type the recalbox IP followed by the communication port (port=8080). You can get the recalbox IP in the setting menu  [NETWORK SETTINGS](#user-content-6---network-settings)

[![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/virutalgamepad_touch_zones-350px.png)](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/virutalgamepad_touch_zones.png)

For more info see [[Virtual Gamepad|Virtual-Gamepad-(EN)]]

### <a name='system-settings'></a>B - System Settings
You have two ways to configure your recalbox. The frontend Emulationstation offers many configurations features. See [EmulationStation settings](#es-settings)

But if you want to fine tuning emulators one by one, you should have a look at **[[recalbox.conf|recalbox.conf-(EN)]]**


## <a name='es'></a>III - EmulationStation

### <a name='es-pres'></a>A - Presentation

When you start the recalbox system, the frontend emulationstation shows up.  
You can select your systems, launch your games, or access configuration menu from here.

The first screen is the system screen : 

[![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/emulationstation-350px.jpg)](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/emulationstation.jpg)

It shows all available systems.


### <a name='es-settings'></a>B - Settings

By pressing start, you will be able to change some system settings.  
[![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/settings-350px.jpg)](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/settings.jpg)

#### <a name='es-settings-sys'></a>1 - SYSTEM SETTINGS
You will access **system information**, **language selection**, **overclock settings**, **updates settings** and **kodi settings**.  
You can change the overclock of your RPI. The overclock speed order for RPI1 is :  
*NONE* < *HIGH* < *TURBO* < *EXTREM*  
Extreme may void your warranty but is **the only one** that will give you really good performance for all emulators on RPi1.

It is also recommended to overclock your RPi2, if you want emulate the N64 and have the best gaming experience.

#### <a name='es-settings-games'></a>2 - GAME SETTINGS
You can set game options : **video ratio** (16/9, 4/3), **image smooth**, **rewind** and **auto save/load**.   
The **rewind** option allows you to turn back time in games.  
:warning: _This feature may slow down some emulators (snes, psx)_ if you enable it by default. You can enable it by emulator in [[recalbox.conf|recalbox.conf-(EN)]]   

The **auto save/load** option allows you to auto save a savestate when you exit a game, then reload automatically this savestate when you restart this game. Once the game started, and the savestate loaded, if you want to return to the title screen of this game, use the [special command](#duringgame-special) **reset**. You can enable it by emulator in [[recalbox.conf|recalbox.conf-(EN)]]   

You can also easily configure *shaders* for your systems. The **shader set** configuration contains the shader sets available for recalbox. The **scanlines** shaders enable scanlines on all systems to look like a CRT television. The **retro** shaders is a set of the best shaders, chosen by the community, that will offer you the closest to original gaming experience !  
More info on [[Shaders configuration|Shaders-configuration-(EN)]] page.  

You can also switch *shaders* in-game using your controller. Use the [Special commands](#duringgame-special) Hotkey + R2 or Hotkey + L2 to see the next or previous shader.

You can alose


#### <a name='es-settings-controllers'></a>3 - CONTROLLER SETTINGS
You can configure your controllers.

#### <a name='es-settings-ui'></a>4 - UI SETTINGS
You will have access to the frontend setting. You can set the overscan here if you have black border or a cropped image. See [[Overscan settings|Overscan-settings-(EN)]] for more information.

#### <a name='es-settings-sound'></a>5 - SOUND SETTINGS
You can enable or disable **background sounds** in emulationstation, set **system volume** and choose **output device** (*auto*, *jack* or *hdmi*)  
Select jack to force analog output.  

#### <a name='es-settings-network'></a>6 - NETWORK SETTINGS
You can enable and configure the **wifi** and the **hostname**, get the recalbox **IP**
Type the SSID of your network and the network key with a keyboard.  
Once you validate, the wifi is activated.  
A known bug bug exists that does not allow you to enter all the characters you need for the SSID or the Key. 
You can configure this directly from your wifi using [[recalbox.conf|recalbox.conf-(EN)]]


### <a name='controls'></a>C - Controls

**Frontend commands :**

B → Select  
A → Back  
Y → Switch Favorite  
X → Launch Kodi  
Start → Menu  
Select → Options (reboot menu on systems screen)  
R → Next Page   
L → Previous Page  

When you select a system with A, the screen change and show all available games.

When the game is running, go to the section *During the game* to see how you can go back to the frontend.


### <a name='favorites'></a>D - Favorites

You can set a game as a favorite by pressing the Y button. The game will be on top of the game list with a ☆ before its name. Toggle the favorite with Y. 
It is necessary to turn off/reboot the system properly with the emulationstation menu to save your favorites and then find them in the next startup.


### <a name='scrapper'></a>E - Scraper
For each game, you can get the cover art and information about the games you have stored while browsing your games lists in the emulationstation. Press **START** and go to **SCRAPPER**. Then follow the instructions. 



## <a name='duringgame'></a>IV - During the game

When you are in the game, there are special commands available.

### <a name='duringgame-saves'></a>A - Saves 
Emulators bring a very useful feature : save state. A saved state is a quick save of the game, and allows you to reload the game at this point.

With save states, you will never have to seek for a saved point again !

You can save more than one state per game if you change the save slot.

You can save a state with **Hotkey** + **Y**
You can load a state with **Hotkey** + **X**


### <a name='duringgame-special'></a>B - Special commands
  
**Hotkey** + Y → Save State    
**Hotkey** + X → Load State      
**Hotkey** + Up → Select Save Slot -1    
**Hotkey** + Down → Select Save Slot +1    

**Hotkey** + Start → End Game and Quit To Main Menu    
**Hotkey** + A → Reset Game    
**Hotkey** + B → Retroarch Menu     
**Hotkey** + L1 → Screenshot    

**Hotkey** + Right → Speedup game    
**Hotkey** + Left → Rewind (if activated in options)    

**Hotkey** + R2 → Next shader preset    
**Hotkey** + L2 → Previous shader preset    


In FBA and Mame, press Select to add a credit.

You can access retroarch configuration menu with *Hotkey* + *B*
If you want to configure retroarch and save the config, you can select the "Save Settings on Exit" in the retroarch menu. After that, all configuration you make in rgui will be saved.

### <a name='updates'></a>V - Updates
The recalbox update can be done in the frontend menu. Configure the wifi or plug an ethernet cable on the recalbox, press Start and select "SYSTEM SETTINGS" with A, then "UPDATES" and "START UPDATE".

After the update, the system will reboot.


## <a name='network'></a>VI - Network features
If you configured the wifi or plugged an Ethernet cable on the recalbox, it shares files on your local network. On your computer, got to Network on Windows explorer, and select the recalbox :

[![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/recalbox-network1-350px.jpg)](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/recalbox-network1.jpg)

If you don't see the recalbox in your network, try to type **\\\\RECALBOX** in the explorer address bar. If it doesn't work, go in the recalbox menu, __NETWORK SETTINGS__ and note the ip.
Then type your ip in the explorer address bar, for example **\\\\192.168.1.30**

You can access all recalbox shared folders :

[![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/recalbox-network2-350px.jpg)](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/recalbox-network2.jpg)


### <a name='network-add'></a>A - Add your games
Just copy the files in the corresponding folder. You can use either *.zip* files or uncompressed roms.
To refresh the game library, go to the **Menu**, then **Games Settings** then **Update Games Lists**

Don’t hesitate to talk about your favorite games in the recalbox forum !
http://blog.recalbox.fr/forums/

### <a name='network-arcade'></a>B - Arcade games
If you want to add arcade games on your recalbox, you should read the mini how to [[Easy Arcade on Recalbox|Easy-Arcade-on-Recalbox-(EN)]] and learn how to [[check your roms version|Check-your-roms-version-with-clrmamepro-(EN)]].   
Then you can also enable the [[Neogeo Unibios|Use-Neogeo-Unibios-(EN)]] to have more options with your games.

### <a name='network-scummvm'></a>C - Scummvm games
When you add a Scummvm game, it must be in an uncompressed folder. In this folder, you will have to add a single file, named [gameshortname].scummvm

You can find shortnames for all supported games at http://scummvm.org/compatibility/

For example, if you copied the folder "Broken Sword 1" in the scummvm directory. In this folder create a file named sword1.scummvm

Your game will appear in the frontend, and you will be able to change it's metadata if you want to display a good name. 

### <a name='network-screenshots'></a>D - Screenshots
Press Hotkey + L1 in emulators to take a screenshot. The png file is saved in the "screenshots" directory, you can access on the network.  
Share your best screenshots with us on http://blog.recalbox.com/forums/

### <a name='saves'></a>E - Save your saves
The *saves* folder share contains all saves and saved states. You can copy all the files if you want to secure them.

## <a name='kodi'></a>VII - Kodi Media Center
By pressing X button on your controller, you can launch Kodi Media Center, aka XBMC. You can also access Kodi by pressing start and launching it from the menu.

To quit Kodi, Navigate to the lower left power icon and select "Power Off System" in the program, and you will come back to recalboxOS. _Currently(3.3.0b17) using the "Exit" button may lock up your PI_

The controllers are now supported in kodi, but if you prefer, you can use HDMI CEC or a smartphone remote application. More info on the mini how to [[Kodi on recalbox|Kodi-on-recalbox-(EN)]]


## <a name='trouble'></a>VIII - Troubleshooting

### <a name='trouble-controllers'></a>A - Controllers :

- The PS3 controller is blinking but does not associate   
Plug a controller on the recalbox and wait 10 seconds. You can now unplug the controller and press the Home button.

- The PS3 controller seems dead  
You must reset the controller by pressing a little button behind the controller in a little hole, with a paperclip.

### <a name='trouble-other'></a>B - Other

- Black border, image too big  
Use your tv remote to find the image menu, and set the image size to *1:1 pixel* or *full*.  
If it doesn't work, try to activate the overscan in the recalbox menu **System Settings**.  
See [[Overscan settings|Overscan-settings-(EN)]] for more information.


- Black screen on PC monitor
If you have a black screen on PC monitor (hdmi or dvi) edit the config.txt file (MAJ at start) and remove the line hdmi_drive=2  
More info in [[Mini HowTo - Connect your recalbox to a DVI screen|Connect-your-recalbox-to-a-DVI-screen-(EN)]]  


### <a name='hard-reset'></a>C - Hard reset
- If you want to reset the system, plug an usb keyboard and press Shift at startup. You can reinstall recalboxOS from here. All your data will be erased.

### <a name='root-access'></a>D - Root Access
- Use the username `root` and the password `recalboxroot` 
- You can connect through ssh to the recalbox. 
- You can access a terminal by quitting emulationstation with F4 and then press ALT+F2.

More info in [[Mini HowTo - Root access on terminal|Root-access-on-terminal-(EN)]]  

## <a name='recalbox.conf'></a>IX - recalbox.conf
The file `recalbox.conf` shared in the samba `system` directory is used to modify other settings that will not appear in the frontend.
See [[recalbox.conf|recalbox.conf-(EN)]]
