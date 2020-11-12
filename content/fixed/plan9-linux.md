+++
title = "Plan 9 -> Linux"
date = "2020-11-12T15:16:32+01:00"
draft = false

+++

[Plan 9 from Bell Labs](https://9p.io/plan9/) is one of the more interesting operating systems out there. I've always found it interesting to find software, that is in some way inspired by Plan 9 on other operating systems. So, to document what I find on this, I decided to make a list of Plan 9 inspired Linux programs.

## Ports

This category gets the straight-up ports of Plan9 programs to Linux/Unix out of the way, before going further. All the software listed here shares a significant amount of code with their ancenstors. If it doesn't, I don't count it as port, but as inspired.

- [Plan 9 from User Space (plan9port)](https://9fans.github.io/plan9port/): A port of most of the Plan 9 userland.
- [9base](https://tools.suckless.org/9base/): Based on plan9port, but seems to be more minimal (and less maintained).
- [frontbase](http://openbsd.stanleylieber.com/frontbase/): Based on 9base, but uses the Plan 9 distribution [9front](http://9front.org) as a source.
- [mk](https://9fans.github.io/plan9port/unix/): A port of just ```mk``` and the libraries needed for it.
- [sam](https://github.com/deadpixi/sam): An updated port of the ```sam``` text editor.
- [acme2k](https://github.com/karahobny/acme2k): An updated port of the ```acme``` programming environment.

## Inspired programs

This category lists all the software I could find, that is more or less explicitly inspired by Plan 9.

### window management:

- [9wm](https://github.com/9wm/9wm): X11 window manager inspired by ```rio```.
- [w9wm](http://www.drieu.org/code/w9wm.en.html): An improved version of ```9wm```.
- [larswm](http://porneia.free.fr/larswm/larswm.html): Rewrite of ```9wm``` featuring automatic tiling, virtual dektops and more.
- [windowlab](https://github.com/nickgravgaard/windowlab): Based on ```larswm```, an window manager *»of novel design«*.
- [riosh](https://gitlab.com/nilix/riosh): Emulates some ```rio``` behaviour on X11.
- [ryudo](https://gitlab.com/nilix/ryudo): Fork of plan9port's ```rio```, adding keyboard shortcuts, customizable colors and better support for URxvt.
- [Mux](https://github.com/as/Mux): Plan9-like window environment for your shell.
- [pRio](https://github.com/letoram/prio): ```Rio```-like window manager for the [Arcan](https://github.com/letoram/arcan) desktop engine.
- [wio](https://wio-project.org): ```Rio```-like wayland compositor.

### text editing

- [Wily](http://www.cs.yorku.ca/~oz/wily/): Implementation of ```acme``` for *NIX operating systems.
- [Edwood](https://github.com/rjkroege/edwood): Go reimplementation of ```acme```.
- [yacco](https://github.com/aarzilli/yacco): Go reimplementation of ```acme```.
- [A](https://github.com/as/a): Text editor inspired by ```sam``` and ```acme```.
- [Editor](https://github.com/jmigpin/editor): Text editor inspired by ```acme```.
- [T](https://github.com/eaburns/T): Text editor inspired by ```acme```.
- [Edit](https://c9x.me/edit/): Tries to mix ```acme``` and ```vi```.
- [vis](https://github.com/martanne/vis): Modal editor (like ```vi```) using structural regular expressions (like ```sam```).

#### plugins

- [kak-plumb](https://github.com/eraserhd/kak-plumb): [Kakoune](https://kakoune.org) integration with the plan9port plumber.
- [sink.el](https://github.com/alcah/sink.el): Emacs integration with the plan9port plumber.
- [Plan 9 for vimspace](https://github.com/plan9-for-vimspace/plan9-for-vimspace): Plan 9 inspired utilities for vim.

### shell

- [nash](https://github.com/madlambda/nash): Shell inspired by ```rc```.
- [rwsh](https://github.com/tudurom/rwsh): Shell based around structural regular expressions.

### shell utils

- [usam](https://github.com/tudurom/usam): ```sam``` commands as unix commands.
- [edit](https://github.com/as/edit): Stand-alone implementation of the ```acme``` command language.
- [goblin](https://github.com/mortdeus/goblin): Go reimplementation of the Plan 9 userland.
- [Torgo](https://github.com/as/Torgo): Command line toolkit inspired by Plan 9.#

### make

- [mk](https://github.com/dcjones/mk): »Reboot« of Plan 9 ```mk```.
- [hmk](https://github.com/mboes/hmk): Pure haskell clone of ```mk```.

### plumber related

- [xdg-open](https://www.freedesktop.org/wiki/Software/xdg-utils/): Basically the native Linux implementation of the plumber. [This article](https://woozle.org/papers/plan9.html) details how it can be used.
- [plumber](https://github.com/halfwit/plumber): Plan 9 inspired script to open programs based on a string.
- [xplumb](https://gitlab.com/fdedden/xplumb): Integrating the plumber with X11.

### (9p)[https://en.wikipedia.org/wiki/9P_(protocol)] related

- [u9fs](bitbucket.org/plan9-from-bell-labs/u9fs): 9p server.
- [v9fs](http://v9fs.sourceforge.net): File system driver for the Linux kernel.
- [c9](https://git.sr.ht/~ft/c9/): Low level 9p client and server.
- [9pfuse](https://github.com/aperezdc/9pfuse): FUSE-based 9p client.
- [9mount](http://sqweek.net/code/9mount/): 9p mounting tools.

[See more.](http://9p.cat-v.org/implementations)

### misc

- [Go](https://golang.org): Programming language.
- [werc](http://werc.cat-v.org): Web anti-framework.
- [frame](https://github.com/as/frame): Graphics toolkit.
- [tanna](https://gitlab.com/brendes/tanna): Font converter.
