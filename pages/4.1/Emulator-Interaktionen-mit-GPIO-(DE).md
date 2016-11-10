---
layout: page
title: Emulator Interaktionen mit GPIO (DE)
wikiPageName: Emulator-Interaktionen-mit-GPIO-(DE)
menu: wiki
---

Netzwerk-Befehle werden gebraucht, um gewisse Teile von RetroArch zu steuern. Dazu werden diese Befehle über UDP (User Datagram Protocol) an RetroArch gesendet. 
  
Normalerweise werden diese Befehle in ***recalbox*** über die **Hotkey**-Funktion vom Controller aus gesendet. So wird zum Beispiel mit **Hotkey+A** ein Reset des Spiels durchgeführt, oder mit **Hotkey+Y** das Spiel gespeichert. 
  
Beachte, dass dies nur mit Emulatoren von **libretro** funktioniert.  

##Aktivierung
Diese Befehle können jedoch auch über die Kommandozeile, oder über GPIO-Pins, an RetroArch gesendet werden. Dazu muss jedoch erst die Option **Network Command** im RetroArch-Menü aktiviert werden, oder in der ‘retroarch.cfg’ folgende Zeile abgeändert werden:  

* `network_cmd_enable = "false"`
in
* `network_cmd_enable = "true"`  

##Befehle senden über GPIO
###Anwendungsbeispiele
Du verwendest ein bestehendes Retro-Konsolengehäuse (NES, N64 etc.) und willst den originalen Reset-Button verwenden, um ein Reset des aktuellen Spiels durchzuführen und nicht um die gesamte Hardware (Raspberry Pi etc.) neuzustarten.
Das folgende Script zeigt, wie mit den GPIO-Pins 5 und 6 der Netzwerk-Befehl **RESET** an RetroArch gesendet wird, um so das Spiel zurückzusetzen:

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
  
Mit diesem Script ist es nicht nur möglich einen Emulator **ZURÜCKZUSETZEN** (RESET), sondern es kann für eine ganze Menge von Befehlen benutzt werden. Emulatoren können **BEENDET** (QUIT, Zurück zu EmulationStation) und **PAUSIERT** (PAUSE) werden. Es können Speicherpunkte **GELADEN** (LOAD) oder **GESPEICHERT** (SAVE) werden.  
Um das zu erreichen, muss lediglich die folgende Zeile im Script geändert werden:  
  
`COMMAND = RESET`zu `COMMAND = BefehlDeinerWahl`  
  
_**ACHTUNG: Dieses Script funktioniert nicht Out-of-the-Box mit allen RetroArch-Befehlen. Für manche funktioniert es, für andere jedoch braucht es mehr Arbeit und Abänderungen, um es zum Laufen zu bringen (z.B. FASTFORWARD_HOLD).**_
  
Die Pins vom Raspberry Pi können ebenfalls geändert werden.  
  
**NICHT VERGESSEN**: ***recalbox*** hat bereits integrierte Optionen um die Hardware via Druckknöpfe und GPIO-Pins zu starten, zurückzusetzen und herunterzufahren:  
  
https://github.com/recalbox/recalbox-os/wiki/Add-a-start-stop-button-to-your-recalbox-%28EN%29    
  
##Befehle
Die folgenden Befehle werden von RetroArch unterstützt:  

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
  
##Befehl über die Kommandozeile senden 
Die Netzwerk-Befehle können auch über die Kommandozeile auf Linux versendet werden. Dies funktioniert folgendermaßen:  
  
`echo -n "QUIT" | nc -u -w1 127.0.0.1 55355`  
  
Standardmäßig hört RetroArch auf den **Port 55355**.  
