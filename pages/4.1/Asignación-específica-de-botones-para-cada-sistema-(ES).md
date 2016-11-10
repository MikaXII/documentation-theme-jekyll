---
layout: page
title: Asignación específica de botones para cada sistema (ES)
wikiPageName: Asignación-específica-de-botones-para-cada-sistema-(ES)
menu: wiki
---

Existen dos formas de personalizar la configuración de controles de forma específica para cada sistema:

## Cambiar los botones asignados de RetroPad  a los controles del sistema.

Este metodo solo funcionará a partir de Recalbox 4 (por verificar)

Este es el método mas facil. Te permitirá seguir utilizando los botones ya configurados en EmulationStation, pero simplemente cambiarás el orden.

* Comienza abriendo cualquier juego del sistema que deseas cambiar
* Abre el menú de Libretro utilizando _Hotkey + B_
* Dirígete a _Quick Menu>Controls_
* Aquí puedes asignar los diferentes botones al control del sistema elegido.
* Una vez terminado no olvides seleccionar _Save Core Remap File_ o tu configuración se perderá en cuanto salgas del juego. 
Tambien puedes seleccionar guardar un mapeado especial para un juego específico lo deseas.

## Cambiar completamente la configuración de controles de Libretro

Si deseas configurar el mapeado de tu control para un nucleo de Libretro, puedes crear un archivo de configuración y utilizar la opción de [recalbox.conf](recalbox.conf (ES))

`[system].configfile=/path/to/my/configfile.cfg`

Esto significa que el sistema tendrá su propio archivo de configuración, por lo que la opción configgen de Recalbox no funcionará más para este sistema.

1. Abre un juego del sistema que deseas configurar
2. Abre el menú (Hotkey + B) y dirígete a "Settings", y luego a "input user 1 binds"
3. Reconfigura todos los controles, mantén un teclado cerca tuyo en caso de que el control no responda a tu configuración (W aceptar y X cancelar)
4. Dirígete a "input hotkey binds" y configura todas configuraciones con la tecla HotKey
5. Retrocede al menú principal de Retroarch y selecciona "Save new Config" ( la nueva configuración se guardará bajo el nombre [system]_libretro.cfg) 
6. [Conéctate como root](Acceso root en terminal (ES)) y renombra el archivo de configuración a un nombre que te sea facil de recordar, por ejemplo para NEO-GEO:

`mv /recalbox/configs/retroarch/fba_libretro.cfg /recalbox/configs/retroarch/inputs/neogeocustom.cfg`

7. Modifica el archivo recalbox.conf añadiendo la siguiente linea, que sobreescribirá la configuración por defecto del sistema por una nueva. Esto sobreescribirá todas tus configuraciones (shaders, cheats, rebobinado, etc)

`neogeo.configfile=/recalbox/configs/retroarch/inputs/neogeocustom.cfg`
