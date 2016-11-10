---
layout: page
title: Cómo jugar a juegos multidisco de PS1 (ES)
wikiPageName: Cómo-jugar-a-juegos-multidisco-de-PS1-(ES)
menu: wiki
---

Tener tus juegos multidisco en un solo archivo es posible.

# Recuerda, debes usar tus propias imagenes ISO

Solo necesitas crear un archivo eboot que contenga tus archivos iso, bin, img con ayuda del software gratuito **psx2psp**.

Revisa el archivo` es_system_cfg`

A través de la terminal, dirigete a nano `/root/.emulationstation/es_systems.cfg`

Edítalo y revisa si las terminaciones .pbp .PBP se encuentran presentes.

`<extension>.img .IMG .pbp .PBP .bin .BIN .cue .CUE .iso .ISO</extension>`

## Creación de un archivo EBOOT:

Busca en internet el programa psx2psp v1.42, descárgalo e inícialo.

Selecciona el modo clásico, opción que encontrarás en la parte izquierda, carga las ISOS una a una. haz click en el botón "convertir" y luego espera.

Carga tus carpetas o renombra el archivo EBOOT creado en RECALBOX en la ruta `/recalbox/share/roms/psx`

## Cambiar CDs

Para cambiar un CD mientras juegas, necesitas activar 2 o 3 opciones en el menú de RetroArch.

* Abre el menú de RetroArch dentro del juego (hotkey+B por defecto)
* Dirígete a "Settings/general settings" y cambia la opción "configuration save on exit" a "on". Ten cuidado, a partir de este punto, todos los cambios que hagas en RetroArch quedarán guardados.
* Vuelve atrás, selecciona "Quit RetroArch" y regresa a tu juego.

Cuando dentro de tu juego encuentres una pantalla solicitandote que cambies de CD (swap CD), solo debes retirar el CD de forma virtual (Hotkey + atajo para la opcion "disk eject toggle"), debes cambiar de CD y luego cerrar el reproductor de disco virtual, tu juego iniciará el siguiente CD.

## CD swap para PCSX-reARMed (r22)

### Método con archivos .BIN

* Entra el menu de Retroarch (hotkey+B)
* Selecciona "Quick Menu", y luego "core disk options"
* Retira el CD virtual seleccionando la opción "disk cycle tray status"
* Selecciona el archivo que buscas (debe estar ubicado en recalbox/roms/psx) seleccionando "disk image apped""
