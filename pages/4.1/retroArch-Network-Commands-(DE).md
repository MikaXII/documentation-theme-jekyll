---
layout: page
title: retroArch Network Commands (DE)
wikiPageName: retroArch-Network-Commands-(DE)
menu: wiki
---

Netzwerk-Befehle werden gebraucht, um gewisse Funktionen von RetroArch zu steuern. Diese Befehle werden über UDP (User Datagram Protocol) an RetroArch gesendet. Bei ***recalbox*** werden diese Befehle über die **Hotkey**-Funktion vom Controller aus gesendet. So wird zum Beispiel mit **Hotkey+A** ein Reset des Spiels durchgeführt und mit **Hotkey+Y** das Spiel gespeichert.  

##Aktivierung
Diese Befehle können jedoch auch über die Kommandozeile, oder über GPIO-Pins an RetroArch gesendet werden. Dazu muss jedoch zuerst die Option **Network Command** im RetroArch-Menü aktiviert werden, oder in der ‘retroarch.cfg’ folgende Zeile abgeändert werden:  

`network_cmd_enable = "false"` wird zu `network_cmd_enable = "true"`

##Befehl über die Kommandozeile senden
Die Netzwerkbefehle können mit folgendem Befehl über die Kommandozeile versendet werden (Das Beispiel gilt für Linux):
  
` echo -n "QUIT" | nc -u -w1 127.0.0.1 55355`  
  
Standardmässig hört RetroArch auf den **Port 55355**.  

##Befehl senden über GPIO
###Anwendungsbeispiel:
Du verwendest ein bestehendes Retro-Konsolengehäuse (NES, N64 etc.) und willst den originalen Reset-Button dazu verwenden um ein Reset des aktuellen Spiels durchzuführen und nicht um die gesamte Hardware (Raspberry Pi etc.) neuzustarten.
Das folgende Script zeigt, wie mit den GPIO-Pins 5 und 6 der Netzwerk-Befehl **RESET** an RetroArch gesendet wird, um so das Spiel zurückzusetzen: 
 
```
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
```

##Befehle
Die folgenden Befehle werden alle unterstützt:  
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
