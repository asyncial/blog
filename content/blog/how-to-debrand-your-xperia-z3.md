+++
date = "2016-04-10T18:23:33+02:00"
draft = false
title = "how to debrand your xperia z3"

+++

When I got myself a new Z3 the other day, it had a T-Mobile software branding. I think, you know, what that means: stupid bloatware and less chance to get updates. So I decided to get rid of it. That’s how you do it:

1.  Do a back up of your data!
2.  Get and install the [Sony PC Companion](http://support.sonymobile.com/global-en/tools/pc-companion/), if you don’t already did.
3.  Get and install [Flashtool](http://www.flashtool.net/downloads.php). I recommend to use the torrent link, because the download server was quite slow, when I tried it.
4.  Get your firmware
    1.  Start Flashtool and click the button on the right of the toolbar, labeled XF. A new window should open.
    2.  In the list on the left, look out for the Xperia Z3/Z3v and choose your model. In the middle, you should know see a new list.
    3.  Choose the correct firmware. It’s the one, where the “market” coloumn is the country, you live in and the “operator” looks something like this: “Customized XX”
    4.  Now, there are different versions listed on the right coloumn of the window. For example: “23.4.A.1.264 / R7C”. The top one is the newest one. Click on it.
    5.  In the new window, just click download. This could take a few minutes.
    6.  If it has finished, you are ready to flash the new firmware.
5.  Flash your firmware.
    1.  Activate the developer options on your Z3.
        1.  In your settings, go to “About phone”
        2.  Click several times on the entry called “Build number” until you get a toast message: “You are now a developer”
    2.  Activate USB debugging in the new entry “Developer options” in your setting. It’s right above “About phone”.
    3.  Connect your phone with your PC and allow USB debugging in the dialog, which should pop up on your phone, when it’s connected.
    4.  In Flashtool, click now on the button with the lightning on the left. Choose Flashmode. Choose your previously downloaded firmware image in the list on the left. Now click “Flash”
    5.  Activate your phones flashmode.
        1.  Disconnect your device from the PC.
        2.  Shut your device down.
        3.  While pressing volume down, reconnect your device.
    6.  Flashtool starts flashing. This could take some time.
6.  Reboot your phone and have fun with an debranded Z3!

I think this could also work with other Xperia phones, for example the Z3 compact, but I didn’t test it. It could also be possible, to flash another countries firmware to your model, but I didn’t test it neither.
