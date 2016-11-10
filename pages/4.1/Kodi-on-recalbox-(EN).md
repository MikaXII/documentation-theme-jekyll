---
layout: page
title: Kodi on recalbox (EN)
wikiPageName: Kodi-on-recalbox-(EN)
menu: wiki
---

Kodi is a Media Center integrated into recalbox. You can connect to a wide variety of streams with an Ethernet connection to enjoy movies, music, and more. Live and recorded media are accessible with a properly setup KODI installation. Likewise you can just connect to your own local media via USB or network. 

You can either start it by pressing the **X** button(within ES), or pressing **START** + Selecting the first entry of the menu(KODI). To quit KODI navigate to the power icon on the lower left of the main KODI menu and select "Power Off System" or "Reboot", both items will return you the ES main Menu follow regular ES commands if you wish to power down. In the default configuration (3.3.0b17) The "Exit" feature may lock up the system. Also, you cannot power down straight from KODI you have to return to ES if you wish to actually power down. 

**New KODI users:** Out of the box KODI only has a few options. You need an Ethernet connection unless you are only using local or USB connected Media. [KODI wiki](http://kodi.wiki/view/Main_Page) has more info on specifics of setting up and using KODI. KODI is fairly intuitive. It will usually find USB media automatically when you enter the Video or Music options you should see you USB connected media or a path to it. Additionally the Video, Music & other tabs have "Addons", _(similar to an APP)_. There are several "Addons" you can download straight from the main KODI repository within KODI itself, and several other repositories _(collection of addons)_ users have created you may need to dig a little deeper for to add some pretty amazing content. To Get Music or Video "Addons", navigate to the "Addons" tabs under the "Music" or "Video" tab and click on it. Or select the main tab by clicking it and you will see any locally connected Media or Devices, "Addons" already installed. Click "Addons" and find the button that says "Get More". That will take you to a list of relevant KODI approved "Addons". Simply select one you are interested in and click install. This will happen in the back ground and if you have a decent Ethernet connection will take less than a minute to download and install typically. If you have Network media, you need to set up those paths in the file system settings. Again all these are well documented on their own WIKI and many videos are available on setting up KODI. 

Notes: 
* There are some options in the [config](https://github.com/recalbox/recalbox-os/wiki/recalbox.conf-%28EN%29) if you wish to boot directly to KODI each time rather than ES(default). 
* For your initial setup of KODI you will want a keyboard, though not required. This will make some of the initial setup easier. Also, most of the Smartphone/Tablet apps (if configured within KODI) will offer a keyboard as required when you enter a dialog requiring one, or simply click in the open dialog box to bring up an on screen keyboard you can use with your controller. 
* Some people sell dongle's or instructions to getting content on your KODI, but these are just pre-assembled collections or repositories that are free if you find them on your own. 
* Some of the "Addons" may require a subscription, like Netflix or Amazon Video, others may simply require you set up an account like Pandora. 
* If your controllers are going crazy when you enter KODI, they are not set up correctly. Revisit setting up controllers. [Recalbox Controller Section](https://github.com/recalbox/recalbox-os/wiki/Manual-%28EN%29#controllers)
* Not all features and Add-Ons are available to PI version of KODI, but most are.
* The first time and each time you start KODI it will do some background updates or checks. This may lead to some inconsistent or delayed use of certain features. Usually just waiting a moment, will clear those up. The more addons you have the longer this may take and some may be changed in settings to not be automatic. 
* Current Recalbox version of KODI is "Helix"

# OPTIONS:

The [[recalbox.conf|recalbox.conf-(EN)]] contains some Kodi options. You can enable or disable kodi, enable the X button shortcut or auto start kodi on boot.  

Controllers are supported in Kodi. You can use **HDMI CEC** feature of your TV, to control Kodi from your tv remote, or **Yatse**, a Kodi remote for smartphone.

# Miscellaneous : 
## Power management with **HDMI CEC**
If you try to exit or to shutdown Kodi, your Raspberry will always send a shutdown HDMI order to your A/V amplifier + television. In consequence all your "peripherals" will be shut down.

To avoid this behaviour you have to disable "Shutdown peripheral on exit" parameter by going into:
> System -> Settings -> System -> Input Devices -> Peripherals -> CEC adapter

CEC Adapter, will in some cases allow control of your KODI via your regular TV remote if they all support CEC. CEC sends remote commands VIA HDMI cable to your PI. [Kodi CEC Wiki](http://kodi.wiki/view/CEC)

## Yatse configuration:
Yatse and some other APP's are remote controls for KODI. These apps often offer more control and more intuitive control of KODI. It's not required but if you find you like KODI, you will probably enjoy the experience with the APP remote better.
 
**First you'll have to start kodi on your recalbox.**

After the installation of the Yatse application, Yatse will search on your network for available Kodis.  

[![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/yatse/configure_yatse_for_kodi_recalbox_1-300px.png)](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/yatse/configure_yatse_for_kodi_recalbox_1.png)

You can skip this step and go to the manual configuration.  
Just set the recalbox IP on your network (displayed in the _Network Option_ menu of recalbox) and the port to **8081**  

[![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/yatse/configure_yatse_for_kodi_recalbox_2-300px.png)](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/yatse/configure_yatse_for_kodi_recalbox_2.png)

Now your Yatse controller is connected :  
 
[![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/yatse/configure_yatse_for_kodi_recalbox_3-300px.png)](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/yatse/configure_yatse_for_kodi_recalbox_3.png)

If you like Yatse, please buy the unlocker for awesome new features. 

## Joystick configuration :
The configuration mapping between joystick and action in Kodi can be changed in the file /recalbox/configs/kodi/input.xml using actions and functions listed here http://kodi.wiki/view/Keymap#Commands

The current default mapping is :
- a: Select
- b: Back
- x: Stop
- y: Menu
- start: Pause
- select: ContextMenu
- pageup: nothing
- pagedown: nothing
- l2: nothing
- r2: nothing
- up: Up
- down: Down
- right: Right
- left: Left
- joystick1up: VolumeUp
- joystick1down: VolumeDown
- joystick1left: VolumeDown
- joystick1right: VolumeUp
- joystick2up: Up
- joystick2down: Down
- joystick2left: Left
- joystick2right: Right
- hotkey: nothing
