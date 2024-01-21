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

# P**re-requisite**:

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

## [Links] Downloads :

Balena etcher :  [Click Here!](https://etcher.balena.io/)

Armbian Linux Distro : [Download (Google Drive)](https://drive.google.com/file/d/1n6CZa582uJECV3lzQDtFbmbyvmOSiUSg/view?usp=sharing)

Manjaro Linux Distro : [Download (Google drive)](https://drive.google.com/file/d/1iF3KZBWze9VWiQ-4P6zYMTX9hA7TsM1h/view?usp=sharing)

pick any one.

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
