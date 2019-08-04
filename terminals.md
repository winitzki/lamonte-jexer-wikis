Terminal Features
=================

Jexer can use the following features of a terminal if available:

* Mouse clicks.
* Mouse motion, including dragging and resizing windows.
* 24-bit ("true color") RGB.
* Image support via sixel.  (So far as I know, Jexer is the only text windowing system with sixel image support.)

Terminals
---------

Most popular X11 terminals can run Jexer, but so far only [xterm](https://invisible-island.net/xterm/) supports all of Jexer's features.  The table below lists the terminals tested against Jexer recently:

| Terminal       | Environment        | Mouse Click | Mouse Cursor | Images |
| -------------- | ------------------ | ----------- | ------------ | ------ |
| xterm          | X11                | yes         | yes          | yes    |
| jexer          | X11                | yes         | yes          | yes    |
| lcxterm(3)     | CLI, Linux console | yes         | yes          | no     |
| rxvt-unicode   | X11                | yes         | yes          | no(2)  |
| alacritty(3)   | X11                | yes         | yes          | no     |
| gnome-terminal | X11                | yes         | yes          | no     |
| xfce4-terminal | X11                | yes         | yes          | no     |
| mlterm         | X11                | yes         | yes          | no(5)  |
| aminal(3)      | X11                | yes         | no           | no     |
| konsole        | X11                | yes         | no           | no     |
| yakuake        | X11                | yes         | no           | no     |
| screen         | CLI                | yes(1)      | yes(1)       | no(2)  |
| tmux           | CLI                | yes(1)      | yes(1)       | no     |
| putty          | X11, Windows       | yes         | no           | no(2)  |
| Linux          | Linux console      | no          | no           | no(2)  |
| qodem(3)       | CLI, Linux console | yes         | yes(4)       | no     |
| qodem-x11(3)   | X11                | yes         | no           | no     |
| yaft           | Linux console (FB) | no          | no           | yes    |

1 - Requires mouse support from host terminal.

2 - Also fails to filter out sixel data, leaving garbage on screen.

3 - Latest in repository.

4 - Requires TERM=xterm-1003 before starting.

5 - Opening image crashes terminal.

When running on the raw Linux console, [LCXterm](https://gitlab.com/klamonte/lcxterm) or [Qodem](http://qodem.sourceforge.net) are required if one wishes to use the mouse.  [GPM](https://github.com/telmich/gpm) is also required.
