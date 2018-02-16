+++
title = "Backup your current Vivaldi session automatically"
date = "2018-02-16T22:20:57+01:00"
draft =false

+++

As you might know, I use [Vivaldi](https://vivaldi.com). I really like it, because I think, it is a quite flexible window manager. I can have tens and hundreds of tabs open, but I can sort them, group them, view them as a tree, even tile them. Vivaldi has a downside though. It is not exactly the most stable browser on my system. So, from time to time, Vivaldi crashes and loses all my tabs. It's doesn't happen all the time, but sometimes. Because this annoyed me one time to often, I have written a session backup solution in POSIX shell (+ local variables).

There are three scripts. One is called [backup_vivaldi_session.sh](https://raw.githubusercontent.com/asyncial/bin/master/backup_vivaldi_session.sh). It is responsible for saving the ```Current Session``` file, stored in ```~/.config/vivaldi/Default```, periodically in a user definded folder. To set the backup folder, change the ```backup_path``` variable in the script. You can also change the number of backups, that are kept and the how often the backup should run. The script automatically stops, when Vivaldi is not running on the system.

The next one helps you restore your Vivaldi session after a crash. It is called [restore_vivaldi_session.sh](https://raw.githubusercontent.com/asyncial/bin/master/restore_vivaldi_session.sh). You use it, by invoking ```restore_vivaldi_session.sh -n 3```. This way, you would restore the third most recent session backed by the script. Without any arguments, it uses the most recent one. (Equivalent to ```-n 0```). **But before you can do that**, you need to set the same path, as in the backup script in the variable ```VIVALDI_BACKUP_DIR```.

The last script is a starter script. It assumes the backup script and the vivaldi-bin file in the ```$PATH```. It is just called [vivaldi](https://raw.githubusercontent.com/asyncial/bin/master/vivaldi) and starts Vivaldi, as well as the backup script, after a short waiting time, to let vivaldi finish it's startup.

You can find all the scripts and more in my [/bin/ repository](https://github.com/asyncial/bin) on GitHub.I put all of them in my ```$PATH``` and have ```alias vivaldi-bin="vivaldi"``` in my shell startup file, so everytime Vivaldi runs, it is safe against crashes.
