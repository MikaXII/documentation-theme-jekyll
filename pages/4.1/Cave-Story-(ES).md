---
layout: page
title: Cave Story (ES)
wikiPageName: Cave-Story-(ES)
menu: wiki
---

Cave story es un juego de plataformas de distribución libre lanzado el año 2004 para PC,revisa el siguiente [link](http://www.cavestory.org/) para mas información.

## Para la versión 3.2.11

**Primero:**

Necesitas editar el archivo emulatorlauncher.sh:

`nano /recalbox/scripts/emulatorlauncher.sh`

Y añadir al final:
```
if [[ "$emulator" == "nxengine" ]]; then  
    /recalbox/scripts/runcommand.sh 2 "$retroarchbin -L $retroarchcores/nxengine_libretro.so --config /recalbox/configs/retroarch/retroarchcustom.cfg \"$1\""  
fi  
```
**Segundo:**
Necesitas editar el archivo es_system.cfg

`nano /root/.emulationstation/es_systems.cfg`

Y añadir justo antes de `</systemList>`

```
<system>  
        <name>Ports</name>  
        <fullname>Ports</fullname>  
        <path>/recalbox/share/roms/ports/</path>  
        <extension>.exe .EXE .sh .SH</extension>  
        <command>/recalbox/scripts/emulatorlauncher.sh %ROM% "nxengine"</command>  
        <platform>ports</platform>  
        <theme>ports</theme>  
</system>  
```

**Tercero:**
Añadir los datos del directorio de Cave Story en la carpeta de ports a través de scp o winscp, para hacerlo:

1. Ve a http://www.cavestory.org/

2. Descarga la versión en inglés para windows (pre-parchada) comprimida en .zip

3. Extrae el archivo .zip a una carpeta llamada cave_story

4. Cambia el nombre del archivo DoConfig.exe a DoConfig.exe.old

5. Carga la carpeta completa a Recalbox en ` /recalbox/share/roms/ports/` tal vez debas crear la carpeta ports primero

6. Reinicia tu Recalbox y listo


##Para la versión 3.3.0

Añadir los datos del directorio de Cave Story a la partición "Share" a través de scp o winscp, para hacerlo:

1. Ve a http://www.cavestory.org/

2. Descarga la versión en inglés para windows (pre-parchada) comprimida en .zip

3. Extrae el archivo .zip a una carpeta llamada cave_story

4. Cambia el nombre del archivo DoConfig.exe a DoConfig.exe.old

5. Carga la carpeta completa a Recalbox en ` /recalbox/share/roms/cavestory/` Utilizando winscp en Windows

6. Reinicia tu Recalbox y listo
