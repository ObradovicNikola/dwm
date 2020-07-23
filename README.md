# dwm - dynamic window manager
============================
## dwm is an extremely fast, small, and dynamic window manager for X.


This is my personal customization of dwm.

`dev` branch is used for customization (make dwm from this branch)

`master` branch represents `upstream` and reflects [git.suckless.org/dwm](git.suckless.org/dwm)

## Updating

`git checkout master`

`git pull upstream master`

`git checkout dev`

`git rebase --preserve-merges master`

The `--preserve-merges` option ensures that you don't have to resolve conflicts
which you have already resolved while performing merges again.

In case there are merge conflicts anyway, resolve them 
(possibly with the help of `git mergetool`), then record them as resolved
and let the rebase continue.

`git add resolved_file.ext`

`git rebase --continue`

If you want to give up, you can always abort the rebase

`git rebase --abort`


Requirements
------------
In order to build dwm you need the Xlib header files.


Installation
------------
Edit config.mk to match your local setup (dwm is installed into
the /usr/local namespace by default).

Afterwards enter the following command to build and install dwm (if
necessary as root):

    make clean install


Running dwm
-----------
Add the following line to your .xinitrc to start dwm using startx:

    exec dwm

In order to connect dwm to a specific display, make sure that
the DISPLAY environment variable is set correctly, e.g.:

    DISPLAY=foo.bar:1 exec dwm

(This will start dwm on display :1 of the host foo.bar.)

In order to display status info in the bar, you can do something
like this in your .xinitrc:

    while xsetroot -name "`date` `uptime | sed 's/.*,//'`"
    do
    	sleep 1
    done &
    exec dwm


Configuration
-------------
The configuration of dwm is done by creating a custom config.h
and (re)compiling the source code.

## Patches

- [restartsig](https://dwm.suckless.org/patches/restartsig/)
- [hide vacant tags](https://dwm.suckless.org/patches/hide_vacant_tags/)
- [notitle](https://dwm.suckless.org/patches/notitle/)
- [pertag](https://dwm.suckless.org/patches/pertag/)
- [noborder](https://dwm.suckless.org/patches/noborder/)
- [fibonacci](https://dwm.suckless.org/patches/fibonacci/)
- [movestack](https://dwm.suckless.org/patches/movestack/)

### Patches to consider

- [urgentborder](https://dwm.suckless.org/patches/urgentborder/)