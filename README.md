This is a set of scripts and patches I use to try and minimizing the annoyance of dealing with the X selection buffer. The main problem is that on a touchpad it is very easy to accidentally hit the middle mouse button and paste a whole lot of garbage into a shell session or any other program. So we have...

Patches
-------

Patches for both GTK and rxvt-unicode to ignore the middle click event / disable the hardcoded paste functionality. The gtk patch is from Jelle Geerts (posted here: http://askubuntu.com/questions/4507/how-do-i-disable-middle-mouse-button-click-paste). It applies on both gtk2 and gtk3 (with `patch -Np1`). I believe it actually replaces the pasted text with the empty string. Possibly a better patch would more precisely affect only the middle click event handling.

Scripts
-------

`xcopy` is a bash oneliner using xsel to copy the primary selection into the clipboard buffer, so that we can still paste things from terminal apps that only support the selection "buffer". I have this bound to the Meta4+C key combo in the window manager.
