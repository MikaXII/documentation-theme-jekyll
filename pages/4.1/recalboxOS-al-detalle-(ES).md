---
layout: page
title: recalboxOS al detalle (ES)
wikiPageName: recalboxOS-al-detalle-(ES)
menu: wiki
---

**recalboxOS** es un sistema de código abierto. Es una distribución basada en Linux, optimizada para el procesador ARM de la RaspberryPI.

## Buildroot
**recalboxOS** se compila con Buildroot.

Buildroot es una herramienta fácil, sencilla y eficiente para generar mediante compilación cruzada sistemas Linux empotrados. Esta compila tanto el sistema como el software de recalboxOS desde las fuentes y crea los archivos que se copiarán en tu tarjeta SD durante la instalación.

Buildroot crea un sistema Linux minimalista, únicamente con lo que tú quieres para tu sistema.
Por esta razón recalboxOS no tiene ni gestor de paquetes, ni compilador, ni cabeceras, ni ...

## Proyectos
**recalboxOS** es el proyecto principal que aglutina los tres sub-proyectos que componen el sistema:

- **recalbox-buildroot** :
https://github.com/digitalLumberjack/recalbox-buildroot (rama recalbox)
El proyecto recalbox-buildroot es el sistema buildroot. Este crea todo el SO Linux que correrá en tu recalbox.
Puedes compilar este proyecto y copiar los archivos resultantes a una tarjeta SD formateada para ejecutar el sistema en una raspberryPi. Pero hay una manera mejor de hacerlo llamada recalbox-rescue.

- **recalbox-rescue** :
https://github.com/digitalLumberjack/recalbox-rescue (rama recalbox)
Basado en el impresionante NOOBS del equipo de RaspberryPi, recalbox rescue te permite instalar recalboxOS fácilmente y tener una partición de rescate en tu tarjeta SD. Se trata de otro SO minimalista que, descarga recalboxOS, formatea la tarjeta SD e instala el sistema por ti.
Además comprueba si existe una nueva versión disponible en la red antes de instalarse en la tarjeta SD.

- **recalbox-emulationstation** :
https://github.com/digitalLumberjack/recalbox-emulationstation/tree/recalbox-buildroot
Basado en el increible emulationstation 2 de Aloshi, el interfaz ha sido ligeramente modificado para soportar música de fondo en formato ogg, selección de idioma, actualizaciones y la configuración de mandos.

- **recalbox-configgen** :
https://github.com/digitalLumberjack/recalbox-configgen
La herramienta para configurar emuladores automáticamente.

Si quieres saber más y aprender cómo compilar y modificar recalboxOS, ve a [[Compilación y modificaciones|Compilación-y-modificaciones-(ES)]]

## Particiones
RecalboxOS está configurado para funcionar en tres particiones :
- La primera partición, de tipo FAT32, llamada BOOT, montada en /boot dentro del sistema, contiene los archivos de arranque.
- La segunda partición, de tipo EXT4, llamada root, montada en / dentro del sistema, contiene el sistema.
- La tercera partición, de tipo FAT32, llamada SHARE, montada en /recalbox/share dentro del sistema, contiene las roms, BIOS, partidas salvadas y capturas de pantalla.
