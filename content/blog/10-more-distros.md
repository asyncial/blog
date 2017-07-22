+++
date = "2016-08-19T18:50:00+02:00"
draft = false
title = "10 more distros"

+++

I’ve looked at ten more Linux distros! Again, I have the urge to share my experiences with the ca. 15 different visitors my blog already has, because I guess, they are very interested in my texts here. Or they are not. I only know one of them, and I didn’t ask him. However here is the list of the distros:

*   [Alpine Linux 3.4.3](http://alpinelinux.org/)
*   [Chakra Linux 2016.02 Ian](https://chakralinux.org/)
*   [Linux Mint Debian Edition 2](https://www.linuxmint.com/download_lmde.php)
*   [NixOS 16.03](https://nixos.org/)
*   [OpenSuse Tumbleweed](https://www.opensuse.org/)
*   [Porteus 3.1](http://www.porteus.org/)
*   [Slacko Puppy 6.3](http://slacko.eezy.xyz/index.php)
*   [Slackware 14.2](http://www.slackware.com/index.html)
*   [SliTaz 5.0 rolling](http://www.slitaz.org/en/)
*   [Void Linux](http://www.voidlinux.eu/)

You can see, that I chose more minimal and advanced distros than the last time. I would like to say something about each system, because they all were interesting and had interesting concepts, but I’m too lazy to write that much. I apologize beforehand, if things get a bit technical this time, but I will try to explain, whenever I can.

## Alpine Linux

This might be the most interesting, most impressing distro I’ve tested so far. It is aimed at experienced users and has a focus on security, simplicity and small size. They achieve their goal with some interesting design and software choices. Like Arch Linux they just ship a minimal base system on installation. But that is even more minimal than Arch. Instead of using the [bash](https://www.gnu.org/software/bash/) as standard shell, they decided to use the more lightweight ash. Instead of the big and bloated [GNU coreutils](https://www.gnu.org/software/coreutils/coreutils.html), which provide the basic file and text manipulation tools like `cat`, they ship the extremely light [busybox](https://busybox.net/). They also use OpenRC as init instead of the controversial systemd and chose the security hardened and light [musl-libc](https://www.musl-libc.org/) insted of the common glibc. This leads to smaller executables and a more secure system. Also the kernel is patched with the [grsecurity](https://grsecurity.net/) patchset. It also uses it’s very own package manager, called `apk`.

So how are these choices getting together? Awesome. I had to relearn a few things dealing with busybox, OpenRC and the ash, but I liked, how fast and simple the system was. It also had a quite big package base for a project this size, and building your own packages for it is quite easy, too. It is definitely not for a first-time-linux-user. But I was impressed, how well the system works. I’m now using it to run a samba-server on my Raspberry Pi and it uses less than 100 MiB disk space and about 35 MiB RAM. Just impressive.

## NixOS

Another distro, that is unlike others. NixOS is built around the Nix Package-Manager, and is configured through a declarative language in a single or modularized config file. You can even boot different different configs just by creating different config files, which is quite awesome. The approach works quite well and if you run into difficulties, you can look at the solid documentation online. The packages are recent enough and there are many of them.

I like the approach, it is well deployed and I think, if you invest enough time, it becomes extremely powerful, especially, when you are creating config files for different workloads, like gaming on a minimal window manager, so no ressources get wasted, developing on something tiling and office work on a full DE, that gets out of the way. Each with their own sets of services and so on. The downside is, you have to relearn nearly everything, you know about configuring your linux system.

## Porteus

Porteus is a live-system, based on slackware and its most recent version is quite old, but the new one should be released soon. Regardless the problems with not supported hardware because of the old kernel and other age invoked problems, the system was quite cool. Before you download, you choose which browser you want, which desktop environment, which word processor and so on and will then be downloading a already reasonably well configured system. Once running, you can save your settings, document etc. on the pendrive, on which Porteus is installed. It also gives helps you setting up fundamental stuff. Sadly, the package manager was not able to update it’s databases for some reason. I will definitely check out the next version, because I love the idea, to preconfigure your live-system online.

## SliTaz

The last distribution I will talk about is an independent, minimal and rolling released live distribution. They are also using busybox, like Alpine Linux, but they are shipping a graphical interface, based on OpenBox and parts of LXDE. Their package managment, called TazPkg, is quite cool and has an impressingly large package base. The whole system run at 68 MB, running an fully featured OS with a nice GUI. Impressive. It was just a pleasure to use it and it just was fun to explore, how the developers made it possible to make the system that light. This was definitely not the last time, I’ve been using SliTaz.

* * *

So, next time there finally will be other operating systems than Linux. So stay in touch!
