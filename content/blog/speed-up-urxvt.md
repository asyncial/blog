+++
title = "Speed up URxvt"
date = "2017-09-04T01:27:17+02:00"
draft = false

+++

This blog post documents really quick, how you can get [URxvt](http://software.schmorp.de/pkg/rxvt-unicode.html) to be ready in less time. I measured the time, my computer needed, to start instances of URxvt to a usable shell and close it again for 25 times. I tried that with [bash](https://tiswww.case.edu/php/chet/bash/bashtop.html), [dash](https://www.in-ulm.de/~mascheck/various/ash/⎈) and [zsh](http://www.zsh.org/) with and without [oh-my-zsh](http://ohmyz.sh/). It measured it with [time(1)](http://man7.org/linux/man-pages/man1/time.1.html). My test script looks like this:
```
#! /bin/sh

for i in 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25
    do urxvt -e 'dash'
done
```
Of course, 'dash' needs to be replaced with the shell, you want to use. It's not and a beautiful script, and I think, I will redo it sometime, making it more flexible. 
The configs for all shells just consisted of ```exit```, so they close immedietly after they're ready, with the exception of my [oh-my-zsh-config](https://github.com/asyncial/dotfiles-maschine/blob/master/zsh/.zshrc), which is the one, I use at the moment, but with an ```exit``` appended in the last line.
I used MASCHINE, my notebook, as platform for the tests. Look at its specs in my [about](https://asyncial.github.io/about/) page.

### What to do

So, how do we get the start up faster? Throw out stuff we don't need. For example the Perl support. I don't use any extensions or scripts, so I can safely disable it. The great thing is, URxvt lets you do this, without having you recompile it by hand. You can just append the following setting to your ```~/.Xresources```:
```
! DISABLE PERL FOR BETTER PERFORMANCE AND SECURITY !
URxvt.perl-ext:
URxvt.perl-ext-common:
```
This disables the startup of the built-in perl interpreter. But can we get it even faster? Of course. URxvt comes with an optional client-server model. So, if we run the ```urxvtd``` daemon at boot time, we can start its client ```urxvtc``` with insane time improvements. Just add this to your systems autostart file:
```
urxvtd -q -o -f &
```
This starts the daemon in the background and keeps it exclusive for the running X instance. One could this consider cheating, because urxvt is kind of started already, but that is another topic.

### How fast it is

Remember that this is the time 25 instances of URxvt need to launch.

<table>
    <tr>
        <th>shell in use</th>
        <th>urxvt</th>
        <th>urxvt without perl</h>
        <th>urxvt without perl and in daemon mode</th>
        <th>How much of the original time?*</th>
    </tr>
    <tr>
        <th>dash</th>
        <td>1.496 s</td>
        <td>0.827 s</td>
        <td>0.151 s</td>
        <td>10.1 %</td>
    </tr>
    <tr>
        <th>bash</th>
        <td>2.766 s</td>
        <td>2.039 s</td>
        <td>0.465 s</td>
        <td>16.8 %</td>
    </tr>
    <tr>
        <th>zsh</th>
        <td>1.651 s</td>
        <td>0.976 s</td>
        <td>0.245 s</td>
        <td>14.8 %</td>
    </tr>
    <tr>
        <th>zsh with oh-my-zsh</th>
        <td>3.77 s</td>
        <td>3.069 s</td>
        <td>0.525 s</td>
        <td>13.9 %</td>
    </tr>
</table>

*As calculated with: [urxvt] * 100 / [urxvtc without perl]

### Conclusion

We can see, that we now only need ~10-15 % of the time, we once needed to start a terminal window. In the case of my config, that is only a difference of about 0.15 second (for a single run), but it has gone from noticeable to unnoticable. I think, the difference could be even more important, if I had a traditional HDD. I can think of another optimization, which is recompiling the application without all unneeded features and with custom CFLAGS, to optimize for your processor architecture, but that might be overkill. However on a weaker system like the Raspberry Pi, it could be an option.

### Sources

* [URxvt documentation](http://cvs.schmorp.de/rxvt-unicode/doc/rxvt.7.html)
* [Arch Wiki about URxvt](https://wiki.archlinux.org/index.php/Rxvt-unicode)
