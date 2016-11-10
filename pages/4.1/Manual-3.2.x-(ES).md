---
layout: page
title: Manual 3.2.x (ES)
wikiPageName: Manual-3.2.x-(ES)
menu: wiki
---

# recalbox 3.2.0
## Manual v1

![](http://blog.recalbox.com/wp-content/uploads/2015/01/retrobox-etiquette.png)

http://www.recalbox.fr

- I - [Primer uso](#i---primer-uso)
- II - [Configuración](#ii---configuración)
 - A - Controladores
    - 1 - Controladores PS3
    - 2 - Controladores XBox 360
    - 3 - Añadir un controlador USB
    - 4 - Asignación de botones
    - 5 - Asignación de teclado
    - 6 - Controladores GPIO
    - 7 - Configurar Retroarch
 - B - Configuración del sistema
 - C - Configuración de sonido
 - D - Configuración de red
- III - [EmulationStation](#iii---emulationstation)
- IV - [Durante la partida](#iv---durante-la-partida)
 - A - Salvar la partida
 - B - Comandos especiales
- V - [Actualizaciones](#v---actualizaciones)
- VI - [Caraterísticas de red](#vi---características-de-red)
 - A - Añadir tus juegos
 - B - Juegos para Scummvm
 - C - Capturas de pantalla
 - D - Guarda tus partidas
- VII - [Kodi Media Center](#vii---kodi-media-center)
- VIII - [Resolución de problemas](#viii---resolución-de-problemas)
 - A - Controladores
 - B - Otros
 - C - Hard reset
 - D - Acceso root
- IX - [recalbox.conf](#ix---recalbox.conf)


### Introducción
Recalbox es un sistema que te permitirá jugar a juegos retro fácilmente.

Funciona en un mini-ordenador llamado RaspberryPi y utiliza un montón de emuladores optimizados.

### I - Primer uso
Componentes necesarios :
- Una Raspberry PI 1 o 2
- Cable HDMI
- Adaptador de corriente micro USB > 1.5 AMP
- Controlador USB o PS3

Lo primero que debes hacer es conectar la recalbox a la televisión con el cable HDMI.

Para encender la recalbox simplemente conecta el adaptador micro USB.

Si quieres configurar directamente un controlador USB, conecta un teclado USB y lee [Añadir un controlador USB](#3---add-an-usb-controller)

Para apagar el sistema: pulsa el botón "Start", selecciona “QUIT” y “SHUTDOWN SYSTEM”.  
Una vez hecho esto puedes desconectar el cable.

### II - Configuración

La recalbox viene con dos controladores inalámbricos. Los controladores USB, Xbox 360 y PlayStation 3 DualShock son compatibles.


#### A - Controladores
Los controladores inalábricos PS3 dualshock y Xbox están soportados.

##### 1 - Controladores de PS3
Debes disponer de un receptor bluetooth para usar un controlador inalámbrico PS3.
Debes recargar los controladores directamente de un USB. Conecta el controlador únicamente para asociarlo a la recalbox.
Para asociar el controlador de PS3 a la recalbox, conecta el controlador y espera 10 segundos. Ahora puedes desconectar el controlador y pulsar el botón Home.


##### 2 - Controladores de XBox 360
Si usas un controlador XBox 360 con cable o inalámbrico, activa el módulo [xboxdrv en recalbox.conf](https://github.com/digitalLumberjack/recalbox-os/wiki/recalbox.conf-%28EN%29) para tener un soporte completo.

Reinicia con tu controlador conectado y a jugar.

##### 3 - Añadir un controlador USB
Puedes conectar controladores USB a la recalbox.

La mayoría de los modelos son compatibles.

Después de conectar tu controlador USB, pulsa START en un controlador configurado previamente (o INTRO en el teclado) y selecciona “Configure Inputs”.

Ahora sigue las instrucciones. Si no tienes un botón que puedas usar como HotKey, asígnala al botón Select.

Los nombres de los botones se basan en el controlador de Super Nintendo:  

![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/snes-controller.jpg)
 
De vuelta en la pantalla de configuración, asigna el controlador a un jugador. ¡Tu controlador está configurado!


##### 4 - Asignación de botones

Para los controladores de 6 botones (SNES, PSX, arcade, etc) los botones están asignados a los botones correspondientes del controlador original.
Para los controladores de 2 botones (NES, PcEngine, GameBoy, etc) se usan los botnes B y A.

##### 5 - Asignación de teclado
Si no has conseguido configurar ningún controlador, puedes conectar un teclado USB a la recalbox.
"Intro" es START, "Barra espaciadora" es SELECT, "Q" es BACK, "S" es OK

##### 6 - Controladores GPIO
Puedes conectar tus mandos de recreativa directamente al interfaz GPIO de la Raspberry. Activa los controladores GPIO en el archivo [[recalbox.conf|recalbox.conf-(ES)]].

![](https://github.com/DigitalLumberjack/mk_arcade_joystick_rpi/raw/master/wiki/images/mk_joystick_arcade_GPIOsb+.png)

Más información en https://github.com/DigitalLumberjack/mk_arcade_joystick_rpi

Los controladores Marqs DB9 y gamecon también están soportados. Revisa [[recalbox.conf|recalbox.conf-(ES)]]

##### 7 - Configurar Retroarch
Puedes acceder al menú de configuración de Retroarch con la combinación *Hotkey* + *B*
Si quieres configurar retroarch y guardar la configuración, selecciona "Save Settings on Exit" en el menú de retroarch. Después de hacerlo, toda la configuración que hagas en rgui se salvará.

#### B - Configuración del sistema
Pulsando Start y seleccionando la primera entrada podrás cambiar algunas de las configuraciones del sistema.  
Puedes activar o desactivar el overscan, para evitar las bandas negras en los bordes o la imagen recortada en ciertos televisores.  
Puedes activar o desactivar el suavizado de imagen. Afecta a todos los juegos.  
Puedes modificar el overclock de tu RPi1. Las velocidades de overclock son, en orden, NONE < HIGH < TURBO < EXTREM. Extrem podría invalidar tu garantía pero es la única que te dará un buen rendimiento en todos los emuladores.
Puedes seleccionar el formato de los juegos (16/9 o 4/3)

#### C - Configuración de sonido
Puedes seleccionar el volumen del sistema y el dispositivo de salida en la configuración de sonido. Selecciona jack para forzar la salida analógica.

#### D - Configuración de red
Puedes activar el WiFi y establecer tu conexión de red en la configuración de red.  
Teclea el SSID de tu red y la clave de red con un teclado.
Una vez valides la configuración, el WiFi estará activado.
Hay un bug conocido por el que podrías no poder introducir todos los caracteres de tu SSID o clave.
Configura directamente tu WiFi desde [[recalbox.conf|recalbox.conf-(ES)]]

### III - EmulationStation

Cuando inicias el sistema recalbox aparece el interfaz Emulationstation.
Puedes seleccionar tus sistemas y lanzar los juegos desde aquí.

La primera pantalla es la pantalla de sistema: 

![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/emulationstation.jpg)


Esta muestra todos los sistemas disponibles.

Cuando seleccionas un sistema con A, la pantalla cambia y muestra los juegos disponibles.

Cuando se está ejecutando el juego, ve a la sección *Durante la partida* para ver como volver al interfaz.


**Comandos del interfaz :**

A -> Select  
B -> Back  
Start -> Menu  
Select -> Options  
R -> Next Page   
L -> Previous Page  


### IV - Durante la partida

#### A - Salvar la partida
Los emuladores permiten realizar instantáneas. Una instantánea es un guardado rápido del juego, y permite recargar el juego desde este mismo punto.

Con las instantáneas, ¡nunca más tendrás que volver a buscar un punto de salvado!

Puedes salvar más de una instantánea por juego si cambias la ranura de salvado.


#### B - Comandos especiales
Durante el juego, puedes ejecutar los comandos especiales.  

Pulsar la hotkey en el controlador y uno de los siguientes botones:

Y -> Guardar instantánea
X -> Cargar estado
Start -> Salir
B -> Menú  
Up -> Ranura de instantánea anterior
Down -> Siguiente ranura de instantánea
L1 -> Captura de pantalla
Right -> Acelerar el juego


En FBA y Mame, pulsa Select para añadir un crédito.
En Mame, si tu Hotkey es Select, tendrás que salir con R1 + Start (para poder añadir créditos con Select)``

### V - Actualizaciones
La actualización de recalbox se pueden llevar a cabo desde el menú de la interfaz. Conecta un cable de red a la recalbox, pulsa Start y selecciona "Update" con el botón A.

Después de la actualización el sistema se reiniciará.


### VI - Características de red
Si conectas un cable de red a la recalbox, esta comparte archivos en tu red local. En tu ordenador, ve a Red en el Explorador de Windows, y selecciona la recalbox :

![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/partagereseau-recalbox.jpg)



Puedes acceder a todos los directorios compartidos de recalbox:

![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/partagereseau.jpg)



#### A - Añadir tus juegos
Simplemente copia los archivos en el directorio correspondiente.  
Debes descomprimir los archivos antes de copiarlos.

Esta es la lista de archivos soportados :

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

¡No dudes en compartir tus juegos favoritos en el foro de recalbox!
http://blog.recalbox.fr/forums/

#### B - Juegos para Scummvm
Cuando añades un juego para Scummvm, este debe estar en una carpeta descomprimida. En esta carpeta, tienes que añadir un único archivo, llamado [nombrecortodeljuego].scummvm

Puedes encontrar los nombres cortos de todos los juegos soportados en http://scummvm.org/compatibility/

Por ejemplo, si has copiado el directorio "Broken Sword 1" en el directorio de scummvm. En este directorio crea un archivo llamado sword1.scummvm

Tu juego aparecerá en el interfaz frontend, y podrás modificar sus metadatos si quieres mostrar el nombre completo. 

#### C - Capturas de pantalla
Pulsa Hotkey + L1 durante la partida para hacer una captura de pantalla. El archivo png se guardará en el directorio “screenshots” y podrás acceder a él mediante la red.

Comparte tus mejores capturas con nosotros en http://blog.recalbox.fr/forums/

#### D - Guarda tus partidas
El directorio compartido “sauvegardes” contiene todas las partidas guardadas y las instantáneas. Puedes copiar todos los archivos si quieres ponerlos a salvo.

### VII - Kodi Media Center
Pulsando el botón X en el controlador, puedes lanzar Kodi Media Center, alias XBMC. También puedes acceder a Kodi pulsando Start y lanzándolo desde el menú.

Para salir de Kodi, selecciona "QUIT" en el programa, y volverás a recalboxOS.

### VIII - Resolución de problemas

#### A - Controladores:

- El controlador de PS3 parpadea pero no se asocia
Conecta el controlador a la recalbox y espera 10 segundos. Ahora puedes desconectarlo y pulsar el botón Home.

- El controlador no responde
Debes reiniciar el controlador presionando un pequeño botón situado en un agujerito de la parte posterior del controlador usando un clip o similar.

#### B - Otros

- Bandas negras, imagen demasiado grande
Prueba a activar el overscan en el menú "System Settings" de recalbox.
En tu televisión busca el menú de imagen, y configura el tamaño de imágen a “1:1 pixel” o “completa”. Si no funciona, debes activar el overscan en el config.txt del sistema.

- Pantalla negra en monitor de PC
Si tienes una pantalla negra en un monitor para PC (hdmi o dvi) edita el archivo config.txt (Pulsa Mayusculas durante el arranque) y comenta la linea hdmi_drive=2


#### C - Hard reset
- Si quieres reiniciar el sistema, conecta un teclado USB y pulsa Mayúsculas durante el arranque. Desde aquí puedes reinstalar recalboxOS. Todos los datos se borrarán.

#### D - Acceso root
- Utiliza el usuario `root` y la contraseña `recalboxroot` 
- Puedes conectar mediante SSH a la recalbox. 
- Puedes acceder a una terminal saliendo de emulationstation con F4 y pulsando después ALT+F2.  

### IX - recalbox.conf
El archivo `recalbox.conf` compartido en el directorio `system` se usa para modificar configuraciones que no aparecen en el interfaz.
Consulta [[recalbox.conf|recalbox.conf-(ES)]]
