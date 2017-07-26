+++
date = "2017-07-26T15:03:00+02:00"
draft = false
title = "The Status of the Qt desktop"

+++

In the last few years, Qt-based desktop environments are becoming more and more popular. There are a lot of them, by now. Of course the old, trusty [KDE](https://www.kde.org/plasma-desktop), now in version 5.10, as "flagship" of the Qt crew, but there are more. [LXQt](http://lxqt.org/) as the lightweight choice, a fusion between [LXDE](http://lxde.org/) and [Razor-Qt](https://github.com/Razor-qt/razor-qt), the highly experimental [Liri](https://liri.io/), trying to implement a very modern looking desktop, very similar to Google's Material Design, the ... different DE, called [theShell](https://vicr123.github.io/theshell/#), of course [Lumina](https://lumina-desktop.org/) mainly targeted at *BSD, but of course portable enough, to run on Linux too, and in the future [Budgie](https://budgie-desktop.org/2017/01/25/kicking-off-budgie-11/) is going to be Qt-based as well!

One can clearly see, the Qt people landed a hit with Qt 5. But it ist possible to run a system with Qt as the only graphics toolkit?

Short answer is: yes, and some distributions do this already. But there are problems, some quite severe. But let me show you!

## Make your Desktop look Qt.

What do we need for a working desktop, so we can work, have us entertained, learn, communicate and aimlessly look at web pages. The first thing you would need to deicde on, is the desktop environment.

### Desktop Environment

I already talked about the variety of Desktop Environments. For this experiment, I used KDE Plasma 5.10, because I think, it is the most advance and established one out of that list. But I try to find tools without KDE dependencies, so you can use them with any of the DEs I listed, without pulling a lot of dependencies.

The Plasma Desktop is the flagship of the Qt-based DEs. It has endless features and possible configurations and a lot of great applications are developed under it's umbrella. It's UI is extremely costumizable, but it ships, with a sane default. The customizability is achieved via so called "plasmoids". These are mini applications that can work as widgets on the desktop or as a button in your control bar. The control bar is in my opinion one of the best, I've ever seen. You can choose different types of application menus (or non at all), can vary it's height and length, add any plasmoid you wish and so much more. But the other parts of the plasma desktop allow pretty fine grained control, again with sane defaults. Another nice feature is the integration of android phones via KDE connect, but it doesn't work for me, because of my weird router setup...
As you might have noticed, I'm pretty excited about KDE, but it is just as feature-rich, as it gets. I really like it.

So what do else do we need? I established a few categories and went on to find matching software.

### Work

#### Documents, Spreadsheets, Presentation...

So what do we use as our office suite? This is actually already the first weak point of our experiment. There is calligra, which is actually pretty capable of handling your everyday needs (but not very much more), but it depends heavily on the KDE framework. That said, if you are okay with that, it works nice, as far as I experienced it so far. It is not LibreOffice in terms of functionality, but it is definitely worth a try. But what if we don't want that huge pile of dependencies? You would need to dig pretty deep. You could write [markdown](https://daringfireball.net/projects/markdown/) with any of the text editors below, but that gets old pretty quick. If you are smarter than me, and know how to write LaTeX, there is a IDE for that, called [TeXstudio](http://texstudio.sourceforge.net/). Speaking of LaTeX, there is also [LyX](http://www.lyx.org/), which let's you use a traditional word processor interface to help you create LaTeX documents for stupid people like me. It's the thing that comes the closest to your average word processor, if you restrict yourself to Qt. So we have a word processor. So what about spreadsheets and presentation? Besides calligra, I'm afraid there isn't anything. You could use web based applications though.

So long story short: When we look at office suites, the Qt world is quite lacking. You can stick to **LyX**, then you can't edit spreadsheets or create presentations. You can use **calligra**, but then you have a whole lot of KDE dependencies. Or you make a exception for **LibreOffice** like I do it...

#### Text Editors

The situation of text editors is much better. I use [neovim](https://neovim.io/) myself, which offers [nice Qt GUI](https://github.com/equalsraf/neovim-qt). Basically, you can use any CLI text editor for obvious reasons. So what about GUI text editors? The most famous ones (Sublime, any electron based one) are out. What else do we have? If you are comfortable with KDE dependencies, there are [KWrite](https://www.kde.org/applications/utilities/kwrite/) and [Kate](https://kate-editor.org/), which are both quite nice and clean. Of course there are others, non-KDE editors. The best of those is in my opinion [notepadqq](http://notepadqq.altervista.org/s/), which is a Qt5 clone of Notepad++, the popular Windows text editor. And similar to it, notepadqq is lightweight and straightforward to use. I really like it.

Result: **Notepadqq** is the most obvious choice, but **Neovim-qt**, and the KDE solutions are nice too.

#### Terminal

You have basically just one choice here, and that is [QTerminal](https://github.com/lxde/qterminal), but it is not a bad one. It does everything one would expect from a lightweight terminal emulator and a bit more. And that is actually more than I need from a terminal. A nice touch is the pull down mode, which enables you to call it everytime you need. If you count KDE applications, there is [Konsole](https://konsole.kde.org/), which I found to be a bit over the top with it's vast of features. What I liked though, is [Yakuake](https://konsole.kde.org/), which is a pull down terminal, which looks pretty nice.

Result: **QTerminal**, no discussion. Though **Yakuake** looks really good...

#### Graphics

If you just count pure Qt(5), this one is depressing. There just isn't anything. If you count KDE based apps, this one is extremely strong. That is because of [krita](https://krita.org/en/) which might just be the best program for digital painting. But it also allows pretty good image manipulation and even the creation of animated scenes. It has a very active community and a yearly kickstarter to ensure the ongoing development. I think it will see a great future.

#### Movie

If you have to edit videos or movies from time to time a need a easy solution, there is [OpenShot](http://www.openshot.org/). It is pretty solid, as far as I can see. If you need anything more professional, you would have to use KDE software again. [Kdenlive](https://kdenlive.org/) is the tool of trade here. Sadly, I can't say too much about their quality, because I just don't need them a lot.

### Entertainment

#### Images

There are a few image viewers using Qt around. I like [nomacs](http://nomacs.org/) the most. It looks nice enough and has basic image editing capabilites. What would one need more?

#### Video

The situation for video players is really good on Qt. I normally just use [mpv](https://mpv.io/), which isn't Qt, but GTK neither. There are video players using Qt and libmpv though, so best of both worlds, I guess. The player I liked the most of these is [Baka MPlayer](http://bakamplayer.u8sand.net/), which features a pretty interface and nice configurability. But there is another one. [bomi](https://bomi-player.github.io/) is built around a customized mpv fork. It is just as nice as Baka MPlayer and I can't give you a adequate recommendation. You can't do anything wrong here.

#### Music

With music, it's more difficult. After trying different options, I settled for [tomahawk](https://www.tomahawk-player.org/), which does it's job, but is nothing too good. To be fair, I'm really picky, when it comes to music players...

#### Gaming

Most games are built on SDL, so they don't need any other graphics toolkit. The real problem here is, that steam is not based on Qt. So no steam for us? As far as I can see, it doesn't depend on any other toolkit, so we might as well just use it. If you are more on the retro gaming side of things, most emulators provide different front ends, and a quite a few are based on Qt.

### Internet and Communication

#### Browser

Ah, yes, the weakest link of the Qt ecosystem. Although it provides the blazingly fast qtwebengine, the programs using it are not, what one would call a mature browser. The best I found are [Qupzilla](https://qupzilla.com/) and [Otter Browser](https://qupzilla.com/). Qupzilla is actually really nice and I am pretty impressed by it. But there is a problem: Extension support. While Qupzilla provides it's own PlugIn API, it doesn't support Chromium or Firefox add ons. That's a shame, because there are just some extensions, I don't want to give up. Especially https everywhere and reddit enhancement suite. That's acutally the only thing, that stopped me using it as a main browser. Otter on the other hand is a clone of Opera 12, but still unstable and experimental. But at least chrome extension support is on the "after 1.0" list. So maybe in the future, this could be a true replacement for the mainstream browsers.

So yeah, what can you do? I can just say, try **Qupzilla**, and if it might suit you. But beyond that, I guess you have to use your usual suspects, like **Firefox**. At least, there are firefox-kde-integration packages on a few distros.

#### Mail

And the next weak point. You can use [Trojita](http://trojita.flaska.net/), which is good enough, but only if you just have one mail account. Then there is [KMail](https://www.kde.org/applications/internet/kmail/), which not only depends on the K framework, but also on the huge KDE PIM application stack. Both not really alternatives to what we know. So if you don't want to use Thunderbird or something similar, you have to use your webmail interfaces...

#### Torrenting

Bittorrent tools are pretty important in the linux world, as you need them to load your gigabytes of distribution isos, you "want to try some time", and then never do. So what is here for that? [qBittorrent](https://www.qbittorrent.org/) has you covered, no further questions your honour!

### Other

#### File Manager

What about file managers? As far as I am concerned, there are two choices: Qt-only: [PCManFM-qt](https://www.qbittorrent.org/), the Qt port of the popular PCManFM. It does it's job and is lightweight doing it. There is one problem: it doesn't support mounting with udisks, trash and remote filesystems without gvfs. Depending on your distribution, gvfs will pull gtk, so be cautios. If you are comfortable with KDE, there is [dolphin](https://userbase.kde.org/Dolphin), which is one of the best file managers on linux. I like it's design, and the most important settings are literally just one click away. 

#### Display Manager

Just one word: [SDDM](https://github.com/sddm/sddm)

#### Calculator

I just picked this category, because there is such a nice tool. It's called [speedcrunch](http://www.speedcrunch.org/), and it's awesome.

## Conclusion

As you can see, there actually is a lot to discover, if you restrict yourself. I think, if you don't set your rules too strict, you can have a nice consistent looking desktop with almost only Qt applications. I think it's a bit sad, that you especially in the fields, one needs often, there are not so strong alternatives, especially for web browsing, mails and office. I think this is not the last time, I am doing this experiment, maybe next year is "the year of the Qt desktop".

#### Bonus: Distributions with a special Qt focus

* [Chakra Linux](https://chakralinux.org/) - Pacman-based distro with plasma desktop. The gtk software is in extra repository, which can be easily deactivated. It is semi-rolling.
* [KaOS](https://kaosx.us/) - Another pacman-based distro with the plasma dekstop. Ships only a few gtk tools on a fresh install, but still provides it in their repositories. It is rolling release.
* [KDE Neon](https://neon.kde.org/) - The "official" KDE distro, built by the KDE community. It is based on Ubuntu LTS, but ships the newest KDE software availible.
* [Mageia](http://www.mageia.org/en/), [OpenMandriva](https://www.openmandriva.org/), [ROSA](http://en.rosalinux.com/rosa-fresh/) - The successors of Mandriva/Mandrake are all using Plasma and LXQt as their desktop environments. Except for Mageia, I found them to be not very polished and/or a bit unstable.
* [Maui](https://mauilinux.org/), [Netrunner](http://www.netrunner.com/) - Plasma distributions from the same community, but with different bases. Maui uses Ubuntu, Netrunner on Debian and Netrunner Rolling on Manjaro. Focus on a nice KDE experience without KDE PIM.
* [OpenSUSE](https://www.opensuse.org/) - OpenSUSE is not "just plasma", but it is said to provide one of the best out-of-the-box plasma experiences. Rolling or stable.
* [Siduction](https://forum.siduction.org/) - Also not "just Qt", but it has one of the nicest LXQt configs, I have seen so far.
* [Liri OS](https://liri.io/) - Arch-based distro, with it's very own Qt DE, called liri.
* [TrueOS](https://www.trueos.org/) - Not a linux, but the home of the Lumina Desktop Environment. Based on FreeBSD.

#### Additional Resources

* [List of Qt Applications - Manjaro Wiki](https://www.trueos.org/)
* [Qt Desktop Applications - Gentoo Wiki](https://wiki.gentoo.org/wiki/Qt_Desktop_applications)
* [3rd party applications - Razor-qt Wiki](https://github.com/Razor-qt/razor-qt/wiki/3rd-party-applications)
* [LXQt: Suggested Applications - Fedora Wiki](https://fedoraproject.org/wiki/LXQt:_Suggested_Applications)
* [Third party apps - LXQt Wiki](https://github.com/lxde/lxqt/wiki/Third-party-apps)
* [List of applications - Arch Wiki](https://wiki.archlinux.org/index.php/List_of_applications)
* [Distributions - KDE Wiki](https://community.kde.org/Distributions)
