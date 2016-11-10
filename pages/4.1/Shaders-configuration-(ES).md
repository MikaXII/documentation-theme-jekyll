---
layout: page
title: Shaders configuration (ES)
wikiPageName: Shaders-configuration-(ES)
menu: wiki
---

### I - Introducción

Los Shaders(sombreados) y los Filtros pueden cambiar la imagen que obtienes mientras usas un emulador.
A menudo son usados para obtener una apariencia "retro", Similar a los viejos televisores de tubo en los que soliammos jugar.

Los diferentes archivos que encontrarás en Recalbox son:

* **glsl**: El Shader (sombreado) en si mismo.
* **glsp**: El Shader predefinido. Puede conbinarse con diferentes Shaders.
* •	/recalbox/share_init/system/configs/shadersets/**xxx.cfg**: Los archivos de configuración para los Shader sets.

### II - Shader sets

Gracias a los shader sets, puedes configurar shaders para todos tus sistemas con solo una opción.
Estos sets son creados por la comunidad, y están optimizados para cada nueva versión de Recalbox.

Sets disponibles: 
* **Scanlines**: Habilita Scanlines (lineas de escaneado en televisores antiguos) en todos los emuladores.
* **Retro**: Selecciona los "mejores" shaders para cada sistema, escogidos por la comunidad. Esto te proporcionará experiencia mas cercana a la original.
* **nonne**: Sin Shaders

Puedes escoger el **shaderset** que quieres habilitar, en el menú de EmulationStation "GAME SETTINGS", o directamente en
[[recalbox.conf|recalbox.conf-(ES)]], con la opción de global.shaderset .

### III - Custom Shaders
puedes combinar el asombroso poder de los **shader sets** con la increible capacidad de customización de recalbox.conf .
El global.shaderset puede usarse como shader base para cada emulador. Entonces puedes cambiar el shader preset de un sistema con la opción systemname.shader

por ejemplo, si yo quiero los mejores shaders para todos mis emuladores, pero no quiero shaders para gameboy, quiero ademas un preset de shaders existente para megadrive, y un shader custom para snes:
```
 # Establecer el shader set retro para todos los emuladores, now ahora se que esta es la mejor opción
global.shaderset=retro
# Pero para mi, mi gameboy se ve mejor sin shaders
gb.shaders=
# usaremos el existente 4xbr_retro.glslp shader para megadrive
megadrive.shaders=/recalbox/share_init/shaders/4xbr_retro.glslp
# Y ahora quiero usar mis propios shaders para snes
snes.shaders=/recalbox/share/shaders/custom/snes.glslp
```
Puedes cambiar los shaders mientras juegas usando simplemente tu control. Usa los [comandos especiales](https://github.com/digitalLumberjack/recalbox-os/wiki/Manual-%28ES%29#duringgame-special) **Hotkey + R2** o **Hotkey + L2** para visualizar el proximo o el anterior juego de shaders.

### IV - Screenshots
Sin shaders :  
![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/shaders/nes-no-filter.png)

Con el retro shader set :  
![](https://github.com/digitalLumberjack/recalbox-os/blob/master/wiki/images/shaders/nes-caligari-115.png)

