---
layout: page
title: Compilación y modificaciones (ES)
wikiPageName: Compilación-y-modificaciones-(ES)
menu: wiki
---

Pues aquí estamos. Parece que quieres compilar recalboxOS. Tal vez incluso añadirle tus propias modificaciones al al SO.
Antes de nada asegúrate de entender los diferentes proyectos que componen recalboxOS: [[recalboxOS al detalle|recalboxOS-al-detalle-(ES)]]

A continuación te enseñaré como compilar los proyectos y crear la tarjeta SD de recalboxOS a mano. Si lo único que quieres es empezar a jugar ve a las [[instrucciones de instalación|Instalación-(ES)]].

## I - Proceso de construcción
Lo primero que debes hacer es compilar el proyecto recalbox-buildroot.
Una vez hecho esto tendrás dos opciones:  
- compilar el sistema recalbox-rescue y usarlo para instalar recalbox-os.
- particionar a mano la tarjeta SD e instalar recalboxOS directamente (caso no cubierto en este tutorial)

### A - recalbox-buildroot
Para compilar el buildroot de recalbox debes instalar las siguientes dependencias:
```
sudo apt-get install build-essential git libncurses5-dev qt5-default qttools5-dev-tools mercurial libdbus-glib-1-dev texinfo zip imagemagick subversion
```
Una vez hecho esto clona el repositorio y elige la rama unified. Usaremos la variable arch para especificar la versión de RPi que tenemos (rpi1, rpi2, rpi3, odroidxu4 o x86)

```
arch=rpi2
git clone https://github.com/recalbox/recalbox-buildroot.git recalbox-buildroot-${arch}
cd recalbox-buildroot-${arch}
```

Crea la configuración de la arquitectura con un defconfig
```
make recalbox-${arch}_defconfig
```

Y ejecuta make para compilar el sistema 
```
make
```

Al finalizar la compilación debes tener en cuenta tres cosas:  
- el archivo output/images/rootfs.tar.xz es la raíz de tu sistema de archivos.
- el archivo output/images/recalbox/boot.tar.xz es la partición boot.
- el archivo output/target/recalbox/share.tar.xz es la partición share.
Ahora sigue leyendo.

### B - recalbox-rescue
Si has instalado la dependencias de recalbox-buildroot, simplemente clona y compila el proyecto recalbox-rescue:
```
git clone https://github.com/recalbox/recalbox-rescue
cd recalbox-rescue
git checkout recalbox
lupdate -no-obsolete recovery/recovery.pro
./BUILDME.sh
```

Al finalizar la compilación, los archivos del sistema recalbox-rescue que has de copiar a tu tarjeta SD están en el directorio `output/`

### C - Creando la tarjeta SD
Ahora que tenemos compilados *recalbox-buildroot* y *recalbox-rescue* es hora de crear la tarjeta SD.
Primero crearemos el directorio que simulará la raíz de la tarjeta. Después tendrás que copiar el contenido de este directorio a una tarjeta SD formateada en FAT32. Vuelve al directorio inicial y crea este directorio:
```
cd ..
mkdir SDCONTENT
```

Ahora copia el sistema recalbox-rescue:
```
cp -r recalbox-rescue/output/* SDCONTENT
```

Recalbox rescue necesita tres archivos para instalar las tres particiones de recalboxOS:
- boot.tar.xz se extraerá en la primera partición, tipo FAT32, llamada BOOT y montada como /boot en el sistema.
- root.tar.xz se extraerá en la segunda partición, tipo EXT4, llamada root y montada como / en el sistema.
- share.tar.xz se extraerá en la tercera partición, tipo FAT32, llamada SHARE y montada como /recalbox/share en el sistema.

¿Recuerdas la variable *arch* que establecimos como *rpi1*, *rpi2*, *rpi3*, *odroidxu4* o *x86* ?

Vamos a copiar los tres archivos de golpe:
```
cp recalbox-buildroot-${arch}/output/images/recalbox/*.tar.xz SDCONTENT/os/recalboxOS-${arch}/
```

OK, ahora es el momento de copiar el contenido de SDCONTENT a tu tarjeta SD.

**Arranca tu RPi y... ¡ya tienes una recalbox!**


## II - Modificación
Hay dos directorios importantes en las fuentes de recalbox-buildroot:
- `board/recalbox/fsoverlay/` es el directorio que contiene archivos que serán sustituidos o añadidos a la partición root. Por ejemplo `board/recalbox/fsoverlay/etc/fstab` sustituye el fstab original de buildroot para montar las particiones de recalbox de forma personalizada. Así que, si tienes archivos de configuración, recursos personalizados, etc, deberías incluirlos aquí.
- `package` es el directorio que contiene los descriptores de los paquetes. Hay muchos programas ya disponibles pero si quieres añadir los tuyos, hazlo aquí.

### 1 - Configuración
Puedes configurar el sistema con
```
make menuconfig
```
Este menú muestra la configuración del sistema y el selector de paquetes. La configuración se guarda en el archivo `.config`

### 2 - Añadir un paquete
Si quieres añadir un paquete puedes basarte en una existente. Vamos a usar `recalbox-emulationstation` como ejemplo:
``` 
$ ls package/recalbox-emulationstation/
Config.in  recalbox-emulationstation2-000-cmakelist.patch  recalbox-emulationstation2.mk
```

El `Config.in` lo usa buildroot para obtener información sobre el paquete: dependencias, mensajes, ...

Los archivos .patch se ejecutarán antes de la compilación.

El archivo mk contiene los comandos para configurar, construir e instalar el programa.

Una vez hayas copiado y modificado tu paquete, edita el archivo `package/Config.in`. Este lista todos los paquetes disponibles para menuconfig. Añade tu paquete a este archivo y ejecuta `make menuconfig` desde la raíz del proyecto. ¡Tu paquete aparecerá en el listado de paquetes!

Asegúrate de comprobar el nombre de tus variables. Para lo demás, la documentación de buildroot es muy clara : http://buildroot.uclibc.org/downloads/manual/manual.html
