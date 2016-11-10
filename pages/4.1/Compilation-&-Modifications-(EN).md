---
layout: page
title: Compilation & Modifications (EN)
wikiPageName: Compilation-&-Modifications-(EN)
menu: wiki
---

So here we are. You want to compile the recalboxOS. Maybe you even want to add you own components to the OS.
Be sure you understand the different projects composing the recalboxOS : [[recalboxOS detailled|recalboxOS-detailled-(EN)]]

The following will show you how to compile the projects, and create the recalboxOS sd card manually. If you just want to play, jump to [[Installation|Installation-(EN)]].


## I - Compilation process
The first thing to do is to compile recalbox-buildroot project.
Then you will have a choice :  
- compile the recalbox-rescue system and use it to install recalbox-os.
- manually create partitions on your sd card and install recalboxOS directly (not covered in this tutorial)

### A - recalbox-buildroot
To compile recalbox buildroot, install following dependencies :
```
sudo apt-get install build-essential git libncurses5-dev qt5-default qttools5-dev-tools mercurial libdbus-glib-1-dev texinfo zip default-jre imagemagick subversion
```
On a Ubuntu 16.04 fresh install, you'll need these dependencies : 

```
sudo apt-get install build-essential git libncurses5-dev libssl-dev mercurial texinfo zip default-jre imagemagick subversion hgsubversion autoconf automake bison scons libglib2.0-dev
```

Then clone the repository and select the unified branch. We will use the arch variable to specify the version of rpi we are on (rpi1, rpi2, rpi3, odroidxu4 or x86)

```
arch=rpi2
git clone https://github.com/recalbox/recalbox-buildroot.git recalbox-buildroot-${arch}
cd recalbox-buildroot-${arch}
```

Create the arch configuration with a defconfig
```
make recalbox-${arch}_defconfig
```

And use make to compile the system 
```
make
```

_Notice_: "make" allocates a lot of disk space. Make sure that you have at least 20 GB of free disk space.

At the end of the compilation, you will have 3 things to remind :  
- the file output/images/recalbox/root.tar.xz is the archive of your root filesystem.
- the file output/images/recalbox/boot.tar.xz is the archive of your boot partition.
- the file output/images/recalbox/share.tar.xz is the archive of your share partition.
See below.

### B - recalbox-rescue
If you installed recalbox-buildroot dependencies, just clone and compile the recalbox-rescue project :
```
git clone https://github.com/recalbox/recalbox-rescue
cd recalbox-rescue
git checkout dual
lupdate -no-obsolete recovery/recovery.pro
./BUILDME.sh
```

At the end of the compilation, the recalbox-rescue system files that will be copied to the SD card are in `output/` directory.

### C - Creating the SD card
Now we have both *recalbox-buildroot* and *recalbox-rescue* systems compiled we will have to create the SD card.
Let's create a directory that will fake the sdcard root. You will just have to copy all files in this directory to a FAT 32 formatted SD card. Go back on the working directory and create this folder :
```
cd ..
mkdir SDCONTENT
```

Now we can copy the recalbox-rescue system :
```
cp -r recalbox-rescue/output/* SDCONTENT
```

Recalbox rescue need 3 archives to install the recalboxOS 3 partitions:
- the boot.tar.xz will be extracted to the first partition, type FAT32, named BOOT, mounted on /boot on the system
- the root.tar.xz will be extracted to the 2nd partition, type EXT4, named root, mounted on / on the system
- the share.tar.xz will be extracted to the 3rd partition, type FAT32, named SHARE, mounted on /recalbox/share on the system

Remember our *arch* variable we set to *rpi1*, *rpi2*, *rpi3*, *odroidxu4* or *x86* ? 

Let's copy the 3 archives in one command :  
```
cp recalbox-buildroot-${arch}/output/images/recalbox/*.tar.xz SDCONTENT/os/recalboxOS-${arch}/
```

Ok now you can copy all files in SDCONTENT to your SD card !

**Boot on the RPi, and it's now a recalbox !**



## II - Modification
There are two important directories in the recalbox-buildroot sources :
- `board/recalbox/fsoverlay/` is the directory containing files that will replace or be added to the root partition. For example `board/recalbox/fsoverlay/etc/fstab` overwrites the original buildroot fstab to mount recalbox partitions on custom mountpoints. So if you have configuration files, assets etc, you will have to add them here.
- `package` is the directory containing all packages descriptor. Many software are already available, but if you want to add your own, it's here.

### 1 - Configuration
You can configure the system with 
```
make menuconfig
```
This menu show system configuration, and package selection. It saves the configuration to the `.config` file

### 2 - Adding a package
If you want to add a package, you can base yourself on an existing package. Let's take `recalbox-emulationstation` as a study case :
``` 
$ ls package/recalbox-emulationstation/
Config.in  recalbox-emulationstation2-000-cmakelist.patch  recalbox-emulationstation2.mk
```

The `Config.in` will be used by buildroot to get information on the package, dependencies, messages etc...

All .patch files will be executed before compilation.

The mk file contains the commands to configure, build, and install the software.

Once you have copied and modified your package, edit the file `package/Config.in`. It lists all available packages for the menuconfig. Add your new package to this file and then run `make menuconfig` from the project root. You will see your new package in the target package list !

Be sure to double check your variables name in files. For the rest, the buildroot documentation is very clear : http://buildroot.uclibc.org/downloads/manual/manual.html
