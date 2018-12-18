+++
title = "HOWTO: Host a samba-share on a Raspberry Pi"
date = "2018-12-18T23:59:28+01:00"
draft = true

+++
__The problem__: Having to carry your external HDD around the house, or using it on different PCs at the same time.
__The solution__: Use a Raspberry Pi to share your HDD in your local network via the CIFS/SMB/SAMBA protocol. This is going to be usable from all major operating systems, including Windows.

[Further down](#technologies) I have explained my choice of technologies used in this how-to.

__Let's get started.__

### What do I need?

- [Raspberry Pi 1, 2 or 3](https://www.raspberrypi.org)
- external HDD with USB and power adaptor OR
- external HDD with USB and an USB hub with power adaptor
- microSD card with at least 256MiB
- An HDMI screen and a USB keyboard for initial configuration
- A stable ethernet connection, preferably wired

Note that I will explain the initial configuration of the SD card and the HDD assuming a Linux computer. It is however not particularly difficult to do this with Windows. It just works differently.

### What do I have to do?

#### Setup your SD card

First you have to download the [latest image](https://alpinelinux.org/downloads/) of Alpine Linux. If you plan to use a Raspberry Pi 1 or 2, use the armhf image or the aarch64 one, if you plan to use a Raspberry Pi 3. 

> fdisk SD card preparation <

After you've done that, you can extract your downloaded image on your freshly formatted SD card. For that you can use this command:

	tar -xvf /path/to/alpine-rpi-3.X.X-ARCH.tar.gz /path/to/sd

You obviously have to adjust the paths to your configuration.

#### Setup your HDD

If your hard drive is formatted with NTFS, you don't have to change any thing. If not, use this command to do it. Beware, that all the data will be lost during the formatting.

	mkfs.ntfs -Q /dev/sdXY

Make sure you have ntfs-3g installed.

#### Setup Alpine

Put the SD card in your Raspberry Pi and boot it up. Log in to the system as root and leave the password empty. Now you type ```setup-alpine``` and hit enter to start the installation process.

> setup-alpine <

After that, you should update the system and install a few tools, you're gonna need. Use these commands to do that:

	apk update
	apk upgrade
	apk add ntfs-3g sudo

> edit /etc/fstab <

You've installed Alpine in diskless mode, which means, you have to save all your work to your hard drive. Otherwise they won't persist a reboot. Use ```lbu``` to do that:

	lbu commit

#### Setup Samba

#### Connect to your Samba share

###<a name="technologies"></a> Technology choices

### Sources and further reading

- [Alpine Linux](https://alpinelinux.org/)
- [Wiki Article](https://wiki.alpinelinux.org/wiki/Raspberry_Pi) about how to install Alpine Linux on a Raspberry Pi
