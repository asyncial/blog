+++
title = "HOWTO: Host a samba-share on a Raspberry Pi"
date = "2018-12-18T23:59:28+01:00"
draft = true

+++
__The problem__: Having to carry your external HDD around the house, or using it on different PCs at the same time.
__The solution__: Use a Raspberry Pi to share your HDD in your local network via the CIFS/SMB/SAMBA protocol. This is going to be usable from all major operating systems, including Windows.

[Further down](#technologies) I have explained my choice of technologies used in this how-to.

__Let's get started.__

## What do I need?

- [Raspberry Pi 1, 2, 3 or 4](https://www.raspberrypi.org)
- external HDD with USB and power adaptor OR
- external HDD with USB and an USB hub with power adaptor
- microSD card with at least 256MiB
- An HDMI screen and a USB keyboard for initial configuration
- A stable ethernet connection, preferably wired

Note that I will explain the initial configuration of the SD card and the HDD assuming a Linux computer. It is however not particularly difficult to do this with Windows. It just works differently.

## What do I have to do?

### Setup your SD card

First you have to download the [latest image](https://alpinelinux.org/downloads/) of Alpine Linux. Use the armv7 version if you use the Raspberry Pi 2. Use the aarch64 image for anything later, since it's not only 64 bit, but also provides a new architecture (armv8). I would recommend the 4 because of the superior connectivity (USB3 and true GBit LAN).

Before you write the sd card, you need to format it in FAT32. I will show how to using the ```fdisk``` command. Make sure the sd card is not mounted. This will assume your card is at /dev/mmcblk0. Check with ```lsblk``` if this is true for your system too. If not, use the name shown in the listing.

	# fdisk /dev/sdb

	Command (m for help): o
	Command (m for help): n

	Partition type
	p   primary (0 primary, 0 extended, 4 free)
	e   extended (container for logical partitions)
	Select (default p): *<use default>*
	Partition number (1-4, default 1): *<use default>*
	First sector (2048-*depends on your sd card*, default 2048): *<use default>*
	Last sector, +/-sectors or +/-size{K,M,G,T,P} (2048-*depends on your sd card*, default *depends on your sd card*): *<use default>*

	Command (m for help): t
	Hex code (type L to list all codes): c
	Command (m for help): a
	Command (m for help): w

Now you need to format and mount the partition:

	# mkfs.fat -F 32 /dev/mmcblk0p1
	$ mount /dev/mmcblk0p1 /mnt  ????


After you've done that, you can extract your downloaded image on your freshly formatted SD card and unmount it. For that you can use this command:

	$ tar -xvf /path/to/alpine-rpi-3.X.X-ARCH.tar.gz -C /mnt
	$ umount /dev/mmcblk0p1

You obviously have to adjust the paths to your configuration.

### Setup your HDD

If your hard drive is formatted with NTFS, you don't have to change any thing. If not, use this command to do it. Beware, that all the data will be lost during the formatting.

	# mkfs.ntfs -Q /dev/sdXY

Make sure ntfs-3g is installed on your system.

### Setup Alpine

Put the SD card in your Raspberry Pi, connect a screen, a keyboard, your ethernet cable and your HDD and boot it up. Log in to the system as root and leave the password empty. Now you type ```setup-alpine``` and hit enter to start the installation process.

> keyboard
> Enter system hostname (short form, e.g. 'foo') [localhost]:
> Available interfaces are: eth0, wlan0
> Enter '?' for help on bridges, bonding and vlans.
> Which one do you want to initialize? (or '?' or 'done') [eth0]
> Ip address for eth0? (or 'dchp', 'none', '?') [dhcp]
> Available interfaces are: wlan0
> Enter '?' for help on bridges, bonding and vlans.
> Which one do you want to initialize? (or '?' or 'done') [wlan0] done
> Do you want to do any manual netwrok configuration? [no]
> Network stuff
> Changing password for root
> New password:
> Retype password:
> passwd: password for root changed by root
> Which timezone are you in? ('?' for list) [UTC]
> HTTP/FTP proxy URL? (e.g. 'http://proxy:8080' or 'none') [none]
> Which NTP client to run? ('busybox', 'openntpd', 'chrony' or 'none') [chrony] busybox
>
> <...>
> Enter mirror number (1-XX) or URL to add (or r/f/e/done) [1]: f
>
>
> Which SSH server ('openssh', 'dropbear' or 'none') [openssh]
> Which disk(s) would you like to use? (or '?' for help or 'none') [none]
> Enter where to store your configs ('floppy', 'mmcblk0p1', 'usb' or 'none') [mmcblk0p1]:

After that, you should update the system and install a few tools, you're gonna need. Use these commands to do that:

	apk update
	apk upgrade
	apk add ntfs-3g sudo

Edit the ```/etc/fstab/``` file and add the following line:

	// only the storage line


Edit ```/etc/lbu/lbu.conf```:

LBU_MEDIA=storage

commit the current changes directly to sd:
lbu commit -d mmcblk0p1

You've installed Alpine in diskless mode, which means, you have to save all your work to your hard drive. Otherwise they won't persist a reboot. Use ```lbu``` to do that:

	lbu commit

### Setup Samba

Next you need to setup your SMB server. So install it with

	apk add samba

> connect your harddrive
> create smb.conf
> create a new user
> add user to samba
> configure samba services
> add needed files to lbu

### Connect to your Samba share

> linux
> windows

##<a name="technologies"></a> Technology choices

### Alpine Linux

There are two reasons for Alpine Linux: It is very tiny, so a Raspberry Pi will have no problems with it, ever. This is also what's making it fast, easy on resources and also energy efficent. The other reason is ```lbu```. This tool enables a rather simple installation, in which the microSD card can be used read-only, preventing it from breaking from too many write cycles in the long run.

### Samba

Samba makes it possible to share your files with every major OS. This makes it superior to NFS for my use-case.

### NTFS

If you ever need to take the harddrive with you, to let a Windows-using friend copy a movie, this is your only choice, because FAT32 is restricted to 4GiB per file.

### Raspberry Pi

It is cheap and easily availible. Version 4 also finally got proper connectivity for a project like this.

## Sources and further reading

- [Alpine Linux](https://alpinelinux.org/)
- [Alpine Wiki Article](https://wiki.alpinelinux.org/wiki/Raspberry_Pi) about how to install Alpine Linux on a Raspberry Pi
- [Alpine Wiki Article](https://wiki.alpinelinux.org/wiki/Setting_up_a_samba-server) about how to install a Samba Server
- [Arch Wiki Article](https://wiki.archlinux.org/index.php/Samba) about Samba
