---
layout: page
title: Emulator interactions via GPIO mapping (EN)
wikiPageName: Emulator-interactions-via-GPIO-mapping-(EN)
menu: wiki
---

Network commands are used to control certain parts of RetroArch. To achieve this, commands are sent to RetroArch via UDP (User Datagram Protocol).  
  
Usually in ***recalbox*** these commands are sent via the **Hotkey** function from the controller. For example to reset the game you press **Hotkey + A** or to save the game you press **Hotkey + Y**.  
  
Remember this works only with **RetroArch / emulators which are part of libretro**.
  
##Enable
But these commands can also be sent to RetroArch via the command line or GPIO pins. For these you have to enable the option **network commands** in the RetroArch menu or change the following line in `retroarch.cfg`: 
* `network_cmd_enable = «true»` 
   
##Send a command via GPIO
###Application examples:
You are using an existing retro game console case (NES, N64, etc.) and you want to use the original reset button to reset the current game you play and not to reset the whole hardware (Raspberry Pi, etc.).  
The following script shows how to send the network command **RESET** to RetroArch via the GPIO pins 5 and 6 to reset the current game.  
  
    import RPi.GPIO as GPIO  
    import time  
    import socket  
    # addressing information of target  
    IPADDR = "127.0.0.1"  
    PORTNUM = 55355  
    # enter the data content of the UDP packet  
    COMMAND = "RESET"  
    # initialize a socket, think of it as a cable  
    # SOCK_DGRAM specifies that this is UDP  
    try:  
        s = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)  
    except socket.error:  
        print 'Failed to create socket'  
        sys.exit()  
    GPIO.setmode(GPIO.BCM)  
    GPIO.setup(3, GPIO.IN, pull_up_down=GPIO.PUD_UP)  
    def exitEmulator(channel):  
        s.sendto(COMMAND, (IPADDR, PORTNUM))  
    GPIO.add_event_detect(3, GPIO.FALLING, callback=exitEmulator, bouncetime=500)  
    while True:  
        time.sleep(10)  

With this script it is not only possible to **RESET** the emulators but you can use the needed command from a variety of commands. You are able to **QUIT** the emulators (return to EmulationStation), **LOAD** or **SAVE** a state, **PAUSE** the game etc. To achieve this, just replace the **RESET** from the **COMMAND = RESET** with a command of your choice.  
  
_**ATTENTION: This script might not work with all RetroArch network commands. For some it does but for other it needs more work to get it running (e.g. FASTFORWARD_HOLD).**_  
  
You can also remap the pins from the Raspberry Pi.  
  
And do **NOT** forget: ***recalbox*** has already built-in options to reset, start and shutdown the hardware you are using via buttons and GPIO:  
  
https://github.com/recalbox/recalbox-os/wiki/Add-a-start-stop-button-to-your-recalbox-%28EN%29  

##Commands
The following commands are supported by RetroArch:  
* FAST_FORWARD  
* FAST_FORWARD_HOLD  
* LOAD_STATE  
* SAVE_STATE  
* FULLSCREEN_TOGGLE  
* QUIT  
* STATE_SLOT_PLUS  
* STATE_SLOT_MINUS  
* REWIND  
* MOVIE_RECORD_TOGGLE  
* PAUSE_TOGGLE  
* FRAMEADVANCE  
* RESET  
* SHADER_NEXT  
* SHADER_PREV  
* CHEAT_INDEX_PLUS  
* CHEAT_INDEX_MINUS  
* CHEAT_TOGGLE  
* SCREENSHOT  
* MUTE  
* NETPLAY_FLIP  
* SLOWMOTION  
* VOLUME_UP  
* VOLUME_DOWN  
* OVERLAY_NEXT  
* DISK_EJECT_TOGGLE  
* DISK_NEXT  
* DISK_PREV  
* GRAB_MOUSE_TOGGLE  
* MENU_TOGGLE  

##Send a command via the command line
You can also send network commands via the command line in Linux. The following shows how to do this:  
* ` echo -n "QUIT" | nc -u -w1 127.0.0.1 55355` 
   
RetroArch is listen to **port 55355** by default.  
