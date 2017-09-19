+++
date = "2017-02-01T18:52:47+02:00"
draft = false
title = "organize your .xresources like a pro"

+++

If you are anything like me, you like to customize your terminal colorscheme. And if you are even more like me, you are using urxvt and need to edit your ~/.Xresources to changes your terminals colors. So I assume your .Xresources are mess an you want to know, how to get them clean and easy to read and customize. If you already have a working system, there is no need to change it. But maybe you can use some of my ideas. So what do my .Xresources look like?

          $ cat ~/.Xresources

* * *

          !!  @@@  @@@  @@@@@@@   @@@@@@@@   @@@@@@    @@@@@@   
          !!  @@@  @@@  @@@@@@@@  @@@@@@@@  @@@@@@@   @@@@@@@@  
          !!  @@!  !@@  @@!  @@@  @@!       !@@       @@!  @@@ 
          !!  !@!  @!!  !@!  @!@  !@!       !@!       !@!  @!@
          !!   !@@!@!   @!@!!@!   @!!!:!    !!@@!!    @!@  !@!
          !!    @!!!    !!@!@!    !!!!!:     !!@!!!   !@!  !!!
          !!   !: :!!   !!: :!!   !!:            !:!  !!:  !!!
          !!  :!:  !:!  :!:  !:!  :!:           !:!   :!:  !:!
          !!   ::  :::  ::   :::   :: ::::  :::: ::   ::::: ::
          !!   :   ::    :   : :  : :: ::   :: : :     : :  : 

          ! SOURCE TERMINAL COLORS !
          #include "/home/tillm/.xres/themes/cyberpunk_mtlx"

          ! SOURCE PROGRAM SPECIFIC FILES !
          #include "/home/tillm/.xres/urxvt"
          #include "/home/tillm/.xres/rofi"

So let’s examine this. ‘!’ initiates a comment. Comments are neat. They help you understand, what you were doing. Any nice config file needs a fancy header. Well, not really, but I like it. Going to the interesting parts: The first interesting statement is this line: #include “/home/tillm/.xres/themes/cyberpunk_mtlx” It tells the interpreter to look in ~/.xres/themes/cyberpunk_mtlx for more instructions. So, to change your scheme, you just create a new file with the colors and change a few characters in this line. It also makes it very easy to change the colors back. Nice, so, how do these theme files look?

          $ cat ~/.xres/themes/cyberpunk_mtlx

* * *

          ! cyberpunk !
          #define c00 #181818
          #define c10 #282828
          #define c11 #383838
          #define c08 #585858
          #define c12 #b8b8b8
          #define c07 #d8d8d8
          #define c13 #e8e8e8
          #define c15 #f8f8f8
          #define c01 #604938
          #define c09 #675348
          #define c03 #AA6640
          #define c02 #9A6D50
          #define c06 #4F9692
          #define c04 #B1875F
          #define c05 #D09339
          #define c14 #DA9561

          *.color0:       c00
          *.color1:       c01
          *.color2:       c02
          *.color3:       c03
          *.color4:       c04
          *.color5:       c05
          *.color6:       c06
          *.color7:       c07
          *.color8:       c08
          *.color9:       c09
          *.color10:      c10
          *.color11:      c11
          *.color12:      c12
          *.color13:      c13
          *.color14:      c14
          *.color15:      c15

You see, I have defined each color as a variable. This way one can use it in other files, which comes now. As you can see, I have created more files, for the applications I use, that are configured through .Xresources. Let’s look at the .xres/urxvt.

          $ cat ~/.xres/urxvt

* * *

          !!  @@@  @@@  @@@@@@@   @@@  @@@  @@@  @@@  @@@@@@@  
          !!  @@@  @@@  @@@@@@@@  @@@  @@@  @@@  @@@  @@@@@@@  
          !!  @@!  @@@  @@!  @@@  @@!  !@@  @@!  @@@    @@!    
          !!  !@!  @!@  !@!  @!@  !@!  @!!  !@!  @!@    !@!    
          !!  @!@  !@!  @!@!!@!    !@@!@!   @!@  !@!    @!!    
          !!  !@!  !!!  !!@!@!      @!!!    !@!  !!!    !!!    
          !!  !!:  !!!  !!: :!!    !: :!!   :!:  !!:    !!:    
          !!  :!:  !:!  :!:  !:!  :!:  !:!   ::!!:!     :!:    
          !!  ::::: ::  ::   :::   ::  :::    ::::       ::    
          !!   : :  :    :   : :   :   ::      :         :     

          ! APPEARANCE !
          URxvt.scrollBar: False
          URxvt.depth: 32
          URxvt.font: -xos4-terminus-medium-r-normal--12-120-72-72-c-60-iso10646-1

          ! COLORS !
          URxvt.background: [90]#000
          URxvt.foreground: #bcbcbc
          URxvt.cursorColor: c14

As you can see, I used the variable ‘c14’ I declared before, to set the value of URxvt.cursorColor. Similar stuff can be seen in the config file for rofi.

* * *

So what are the upsides of organizing your .Xresources this way?

1.  Changing your terminal colorscheme is very convinient.
2.  You can easily reuse the colors declared in your theme for the configuration of other tools and other properties.
3.  You can find the options you want to change faster, because you have separate files for different application. This way, you don’t have to look through just one long file.
4.  You have fancy headers on your config files.

You’re welcome! ;)
