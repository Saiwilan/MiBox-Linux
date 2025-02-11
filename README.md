# Mi Box-Linux

Mi Box S/Mi Box 4k Linux Installation

This guide walks you through installation of Linux [Armbian/Manjaro Arm or any other arm based Linux distros (make sure it has your box's dtb's)] on Mi Box S (Global) / Mi Box 4K (India) or any other Android Boxes with AMLogic S905L CPU.

Note: This is a fork of a tutorial by i12bretro ([YouTube](https://www.youtube.com/watch?v=bb8F20rgEJ4)) but even more better, updated and specific for mi box

This guide should basically work for any other boxes or boards with amlogic cpus but with correct dtb's. This guide is mainly focused and tested on my personal Mi Box 4K. Try your luck!.

# [Specs] Mi Box 4K (India), Mi Box S (Global)

https://github.com/Saiwilan/MiBox-Linux/assets/138218032/6fdc2b8c-7d22-4210-b2d0-779f2dff5b9b

Mi Box 4K, outside of India known as the Xiaomi Mi Box S. Its model number is typically "MDZ-22-AB" or "MDZ-22-AS".

### CPU: AMLogic S905L (Cortex-A53 Quad-Core 64 Bit)

**GPU: Mali-450**

**RAM: 2GB DDR3**

**Storage: 8GB eMMC**

**Operating System: Android 8.1 / 9 (may vary)**

# P**re-requisite**:

- A Mi box (of course!)
- A monitor (bruh!)
- A keyboard and a mouse
- 4Gb or larger Empty Pen drive
- An USB hub ( with external power supply preferred )
- A solid slim plastic card like guitar pick to open the box
- A tooth pick (for non mi boxes like T9 or H9 X3 boxes)
- A screwdriver
- USB Type A to Type A  (USB male to USB male) cable (optional)
- A computer (Windows/Linux/mac)
- A Linux distro image file (I’m gonna go with Armbian and Manjaro for this guide)
- 

## Downloads [Links] :

Balena etcher :  [Click Here!](https://etcher.balena.io/)

Armbian Linux Distro : [Download (Google Drive)](https://drive.google.com/file/d/1n6CZa582uJECV3lzQDtFbmbyvmOSiUSg/view?usp=sharing)

Manjaro Linux Distro : [Download (Google drive)](https://drive.google.com/file/d/1iF3KZBWze9VWiQ-4P6zYMTX9hA7TsM1h/view?usp=sharing)

Note! : original links of the distros are down and outdated, these links are from i12bretro. Comment if you got the updated links

## [Steps] Flashing and configuring Linux image :

Same for Armbian and Manjaro. I’ll go with Armbian for now

1. Download the armbian img.xz file from above
2. Download and run balena etcher
3. plugin the pen drive
4. burn the Armbian image to the pendrive
5. safely remove the pen drive and insert it again
6. Ignore/close the Windows dialogs to format the inserted pendrive
7. open the pen drive folder
8. search and open **uEnv.ini** with notepad
9. edit the FDT line to point to a working .dtb file i.e. **meson-gxl-s905x-p212.dtb**

```
# aml s9xxx
#FDT=/dtb/amlogic/meson-g12a-x96-max-no-cvbs.dtb
#FDT=/dtb/amlogic/meson-g12b-ugoos-am6-no-cvbs.dtb
#FDT=/dtb/amlogic/meson-g12b-odroid-n2.dtb
FDT=/dtb/amlogic/meson-gxl-s905x-p212.dtb
APPEND=root=LABEL=ROOTFS rootflags=data=writeback rw console=ttyAML0,115200n8 console=tty0 no_console_suspend consoleblank=0 fsck.fix=yes fsck.repair=yes net.ifnames=0
```

 **meson-gxl-s905x-p212.dtb** will work for any S905L with 2GB RAM devices.

for 1GB RAM devices **meson-gxl-s905x.dtb** should work

if you have other than 1 and 2GB ram search for dtb accordingly

1. Save and close the file
2. Safely remove Pen drive.

Note : if you don't have .ini file you must have .config file in config folder edit that.

# **Booting to Linux for the First Time :**

Note : This will not install Armbian/Manjaro in your device eMMC internal storage and will only be installed on your pendrive.

![images (1)](https://github.com/user-attachments/assets/51e1e1ca-a940-4133-abb0-db647adeb029)


1. Open up the Mi Box (DO NOT POWER IT YET !!)
2. Remove the metal plate covering the eMMC
3. Connect USB hub to it
4. Insert pendrive
5. Insert keyboard and mouse
6. Plug in HDMI monitor or TV
7. Take a screw driver and and join the metal rim and the pin shown in image (you can use a wire too)    
    
![18490850 (1)](https://github.com/user-attachments/assets/f107b9e3-d4cd-41fc-b764-01310094fab2)

    
8. Power the box on (plug in) while keeping them on
9. You will see the MI logo for a second and next Linux commands flash on your screen (you can lift that screwdriver and let it go)
10. Go through the setup process using keyboard (it doesn't have a GUI ).
11. Done!! You have your Linux up and running.

{IMAGE}

[boxes other than mi box]

Take a toothpick and insert it into headphone jack and press and hold the button inside it to boot from pendrive

for those boxes who don't have a button inside headphone jack you may have a button inside the box named reset button or a tiny hole to pick or may have different grounding pins on motherboard (google it).

# What works and what doesn't

### Major Not Working :

- Bluetooth
- Audio (works with TV’s and monitors with inbuilt speakers)
- Headphone jack
- system freezes after an hour or so even when on idle (may be in only my case but just for your info )
- internal storage not accessible in pendrive boot
- Manjaro is slow but has some useful apps ( like libreoffice ) compared to Armbian
- Don't even dream of gaming on it.

### Major working :

- WIFI
- YouTube/streaming works
- and pretty much

### Usability :

As for Armbian its unexpectedly fast considering my 10-year-old pendrive and lightweight as it has Xfce de. As for apps, you have the least amount of apps, and even does not even come with Libre Office but it's smooth anyways.

As for Manjaro it's a little bit slow but usable and comes with Libre office pre-installed.

### Use cases :

- basic typing, word processing and data entry.
- surfing internet
- learning Linux
- a cheap server
