Terminal Features
=================

Jexer can use the following features of a terminal if available:

* Mouse clicks.

* Mouse motion, including dragging and resizing windows.

* 24-bit ("true color") RGB.

* Image support via sixel or iTerm2.  (So far as I know, Jexer is the
  only text windowing system with image support.)  There is currently
  [no documented
  means](https://gitlab.com/gnachman/iterm2/issues/8940) of detecting
  iTerm2 image support, so Jexer will only emit iTerm2 images when
  jexer.ECMA48.iTerm2Images=true.

Terminals
---------

Most popular X11 terminals can run Jexer, but only a few support all
of Jexer's features.  Jexer is developed against
[xterm](https://invisible-island.net/xterm/) .  The table below lists
the terminals tested against Jexer recently:

| Terminal       | Environment        | Mouse Click | Mouse Cursor | Images |
| -------------- | ------------------ | ----------- | ------------ | ------ |
| xterm          | X11                | yes         | yes          | yes    |
| mintty(3)      | Windows            | yes         | yes          | yes    |
| mlterm         | X11                | yes         | yes          | yes    |
| RLogin         | Windows            | yes         | yes          | yes    |
| alacritty(3)   | X11                | yes         | yes          | no     |
| gnome-terminal | X11                | yes         | yes          | no     |
| iTerm2         | Mac                | yes         | yes          | no(5)  |
| kitty(3)       | X11                | yes         | yes          | no     |
| lcxterm        | CLI, Linux console | yes         | yes          | no     |
| rxvt-unicode   | X11                | yes         | yes          | no(2)  |
| xfce4-terminal | X11                | yes         | yes          | no     |
| DomTerm(3)     | Web                | yes         | no           | yes    |
| aminal(3)      | X11                | yes         | no           | no     |
| konsole        | X11                | yes         | no           | no     |
| yakuake        | X11                | yes         | no           | no     |
| screen         | CLI                | yes(1)      | yes(1)       | no(2)  |
| tmux           | CLI                | yes(1)      | yes(1)       | no     |
| putty          | X11, Windows       | yes         | no           | no(2)  |
| qodem(3)       | CLI, Linux console | yes         | yes(4)       | no     |
| qodem-x11(3)   | X11                | yes         | no           | no     |
| wezterm        | X11, Windows       | no          | no           | yes(7) |
| yaft           | Linux console (FB) | no          | no           | yes    |
| Linux          | Linux console      | no          | no           | no(2)  |
| Windows Terminal(6) | Windows       | no          | no           | no(2)  |

1 - Requires mouse support from host terminal.

2 - Also fails to filter out sixel data, leaving garbage on screen.

3 - Latest in repository.

4 - Requires TERM=xterm-1003 before starting.

5 - Sixel images can crash terminal.

6 - Version 0.7.3291.0, on Windows 10.0.18362.30.  Tested against
    WSL-1 Debian instance.

7 - iTerm2 images only, but functional.

When running on the raw Linux console,
[LCXterm](https://gitlab.com/klamonte/lcxterm) or
[Qodem](http://qodem.sourceforge.net) are required if one wishes to
use the mouse.  [GPM](https://github.com/telmich/gpm) is also
required.


Terminal Widgets
----------------

The table below lists embeddable widgets tested against Jexer recently:

| Terminal       | Language | Mouse Click | Mouse Cursor | Images | Link |
| -------------- | -------- | ----------- | ------------ | ------ | ---- |
| jexer (ECMA48) | Java     | yes         | yes          | yes    | https://gitlab.com/klamonte/jexer
| upp-components Terminal | C++ | yes     | yes          | yes    | https://github.com/ismail-yilmaz/upp-components/tree/master/CtrlLib/Terminal
| gowid | Go | yes | yes | no(1) | https://github.com/gcla/gowid
| xterm.js     | TypeScript | yes         | yes          | no     | https://xtermjs.org
| urwid | Python | no | no | no | https://github.com/urwid/urwid
| JediTerm | Java | yes | no | no | https://github.com/JetBrains/jediterm

1 - Also fails to filter out sixel data, leaving garbage on screen.
