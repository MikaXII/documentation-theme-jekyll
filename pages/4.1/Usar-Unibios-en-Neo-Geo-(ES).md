---
layout: page
title: Usar Unibios en Neo Geo (ES)
wikiPageName: Usar-Unibios-en-Neo-Geo-(ES)
menu: wiki
---

##Para que sirve Unibios:

* Cambiar la región del sistema (Europa/USA/Japón) y el modo de sistema (AES/MVS)
* Acceder a las configuraciones del sistema, para poder cambiar la dificultad/ número de vidas/Tiempo-etc
* Acceso a una base de datos de trucos
*Acceso a reproductor de música.....y mucho más!

##Como instalarla en PIFBA:

1. Descargala aquí (versión 3.2): http://unibios.free.fr/download.html
2. Extrae el archivo descargado y renombralo **asia-s3.rom**
3. Abre tu archivo neogeo.zip (archivo BIOS), debería haber un archivo asia-s3.rom dentro, respaldalo en caso de cualquier insidente.
4. Inserta el nuevo archivo asia-s3.rom dentro del archivo neogeo.zip reemplazando al anterior.
5. Ahora carga el archivo neogeo.zip dentro de las carpetas \bios y \finalburnalpha

##Cómo instalarla en FBA_libretro:

Abre un juego y accede al menu de Retroarch (Hotkey + B)

Dirígete a
> Quick menu > unibios

Y establece la opción

>Neo geo mode > unibios

##Uso:

###Para PIFBA
* Inicia cualquierjuego de neogeo, verás la nueva pantalla de inicio UNIVERSE BIOS v3.2
* Durante esta pantalla de inicio, mantén presionado B+X+Y para las configuraciones de modo y región, o mantén presionado A+B+X para el menú de cambio de configuraciones
* Para acceder al menú durante el juego, mantén presionado B+X+Y+START al mismo tiempo

###Para FBA libretro

* Inicia cualquier juego de NEO-GEO, verás la pantalla de inicio de UNIVERSE BIOS
* Durante esta pantalla, mantén apretado C + B + A ( XBA) para cambio de región - Para salir presiona C
* Para acceder al menú de juego, manten precionado C + B + A (XBA) + START al mismo tiempo
* Para acceder al menú de configuraciones en FBA Libreto, Durante la pantalla de inicio UNIVEESE BIOS, mantén presionado A+X+Y

##Configurando los juegos de NEO-GEO : 

<a href="http://www.zimagez.com/zimage/retroarch-1108-152444.php" target="_blank" title="Visionner l'image"><img src="http://www.zimagez.com/miniature/retroarch-1108-152444.png" alt="Visionner l'image" /></a>

Para activar la sangre : Region Japan / Mode arcade

slot metal slug

<a href="http://www.zimagez.com/zimage/retroarch-1108-152450.php" target="_blank" title="Visionner l'image"><img src="http://www.zimagez.com/miniature/retroarch-1108-152450.png" alt="Visionner l'image" /></a>

blood > on

<a href="http://www.zimagez.com/zimage/retroarch-1108-152456.php" target="_blank" title="Visionner l'image"><img src="http://www.zimagez.com/miniature/retroarch-1108-152456.png" alt="Visionner l'image" /></a>

Presiona C para salir.

### BIOS
 Neo Geo requiere un archivo BIOS neogeo.zip. Debes ubicarlo en la misma carpeta que tus roms de NEO-GEO
 
```shell
/recalbox/share/roms/neogeo
or
/recalbox/share/roms/fba_libreto
or
/recalbox/share/roms/fba
```

EStos son todos los archivos dentro de una BIOS de NEO-GEO verificada

```shell
000-lo.lo
asia-s3.rom
japan-j3.bin
neo-geo.rom
ng-lo.rom
ng-sfix.rom
ng-sm1.rom
sfix.sfix
sm1.sm1
sp-1v1_3db8c.bin
sp-45.sp1
sp-e.sp1
sp-j2.sp1
sp-s.sp1
sp-s2.sp1
sp-u2.sp1
sp1.jipan.1024
uni-bios_1_0.rom
uni-bios_1_1.rom
uni-bios_1_2.rom
uni-bios_1_2o.rom
uni-bios_1_3.rom
uni-bios_2_0.rom
uni-bios_2_1.rom
uni-bios_2_2.rom
uni-bios_2_3.rom
uni-bios_2_3o.rom
uni-bios_3_0.rom
uni-bios_3_1.rom
vs-bios.rom
```
 
