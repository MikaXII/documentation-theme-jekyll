---
layout: page
title: Manual (ES)
wikiPageName: Manual-(ES)
menu: wiki
---

# recalbox 3.3.X
## Manual v1.0.7

![](http://blog.recalbox.com/wp-content/uploads/2015/01/retrobox-etiquette.png)

http://www.recalbox.com

- I - [Primer uso](#first-use)
- II - [Configuración](#configuration)
 - A - [Mandos](#controllers)
   - 1 - [Mandos PS3](#ps3controllers)
    - 2 - [Mandos XBox 360](#xboxcontrollers)
    - 3 - [Añadir un mando Bluetooth](#btcontrollers)
    - 4 - [Configurar un mando](#configurecontrollers)
    - 5 - [Asignación de botones](#btnmapping)
    - 6 - [Asignación de teclado](#keyboardmapping)
    - 7 - [Mandos GPIO](#gpiocontrollers)
    - 8 - [Mandos virtuales](#virtualgamepads)
 - B - [Configuración del sistema](#system-settings)
- III - [EmulationStation](#es)
 - A - [Introducción](#es-pres)
 - B - [Configuración](#es-settings)
   - 1 - [Configuración del sistema](#es-settings-sys)
    - 2 - [Configuración de juego](#es-settings-games)
    - 3 - [Configuración de mandos](#es-settings-controllers)
    - 4 - [Configuración de interfaz](#es-settings-ui)
    - 5 - [Configuración de sonido](#es-settings-sound)
    - 6 - [Configuración de red](#es-settings-network)
 - C - [Controles](#controls)
 - D - [Favoritos](#favorites)
 - E - [Scraper](#scrapper)
- IV - [Durante la partida](#duringgame)
 - A - [Salvar la partida](#duringgame-saves)
 - B - [Comandos especiales](#duringgame-special)
- V - [Actualizaciones](#updates)
- VI - [Características de red](#network)
 - A - [Añadir tus juegos](#network-add)
 - B - [Juegos arcade](#network-arcade)
 - C - [Juegos SCUMMVM](#network-scummvm)
 - D - [Capturas de pantalla](#network-screenshots)
 - E - [Guardar tus partidas](#saves)
- VII - [Kodi Media Center](#kodi)
- VIII - [Resolución de problemas](#trouble)
 - A - [Mandos](#trouble-controllers)
 - B - [Otros](#trouble-other)
 - C - [Hard reset](#hard-reset)
 - D - [Acceso root](#root-access)
- IX - [recalbox.conf](#recalbox.conf)


## Introducción
Recalbox es un sistema que te permitirá jugar a juegos retro fácilmente.

Funciona en un mini-ordenador llamado Raspberry Pi y utiliza una serie de emuladores optimizados.

## <a name='first-use'></a>I - Primer uso
Componentes necesarios :
- Una Raspberry PI 1 o 2
- Tarjeta SD/microSD de 16GB o más
- Cable HDMI
- Adaptador de corriente micro USB **> 1.5 AMP**
- Mando USB o Bluetooth

Visita **[recalbox.com/diy](http://www.recalbox.com/diy)** para más detalles sobre la primera instalación.

Después de la [[Instalación|Instalación-(ES)]], lo primero que debes hacer es conectar la recalbox a la televisión con el cable HDMI.

Para encender la recalbox simplemente conecta el adaptador de corriente micro USB.

Muchos mandos funcionan automáticamente pero si quieres configurar directamente un mando USB, conecta un teclado USB y lee [Añadir un mando USB](#configurecontrollers)

Para apagar el sistema: pulsa el botón "Start", selecciona “SALIR” y “APAGAR EL SISTEMA”.  
Una vez hecho esto puedes desconectar la alimentación.

## <a name='configuration'></a>II - Configuración

### <a name='controllers'></a>A - Mandos
Los mandos _PS3 DualShock_ _Xbox 360_ son compatibles para uso inalámbrico. Muchos mandos **USB** y **Bluetooth** también son compatibles. Para obtener más información comprueba la [lista de periféricos compatibles](https://github.com/digitalLumberjack/recalbox-os/wiki/Compatibility-%28EN%29)

#### <a name='ps3controllers'></a>1 - Mandos de PS3
Para usar un mando inalámbrico PS3 debes disponer de un receptor bluetooth .
Debes recargar los mandos directamente de un USB, no desde la RPi. Conecta el mando **únicamente** para asociarlo a la recalbox.
Para asociar el mando de PS3 a la recalbox, conecta el mando y **espera 10 segundos**. Ahora puedes desconectar el mando y pulsar el botón Home.

Para copias asiáticas del Dualshock 3 (alias GAISA o SHANWAN) sigue las instrucciones de [[Controladores para mandos PS3|PS3-controllers-drivers-(EN)]]

Recuerda que la configuración de los mandos en Recalbox está basada en los botones de la SNES:

| mando ps3 | mando snes |
| :--------------: | :--------------: |
| x | B |
| ◯ | A |
| ⬜ | Y |
| △ | X |

#### <a name='xboxcontrollers'></a>2 - Mandos de XBox 360
Los mandos inalámbricos de Xbox 360 necesitan un receptor específico.
Si usas un mando XBox 360 con cable o inalámbrico, activa el módulo [xboxdrv en recalbox.conf](https://github.com/digitalLumberjack/recalbox-os/wiki/recalbox.conf-%28EN%29) para tener un soporte completo.

Una vez activado reinicia con tu mando o receptor inalámbrico conectado.

Recuerda que la configuración de los mandos en Recalbox está basada en los botones de la SNES:

| mando xbox | mando snes |
| :--------------: | :--------------: |
| A | B |
| B | A |
| X | Y |
| Y | X |

#### <a name='btcontrollers'></a>3- Añadir un mando Bluetooth
Para añadir un mando Bluetooth ajusta tu mando en modo emparejamiento.
Una vez hecho esto ve al menú y selecciona **Configuración de mandos**.

Selecciona **Emparejar un mando bluetooth**:
[![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/bluetooth-pair-350px.jpg)](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/bluetooth-pair.jpg)

Aparecerá una lista de los mandos detectados. Simplemente elige el tuyo y ya estará emparejado. Ahora puedes configurarlo si no es que ya lo está.

Los usuarios de **8bitdo** tienen más información en [[8bitdo en recalbox|8bitdo-on-recalbox-(EN)]]. 

#### <a name='configurecontrollers'></a>4 - Configurar un mando
Puedes conectar mandos USB a la recalbox.

La mayoría de los modelos son compatibles. Para obtener más información comprueba la [lista de periféricos compatibles](https://github.com/digitalLumberjack/recalbox-os/wiki/Compatibility-%28EN%29).

Después de conectar tu mando USB o emparejar tu mando bluetooth, pulsa START en un mando configurado previamente (o INTRO en el teclado) y selecciona “Configuración de controles”.

Ahora sigue las instrucciones. 

El último botón, el **HOTKEY**, es el botón que activará las combinaciones de botones (vease [Comandos especiales](#duringgame-special)) Se recomienda usar el **L3** (el click de joystick en los dualshock) o _**SELECT**_

Los nombres de los botones se basan en el mando de Super Nintendo:  
![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/snes-controller.jpg)

Los botones L y R (como L2, R2, L3 y R3) se basan en el mando de Playstation.
 
Ignora los botones que no estén presentes en tu mando manteniendo pulsando cualquier botón durante 2 segundos.

De vuelta en la pantalla de configuración, asigna el mando a un jugador. _¡Tu mando está configurado!_


#### <a name='btnmapping'></a>5 - Asignación de botones

Para los mandos de 6 botones (SNES, PSX, arcade, etc) los botones están asignados a los botones correspondientes del mando original.
Para los mandos de 2 botones (NES, PcEngine, GameBoy, etc) se usan los botones B y A.

#### <a name='keyboardmapping'></a>6 - Asignación de teclado
Si no has conseguido configurar ningún mando o prefieres hacerlo así, puedes conectar un teclado USB a la recalbox.
"Intro" es **START**, "Barra espaciadora" es **SELECT**, "S" es **VOLVER**, "A" es **ACEPTAR**

#### <a name='gpiocontrollers'></a>7 - Mandos GPIO
Puedes conectar tus mandos de recreativa directamente al interfaz GPIO de la Raspberry. Para obtener más detalles visita [[GPIO controllers|GPIO-controllers-(EN)]]

Puedes conectar mandos originales de PSOne, NES, SNES, MegaDrive y otros sistemas. Para obtener más detalles visita [[DB9 and Gamecon controllers|DB9-and-Gamecon-controllers-(EN)]]

#### <a name='virtualgamepads'></a>8 - Mandos virtuales
Con los [mandos virtuales](https://github.com/miroof/node-virtual-gamepads) de Miroof's puedes añadir hasta 4 mandos con tu smartphone.
Simplemente lanza el navegador de tu móvil e introduce la IP de tu recalbox y el puerto de comunicación (port=8080). Puedes obtener la IP de la recalbox en el menú de configuración [Configuración de red](#es-settings-network)

[![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/virutalgamepad_touch_zones-350px.png)](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/virutalgamepad_touch_zones.png)

Para obtener más detalles visita [[Virtual Gamepad|Virtual-Gamepad-(EN)]]

### <a name='system-settings'></a>B - Configuración del sistema
Tienes dos maneras de configurar tu recalbox. El interfaz Emulationstation ofrece muchas opciones de configuración. Para obtener más detalles ves a [Configuración del sistema EmulationStation](#es-settings-sys)

Si quieres modificar cada uno de los emuladores a tu gusto léete **[[recalbox.conf|recalbox.conf-(ES)]]**

## <a name='es'></a>III - EmulationStation

### <a name='es-pres'></a>A - Introducción

Cuando inicias el sistema recalbox lo primero que aparece es el interfaz emulationstation.
Desde aquí puedes seleccionar sistema, lanzar tus juegos y acceder a los menús de configuración.

La primera pantalla es la pantalla de sistema :

[![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/emulationstation-350px.jpg)](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/emulationstation.jpg)

Esta muestra todos los sistemas disponibles.

### <a name='es-settings'></a>B - Configuración

Pulsando Start y seleccionando la primera entrada podrás cambiar algunas de las configuraciones del sistema.
[![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/settings-350px.jpg)](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/settings.jpg)

#### <a name='es-settings-sys'></a>1 - CONFIGURACIÓN DEL SISTEMA

Desde aquí puedes acceder a **información del sistema**, **selección de idioma**, **overclock**, **actualizaciones** y **configuración de Kodi**.
Puedes modificar el overclock de tu RPi. Las velocidades de overclock para la RPi1 son, de menor a mayor: 
*NONE* < *HIGH* < *TURBO* < *EXTREM*
Extreme podría invalidar tu garantía pero es **la única** que te dará un buen rendimiento en todos los emuladores con la RPi1.

También es recomendable overclockear la RPi2 si quieres emular la N64 y obtener la mejor experiencia de juego.

#### <a name='es-settings-games'></a>2 - CONFIGURACIÓN DE JUEGO
Puedes configurar las opciones: **relación de aspecto** (16/9, 4/3), **suavizado de imagen** y **rebobinar**
La opción **rebobinar** te permite volver atrás en los juegos.
:Advertencia: _Puede ralentizar algunos emuladores (PSOne, SNES)_ si lo activas por defecto. Lo puedes activar por emulador desde [[recalbox.conf|recalbox.conf-(ES)]]

También puedes configurar fácilmente **filtros** (shaders) para tus sistemas. La opción **shader set** contiene los juegos de filtros disponibles en recalbox. La opción **scanlines** activa las lineas de barrido en todos los sistemas para simular un monitor CRT. La opción **retro** es un juego de filtros, seleccionados por la comunidad, que te ofrecen la experiencia más similar a la original en cada sistema.
Puedes obtener más información en la página [[Configuración de filtros|Shaders-configuration-(ES)]].

También puedes cambiar de filtro durante la partida usando el mando. Pulsa el [comando especial](#duringgame-special) Hotkey + R2 o Hotkey + L2 para alternar entre filtros.

#### <a name='es-settings-controllers'></a>3 - CONFIGURACIÓN DE MANDOS
Puedes configurar tus mandos.

#### <a name='es-settings-ui'></a>4 - CONFIGURACIÓN DE INTERFAZ
Aquí puedes configurar algunas opciones del interfaz. 

Puedes activar o desactivar el overscan, para evitar las bandas negras en los bordes o la imagen recortada en ciertos televisores. Puedes obtener más información al respecto en [[Overscan settings|Overscan-settings-(EN)]]
Puedes activar o desactivar el suavizado de imagen. Afecta a todos los juegos.  

#### <a name='es-settings-sound'></a>5 - CONFIGURACIÓN DE SONIDO
Aquí puedes activar o desactivar la **música de fondo**, cambiar el **volumen del sistema** y seleccionar la **salida de audio** (*auto*, *jack* o *hdmi*)
Selecciona jack para forzar la salida analógica.

#### <a name='es-settings-network'></a>6 - CONFIGURACIÓN DE RED
Aquí puedes activar y configurar el **WiFi**, el **nombre de equipo** y obtener la **IP** de la recalbox.
Teclea el SSID de tu red y la clave de red con un teclado.
Una vez valides la configuración, el WiFi estará activado.
Hay un bug conocido por el que podrías no poder introducir todos los caracteres de tu SSID o clave.
Puedes configurar directamente tu WiFi desde [[recalbox.conf|recalbox.conf-(ES)]]

### <a name='controls'></a>C - Controles

**Comandos del interfaz :**

B → Seleccionar
A → Volver
Y → Favorito
X → Lanzar Kodi
Start → Menú
Select → Opciones (reinicia el menú en caso de fallo del sistema)
R → Página siguiente
L → Página anterior

Cuando seleccionas un sistema con A, la pantalla cambia y muestra los juegos disponibles.

Cuando se está ejecutando el juego, ve a la sección *Durante la partida* para ver como volver al interfaz.

### <a name='favorites'></a>D - Favoritos

Puedes marcar un juego como favorito pulsando el botón Y. El juego aparecerá al principio de listado con una ☆ frente al nombre. Marca o desmarca con Y.
Para que tus favoritos se guarden debes apagar el sistema desde el menú de Emulationstation.

### <a name='scrapper'></a>E - Scraper
Puedes obtener información de cada uno de los juegos, como la portada y otros datos, para que aparezcan en la lista de juegos. Pulsa **Start** y ve a **Scraper**. Una vez allí sigue las instrucciones. 


## <a name='duringgame'></a>IV - Durante la partida

### <a name='duringgame-saves'></a>A - Saves 
Los emuladores permiten realizar instantáneas. Una instantánea es un guardado rápido del juego, y permite recargar el juego desde este mismo punto.

Con las instantáneas, ¡nunca más tendrás que volver a buscar un punto de salvado!

Puedes salvar más de una instantánea por juego si cambias la ranura de salvado.

Puedes crear una instantánea con **Hotkey** + **Y**


### <a name='duringgame-special'></a>B - Comandos especiales
Durante el juego, puedes ejecutar los comandos especiales.  

Pulsa **Hotkey** en el mando y uno de los siguientes botones:

Y → Guardar instantánea
X → Cargar instantánea
Start → Salir
B → Menú  
Arriba → Ranura de instantánea anterior
Abajo → Siguiente ranura de instantánea
L1 → Captura de pantalla
Derecha → Acelerar el juego
Izquierda → Rebobinar (si se ha activado)
R2 → Siguiente filtro
L2 → Filtro anterior

En FBA y MAME, pulsa Select para añadir un crédito.
En MAME, si tu Hotkey es Select, tendrás que salir con R1 + Start (para poder añadir créditos con Select)

Puedes acceder al menú de configuración de Retroarch con la combinación *Hotkey* + *B*
Si quieres configurar retroarch y guardar la configuración, selecciona "Save Settings on Exit" en el menú de retroarch. Después de hacerlo, toda la configuración que hagas en rgui se salvará.


### <a name='updates'></a>V - Actualizaciones
La actualización de recalbox se pueden llevar a cabo desde el menú de la interfaz. Configura el WiFi o conecta un cable de red a la recalbox, pulsa Start y selecciona "CONFIGURACIÓN DEL SISTEMA" con el botón A, después "ACTUALIZACIONES" y "EMPEZAR LA ACTUALIZACIÓN"

Después de la actualización el sistema se reiniciará.


## <a name='network'></a>VI - Características de red
Si has configurado la WiFi o conectado un cable de red a la recalbox, esta comparte archivos en tu red local. En tu ordenador, ve a Red en el Explorador de Windows, y selecciona la recalbox :

[![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/recalbox-network1-350px.jpg)](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/recalbox-network1.jpg)

Si no ves la recalbox en tu red prueba a introducir **\\\\RECALBOX** en la barra del explorador. Si no funciona, ve al menú __CONFIGURACIÓN DE RED__ en tu recalbox y apunta la IP.

Ahora introduce tu IP en la barra del explorador, por ejemplo **\\\\192.168.1.30**

Puedes acceder a todos los directorios compartidos de recalbox:

[![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/recalbox-network2-350px.jpg)](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/recalbox-network2.jpg)


### <a name='network-add'></a>A  - Añadir tus juegos
Simplemente copia los archivos en el directorio correspondiente. Puedes usar archivos *.zip* o ROMs sin comprimir.

¡No dudes en compartir tus juegos favoritos en el foro de recalbox!
http://blog.recalbox.com/forums/


### <a name='network-arcade'></a>B - Juegos arcade
Si quieres añadir juegos de arcade a tu recalbox lee el mini-tutorial [[Add Arcade Games|Add-arcade-games-(EN)]] y aprende cómo [[comprobar la versión de tus ROMs|Check-your-roms-version-with-clrmamepro-(EN)]].
También puedes activar la [[Neogeo Unibios|Use-Neogeo-Unibios-(EN)]] para tener más opciones en tus juegos.


### <a name='network-scummvm'></a>C - Juegos SCUMMVM
Cuando añades un juego para Scummvm, este debe estar en una carpeta descomprimida. En esta carpeta, tienes que añadir un único archivo, llamado [nombrecortodeljuego].scummvm

Puedes encontrar los nombres cortos de todos los juegos soportados en http://scummvm.org/compatibility/

Por ejemplo, si has copiado el directorio "Broken Sword 1" en el directorio de scummvm. En este directorio crea un archivo llamado sword1.scummvm

Tu juego aparecerá en el interfaz frontend, y podrás modificar sus metadatos si quieres mostrar el nombre completo. 

### <a name='network-screenshots'></a>D- Capturas de pantalla
Pulsa Hotkey + L1 durante la partida para hacer una captura de pantalla. El archivo png se guardará en el directorio “screenshots” y podrás acceder a él mediante la red.
Comparte tus mejores capturas con nosotros en http://blog.recalbox.com/forums/

### <a name='saves'></a>E - Guarda tus partidas
El directorio compartido *saves* contiene todas las partidas guardadas y las instantáneas. Puedes copiar todos los archivos si quieres ponerlos a salvo.

## <a name='kodi'></a>VII - Kodi Media Center
Pulsando el botón X en el mando, puedes lanzar Kodi Media Center, alias XBMC. También puedes acceder a Kodi pulsando Start y lanzándolo desde el menú.

Para salir de Kodi, selecciona "QUIT" en el programa, y volverás a recalboxOS.

Los mandos de juego aun no funcionan en Kodi pero puedes usar el mando de TV con soporte HDMI CEC o un smartphone con la aplicación de control remoto. Puedes obtener más detalles en el mini-tutorial [[Kodi on recalbox|Kodi-on-recalbox-(EN)]]

## <a name='trouble'></a>VIII - Resolución de problemas

### <a name='trouble-controllers'></a>A - Mandos:

- El mando de PS3 parpadea pero no se asocia
Conecta el mando a la recalbox y espera 10 segundos. Ahora puedes desconectarlo y pulsar el botón Home.

- El mando PS3 no responde
Debes reiniciar el mando presionando un pequeño botón situado en un agujerito de la parte posterior del mando usando un clip o similar.

### <a name='trouble-other'></a>B - Otros

- Bandas negras, imagen demasiado grande
En tu televisión busca el menú de imagen, y configura el tamaño de imagen a “1:1 píxel” o “completa”. Si no funciona, prueba a activar el overscan en el menú "Configuración del sistema" de recalbox.
Puedes obtener más información en [[Overscan settings|Overscan-settings-(EN)]]

- Pantalla negra en monitor de PC
Si tienes una pantalla negra en un monitor para PC (hdmi o dvi) edita el archivo config.txt (Pulsa Mayusculas durante el arranque) y comenta la linea hdmi_drive=2
Puedes obtener más información en [[Mini HowTo - Connect your recalbox to a DVI screen|Connect-your-recalbox-to-a-DVI-screen-(EN)]]  

### <a name='hard-reset'></a>C - Hard reset
- Si quieres reiniciar el sistema, conecta un teclado USB y pulsa Mayúsculas durante el arranque. Desde aquí puedes reinstalar recalboxOS. Todos los datos se borrarán.

### <a name='root-access'></a>D - Acceso root
- Utiliza el usuario `root` y la contraseña `recalboxroot` 
- Puedes conectar mediante SSH a la recalbox. 
- Puedes acceder a una terminal saliendo de emulationstation con F4 y pulsando después ALT+F2.

Puedes obtener más información en [[Mini HowTo - Root access on terminal|Root-access-on-terminal-(EN)]]  

## <a name='recalbox.conf'></a>IX - recalbox.conf
El archivo `recalbox.conf` compartido en el directorio `system` se usa para modificar configuraciones que no aparecen en el interfaz.
Consulta [[recalbox.conf|recalbox.conf-(ES)]]
