# [How To] Mi box 4k linux

# Guide WIP.

# MiBox-Linux

[How To] Mi Box S/Mi Box 4k Linux Installation

This guide walks you through installation of Linux [Armbian/Manjaro Arm or any other arm based linux distros (make sure it has your box's dtb's)] on Mi Box S (Global) / Mi Box 4K (India) or any other Android Boxes with AMLogic S905L CPU.

Note: This is a fork of a tutorial by i12bretro ([YouTube](https://www.youtube.com/watch?v=bb8F20rgEJ4)) but even more better, updated and specific for mi box

This guide should basically work for any other boxes or boards with amlogic cpus but with correct dtb's. But this guide is mainly focused and tested on my personal Mi Box 4K. Try your luck!.

# [Specs] Mi Box 4K (India), Mi Box S (Global)

![image](https://github.com/Saiwilan/MiBox-Linux/assets/138218032/f6f5d9ff-ceb5-42a8-ac33-d9efaa821281)


Mi Box 4K, outside of india known as the Xiaomi Mi Box S. Its model number is typically "MDZ-22-AB" or "MDZ-22-AS.

### CPU: AMLogic S905L (Cortex-A53 Quad-Core 64 Bit)

GPU: Mali-450

RAM: 2GB DDR3

Storage: 8 GB eMMC

Operating System: Android 8.1 / 9 (May Varry)

# **Pre-requisite**:

- A Mi box (ofcourse!)
- A monitor (bruh!)
- A keyboard and a mouse
- 4Gb or larger Pendrive
- Usb hub (with external power supply preferable)
- A solid slim plastic card like guitar pick to open the box
- a tooth pick (for non mi boxes like T9 or H9 X3 boxes)
- a screwdriver
- USB Type A to Type A  (usb male to usb male) cable (optional)
- A computer (Windows/Linux/mac)
- A Linux distro image file (I’m gonna go with armbian and manjaro for this guide)
- Basic linux knowledge and patience :) 

## [Links] Downloads :

Balena etcher :  [Click Here!](https://etcher.balena.io/)

Armbian Linux Distro : [Download (Google Drive)](https://drive.google.com/file/d/1n6CZa582uJECV3lzQDtFbmbyvmOSiUSg/view?usp=sharing)

Manjaro Linux Distro : [Download (Google drive)](https://drive.google.com/file/d/1iF3KZBWze9VWiQ-4P6zYMTX9hA7TsM1h/view?usp=sharing)

pick anyone.

Note! : original links of the distros are down and outdated, these links are from i12bretro comment if you got the updated links

## [Steps] Flashing and configuring Linux image :

Same for armbian and manjaro. I’ll go with armbian for now

1. Download the armbian img.xz file from above
2. Download and run balena etcher
3. plugin the pendrive
4. burn the armbian image to the pendrive
5. safely remove the pendrive and insert it again
6. Ignore/close the Windows dialogs to format the inserted pendrive
7. open the pendrive folder
8. search and open **uEnv.ini** with notepad
9. edit the FDT line to point to a working .dtb file i.e. **meson-gxl-s905x-p212.dtb**

for armbian :

```

# aml s9xxx
#FDT=/dtb/amlogic/meson-g12a-x96-max-no-cvbs.dtb
#FDT=/dtb/amlogic/meson-g12b-ugoos-am6-no-cvbs.dtb
#FDT=/dtb/amlogic/meson-g12b-odroid-n2.dtb
FDT=/dtb/amlogic/meson-gxl-s905x-p212.dtb
APPEND=root=LABEL=ROOTFS rootflags=data=writeback rw console=ttyAML0,115200n8 console=tty0 no_console_suspend consoleblank=0 fsck.fix=yes fsck.repair=yes net.ifnames=0

```

for manjaro :

```
# For AML
FDT=/dtbs/amlogic/meson-gxl-s905x-p212.dtb
APPEND=root=LABEL=ROOT_MNJRO rootflags=data=writeback rw console=ttyAML0,115200n8 console=tty0 no_console_suspend consoleblank=0 fsck.fix=yes fsck.repair=yes net.ifnames=0 bootsplash.bootfile=bootsplash-themes/manjaro/bootsplash
```

 **meson-gxl-s905x-p212.dtb** will work for any S905L with 2GB RAM devices.

for 1GB RAM devices **meson-gxl-s905x.dtb** should work

if you have other than 1 and 2GB ram search for dtb accordingly

10. Save and close the file
11. safely remove Pendrive.

# **Booting to Linux for the First Time :**

Note : This will not install armbian/manjaro in your device eMMC inernal storage and will only be installed on your pendrive.

**[Grounding Method]**

1. Open up the Mi Box (DO NOT POWER IT YET !!)
2. remove the metal plate covering the eMMC
3. connect usb hub to it
4. insert pendrive
5. insert keyboard and mouse
6. plug in hdmi monitor or TV
7. take a screw driver and and join the metal rim and the pin shown in image (you can use a wire too)       **{IMAGE}**
8. power the box on (plug in) while keeping them on
9. you will see the mi box logo for a second and next linux commands flash on your screen (you can lift that screwdriver and let it go)
10. Go through the setup process using keyboard (it dosen’t have a GUI ).
11. Done!! You have your Linux up and running.

{IMAGE}

[boxes other than mi box]

take a toothpick and insert it into headphone jack and press and hold the button inside it to boot from pendrive

for those boxes who dont have a button inside headphone jack you may have a button inside the box named reset button or a tiny hole to pick or may have different grounding pins on mb (google it).

# What works and what dosen't

### Major Not Working :

- Bluetooth
- Audio (works with TV’s and monitors with inbuilt speakers)
- Headphone jack
- system freezes after an hour or so even when on idle (may be in only my case but for info )
- internal storage not accessible in pendrive boot
- manjaro is slow but has some useful apps compared to armbian
- Dont even dream of gaming on it.

### Major working :

- WIFI
- Youtube/streaming works
- and pretty much

### Usability :

As for armbian its unexpectedly fast considering my 10 year old pendrive and lightweight as it has xfce de. As for apps you have a least amount of apps and does not even come with Libre office but its smooth anyways.

As for manjaro its a little bit slow but usable and comes with Libre office pre installed.

### Use cases :

- basic typing, word processing and data entry.
- surfing internet
- learning linux
- a cheap server
- personal portable cpu kinda
- small media box
