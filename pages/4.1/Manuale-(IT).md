---
layout: page
title: Manuale (IT)
wikiPageName: Manuale-(IT)
menu: wiki
---

# recalbox 3.2.0
## Manuale v1

![](http://blog.recalbox.com/wp-content/uploads/2015/01/retrobox-etiquette.png)

http://www.recalbox.fr

- I - [Prerequisiti](#prerequisiti)
- II - [Configurazione](#configurazione)
 - A - Controllers
   - 1 - PS3 controllers
    - 2 - XBox 360 controllers
    - 3 - Aggiungere un controller usb
    - 4 - Buttons mapping
    - 5 - Keyboard mapping
    - 6 - GPIO controllers
    - 7 - Configurare Retroarch
 - B - System settings
 - C - Sound settings
 - D - Network settings
- III - [EmulationStation](#emulationstation)
- IV - [Impostazioni in-game](#impostazioniingame)
 - A - Save game
 - B - Comandi speciali
- V - [Updates](#updates)
- VI - [Network features](#networkfeatures)
 - A - Aggiungere giochi
 - B - Scummvm Games
 - C - Screenshots
 - D - Salva i tuoi salvataggi
- VII - [Kodi Media Center](#kodi)
- VIII - [Troubleshooting](#troubleshooting)
 - A - Controllers
 - B - Altro
 - C - Hard reset
 - D - Root Access
- IX - [recalbox.conf](#recalboxconf)


### Introduczione
Recalbox è un sistema che consente di giocare facilmente con molti retro games.

E' stato ideato per un mini computer noto come RaspberrPi, ed utilizza una serie di emulatori ottimizzati per questo device.


### <a name='prerequisiti'></a>I - Prerequisiti
Ciò di cui hai bisogno :
- Un raspberry PI 1 o 2
- Un cavo HDMI 
- Un cavo micro USB per alimentare Raspberry (>1.5 AMP)
- Un controller USB o un controller PS3 

La prima cosa da fare è collegare il raspberry pi ad una televisione mediante il cavo HDMI

Per accendere il raspberry, basta collegare il cavo micro USB.

Se vuoi configurare direttamente un controller USB, collega la tastiera USB e guarda [Aggiungere un controller usb](#d---add-an-usb-controller)

Per spegnere il sistema: usa il pulsante start e selezione "ESCI" e "SPEGNI SISTEMA".
Successivamente puoi scollegare il cavo di alimentazione.


### <a name='configurazione'></a>II - Configurazione

Recalbox supporta vari controller USB, sono compatibili anche i controller per Xbox 360 and PlayStation 3 DualShock.


#### A - Controllers
I controller PS3 dualshock and Xbox possono essere utilizzati in modalità wireless.
##### 1 - PS3 controllers
Devi avere un dongle USB bluetooth per utilizzare il controller wireless PS3.
Per associare il controller PS3 al sistema recalbox, devi collegare il controller al raspberry ed attendere 10 secondi. Successivamente puoi scollegare il controller e premere il pulsante Home.



##### 2 - XBox 360 controllers
Se hai un controller XBox 360 con cavo or wireless, attiva il [xboxdrv in recalbox.conf](https://github.com/digitalLumberjack/recalbox-os/wiki/recalbox.conf-(IT)) per aver supporto.

Successivamente riavvia il sistema con il controller collegato e gioca.

##### 3 - Aggiungere un controller usb
Puoi aggiungere un controller USB al tuo recalbox.

Sono compatibili molti modelli.

Collega il tuo controller USB, premi il tasto START e selezione "Configura Inputs"

Sucessivamente segui le istruzioni. Se non hai sufficienti pulsanti puoi usare il tasto HotKey, mappandolo con il comando Select

I nomi dei pulsanti si basano su quelli del controller per Super Nintendo :
![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/snes-controller.jpg)

 
Ritorna alla pagina di configurazione, assegna il controller ad un player. Il tuo controller è ora configurato!


##### 4 - Buttons mapping

I controller a 6 pulsanti (snes, psx, arcade etc) la mappatura dei pulsanti corrisponde a quella del controller originario.   
I controller a 2 pulsanti (nes, pcengine, gameboy etc) fanno uso dei soli pulsanti B and A.

##### 5 - Keyboard mapping
Se non riesci a configurare i controller, puoi sempre collegare una tastiera usb a recalbox.
Invio corrisponde START, Spazio è SELECT, Q è BACK, S è OK

##### 6 - GPIO controllers
Puoi collegare il tuo arcade controller (joystick e pulsanti) direttamente al raspberry tramite GPIO. Attiva i controller via GPIO modificando il [[recalbox.conf|recalbox.conf-(IT)]] file.

![](https://github.com/DigitalLumberjack/mk_arcade_joystick_rpi/raw/master/wiki/images/mk_joystick_arcade_GPIOsb+.png)

Per maggiori informazioni: https://github.com/DigitalLumberjack/mk_arcade_joystick_rpi

Marqs DB9 e gamecon drivers sono ugualmente supportati. Vedi [[recalbox.conf|recalbox.conf-(IT)]]

##### 7 - Configurare Retroarch
Puoi accedre all menu di configurazione di retroarch  con la combinazione di comandi *Hotkey* + *B*
se vuoi configurare retroarch e salvare al configurazione, devi selezionare "Save Settings on Exit" nel menu di retroarch. Dopo ciò, tutte le configurazioni che farai tramite la rgui saranno salvate.

#### B - System Settings
Premendo il pulsante start e selezionando la prima voce, potrai cambiare alcuni settaggi di sistema.
Puoi abilitare o meno l'overscan, per ottenere o meno le bande nere laterali a video.  
Puoi abilitare o meno smooth setting. Tutti i giochi prenderanno questa configurazione.
Puoi overclockare il tuo RPi1. Le frequenze di clock passano NONE < HIGH < TURBO < EXTREM. Quest'ultima impostazione puo invalidare la garanzia del vostro raspberry ma è l'unica che ti darà ottime performance con tutti gli emulatori (Non è strettamente necessario overclocckare un RPi2).  
Puoi selezionare il formato immagine(16/9 or 4/3).

#### C - Sound settings
Nelle impostazioni audio, puoi selezionare il volume di sistema e l'uscita audio. Seleziona jack per forzare l'uscita analogica.

#### D - Network settings
Direttamente dal menu impostazioni di rete puoi attivare e configurare il collegamento wifi.
Indica il nome SSID della tua rete wireless e la relativa password.
Non appena confermi questi dati, la tua wifi sarà attivata.
E' noto un bug per il quale non puoi digitare alcuni caratteri come SSID o come password.
In tal caso configura direttamente la tua wifi da [[recalbox.conf|recalbox.conf-(IT)]]

### <a name='emulationstation'></a>III - EmulationStation

Quando avvi recalbox, ti apparirà come frontend emulationstation.
Puoi selezionare da qui il tuo emulatore e lanciarne i rispettivi giochi.

La prima schermata è quella di sistema: 

![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/emulationstation.jpg)


Potrai vedere tutti i sistemi disponibili.

Quando selezioni un sistema con il tasto A, l'immagine cambierà mostrandoti i giochi disponibili per quel sistema.

Quando un gioco è in esecuzione, vai alla sezione *Impostazioni in-game* come tornare al frontend.


**Comandi per il frontend :**

A -> Select  
B -> Back  
Start -> Menu  
Select -> Options  
R -> Next Page   
L -> Previous Page  

### <a name='impostazioniingame'></a>IV - Impostazioni in-game
 
### A - Save game 
Puoi salvare lo stato di gioco in cui ti trovi, consentendoti di ricaricare il gioco a quel punto.


Puoi avere piu di un salvataggio per gioco se cambi lo slot di salvataggio.

#### B - Comandi Speciali

In gioco, sono disponibili alcuni comandi particolari:  

Utilizzando il pulsante hotkey e uno dei seguenti: 

Y -> Salva State  
X -> Carica State  
Start -> Esci  
B -> Menu  
Up -> Salva su slot -1  
Down -> Salva su slot +1  
L1 -> Screenshot  
Right -> Speedup game  


In FBA and Mame, premi Select per aggiungere crediti.
In Mame, se la tua Hotkey is Select, potrai uscire con la combinazione di tasti R1 + Start (visto che il tasto Select è utilizzato per inserire crediti)``

### <a name='updates'></a>V - Updates
Gli aggiornamenti di recalbox possono essere fatti direttamente dal menu di frontend. Collega un cavo di rete, premi il pulsante Start e selezione “UPDATE” con il pulsante A.

Dopo l'aggiornamento il sistema si riavvierà.

### <a name='networkfeatures'></a>VI - Network features

Se colleghi un cavo di rete a recalbox, avrai modo di accedere alle condivisioni presenti. Dal tuo computer, esplora le risorse di rete e seleziona recalbox:

![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/partagereseau-recalbox.jpg)


Puoi accedere alle condivisioni di recalbox:

![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/partagereseau.jpg)



#### A - Aggiungere giochi
Basta che copi le tue rom nella directory corrispondente.

Here is the list of supported files :

Nes : `.nes`  
MasterSystem : `.sms`  
Super Nes : `.smc` `.sfc`  
Megadrive : `.md`
PlayStation : `.img` `.iso` `.bin`  
Game Boy Advance : `.gba`  
Mame : `.zip`  
FBA : `.zip`  
Atari 2600 : `.a26` `.bin`  
MSX : `.mx1` `.mx2` `.rom`  
PcEngine : `.pce` `.iso`  
GameBoy : `.gb` `.gbc`  
Sega SG1000 : `.sg`
Sega CD : `.cue`

Non esitare a condividere i tuoi titoli preferiti sul forum di recalbox !
http://blog.recalbox.fr/forums/

#### B - Scummvm games
Quando aggiungi un gioco Scummvm, deve essere in formato non compresso in una singola directory e nominato [gameshortname].scummvm

Puoi trovare la corretta denominazione dei nomi per i giochi supportati qui http://scummvm.org/compatibility/

Per esempio, per il gioco "Broken Sword 1", nella directory scumvm crea la sotto directory "Broken Sword 1" ed in questa copia il file sword1.scummvm

Il tuo gioco apparirà nel frontend, al limite puoi cambiare i suoi metadata se preferisci visualizzare diversamente il titolo.

#### C - Screenshots
Premendo Hotkey + L1 durante l'esecuzione di un emulatore puoi ottenere uno screenshot. Il rispettivo file png file viene salvato nella directory “screenshots”, accessibile via risorse di rete.  
SCondividi i tuoi screenshoot qui http://blog.recalbox.fr/forums/

#### D - Salva i tuoi salvataggi
La cartella condivisa “sauvegardes” contiene tutti i salvataggi di gioco. Puoi copiarli altrove se desideri averne un backup.

### <a name='kodi'></a>VII - Kodi Media Center
Premento il tasto  X del controller, puoi lanciare Kodi Media Center, aka XBMC. Puoi anche accedevi mediante il pulsante start e la relativa voce di menu.

Per uscire da XBMC, seleziona "QUIT" , ritornerai cosi a recalboxOS.

### <a name='troubleshooting'></a>VIII - Troubleshooting

#### A - Controllers :

- Il controller per PS3 lampeggia ma non si collega
Collega il controller via usb per 10 secondi. Successivamente scollegalo e premi il tasto Home.

- Il controller non risponde
Devi resettare il controller premendo il tasto di reset presente dietro al controller stesso, utilizzando una graffetta

#### B - Altro

- Bordi neri, immagine troppo grande
Prova ad attivare la funzione di overscan nel menu "System Setting"
Utilizza il telecomando della tua tv per accedere al menu di impostazione dell'immagine e setta questa secondo la proporzione "1:1 pixel" o "full". Se cosi non dovesse funzionare devi attivare la funzione di overscan nel file config.txt

- Schermo del PC nero
Se lo schermo del tuo pc rimane nero (collegato via hdmi o dvi) edita il file config.txt e rimuovi la linea hdmi_drive=2


#### C - Hard reset
- Se vuoi resettare il tuo sistema, collega una tastiera usb e premi il tasto Shift all'avvio. Puoi reinstallare recalboxOS da li. Tutti i tuoi dati verranno cancellati.

#### D - Root Access
- Utilizza come username `root` e password `recalboxroot` 
- Puoi collegarti tramite ssh a recalbox. 
- Puoi uscire da Emulationstation ed accedere al terminale con i tasti F4 e premendo poi ALT+F2

### <a name='recalboxconf'></a>IX - recalbox.conf

il file `recalbox.conf` è condivisso nella directory `system` è utilizzato per modificare altre impostazioni non direttamente accessibili via frontend.
Vedi [[recalbox.conf|recalbox.conf-(IT)]]
