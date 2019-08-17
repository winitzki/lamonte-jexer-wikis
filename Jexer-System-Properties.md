System Properties
=================

This document outlines the system properties that can be set to
customize Jexer.  The table below summarizes the properties and
default values, below which is a more detailed outline.

| Property                  | Default | Description                            |
| ------------------------- | ------- | -------------------------------------- |
| jexer.textMouse           | true    | Show text mouse pointer                |
| jexer.hideMouseWhenTyping | false   | Hide mouse on keystroke everywhere     |
| jexer.Swing               |         | Demo: select backend                   |
| jexer.Swing.cursorStyle   | underline | Swing: cursor style                  |
| jexer.Swing.mouseStyle    | none    | Swing: mouse pointer selection         |
| jexer.Swing.mouseImage    |         | Swing: image to use for mouse icon     |
| jexer.Swing.tripleBuffer  | true    | Swing: use triple-buffering            |
| jexer.Swing.color0        | #000000 | Swing: color for black                 |
| jexer.Swing.color1        | #a80000 | Swing: color for red                   |
| jexer.Swing.color2        | #00a800 | Swing: color for green                 |
| jexer.Swing.color3        | #a85400 | Swing: color for yellow                |
| jexer.Swing.color4        | #0000a8 | Swing: color for blue                  |
| jexer.Swing.color5        | #a800a8 | Swing: color for magenta               |
| jexer.Swing.color6        | #00a8a8 | Swing: color for cyan                  |
| jexer.Swing.color7        | #a8a8a8 | Swing: color for white                 |
| jexer.Swing.color8        | #545454 | Swing: color for black + bold          |
| jexer.Swing.color9        | #fc5454 | Swing: color for red + bold            |
| jexer.Swing.color10       | #54fc54 | Swing: color for green + bold          |
| jexer.Swing.color11       | #fcfc54 | Swing: color for yellow + bold         |
| jexer.Swing.color12       | #5454fc | Swing: color for blue + bold           |
| jexer.Swing.color13       | #fc54fc | Swing: color for magenta + bold        |
| jexer.Swing.color14       | #54fcfc | Swing: color for cyan + bold           |
| jexer.Swing.color15       | #fcfcfc | Swing: color for white + bold          |
| jexer.TEditor.hideMouseWhenTyping | true | Hide mouse on keystroke in text editor windows |
| jexer.TTerminal.closeOnExit | false | Close terminal window when shell exits |
| jexer.TTerminal.hideMouseWhenTyping | true | Hide mouse on keystroke in terminal windows |
| jexer.TTerminal.ptypipe   | false   | Use 'ptypipe' for terminal shell       |
| jexer.TTerminal.shell     |    | Command to use for the terminal shell       |
| jexer.TTerminal.cmdHack   | true    | For Windows, append Ctrl-J after Enter |
| jexer.ECMA48.rgbColor     | false   | ECMA48: emit 24-bit RGB for system colors |
| jexer.ECMA48.wideCharImages | true  | ECMA48: draw CJK/emoji as images       |
| jexer.ECMA48.sixel        | true    | ECMA48: draw images using sixel        |
| jexer.ECMA48.sixelPaletteSize | 1024 | ECMA48: number of colors for sixel images |
| jexer.ECMA48.color0       | #000000 | ECMA48: color for black                |
| jexer.ECMA48.color1       | #a80000 | ECMA48: color for red                  |
| jexer.ECMA48.color2       | #00a800 | ECMA48: color for green                |
| jexer.ECMA48.color3       | #a85400 | ECMA48: color for yellow               |
| jexer.ECMA48.color4       | #0000a8 | ECMA48: color for blue                 |
| jexer.ECMA48.color5       | #a800a8 | ECMA48: color for magenta              |
| jexer.ECMA48.color6       | #00a8a8 | ECMA48: color for cyan                 |
| jexer.ECMA48.color7       | #a8a8a8 | ECMA48: color for white                |
| jexer.ECMA48.color8       | #545454 | ECMA48: color for black + bold         |
| jexer.ECMA48.color9       | #fc5454 | ECMA48: color for red + bold           |
| jexer.ECMA48.color10      | #54fc54 | ECMA48: color for green + bold         |
| jexer.ECMA48.color11      | #fcfc54 | ECMA48: color for yellow + bold        |
| jexer.ECMA48.color12      | #5454fc | ECMA48: color for blue + bold          |
| jexer.ECMA48.color13      | #fc54fc | ECMA48: color for magenta + bold       |
| jexer.ECMA48.color14      | #54fcfc | ECMA48: color for cyan + bold          |
| jexer.ECMA48.color15      | #fcfcfc | ECMA48: color for white + bold         |
| jexer.cjkFont.filename    | NotoSansMonoCJKtc-Regular.otf | Font for CJK characters |
| jexer.emojiFont.filename  | OpenSansEmoji.ttf | Font for emojis              |
| jexer.fallbackFont.filename |       | Font to use when no other available font has a codepoint |



jexer.textMouse
---------------

Used by jexer.TApplication and jexer.backend.SwingTerminal.  If true,
display a text-based mouse pointer, otherwise do not.  (Also, the
Swing backend will display the normal arrow mouse cursor when
textMouse is false.)  Default: true.

jexer.hideMouseWhenTyping
-------------------------

Used by jexer.TApplication.  If true, suppress the text-based mouse
pointer after a user presses a key.  Mouse motion will restore the
pointer.  Default: false.

jexer.Swing
-----------

Used by jexer.demos.Demo1 and jexer.demos.Demo4.  If true, use the
Swing interface for the demo application.  Default: true on Windows
(os.name starts with "Windows") and Mac (os.name starts with "Mac"),
false on non-Windows and non-Mac platforms.

jexer.Swing.cursorStyle
-----------------------

Used by jexer.backend.SwingTerminal.  Selects the cursor style to
draw.  Valid values are: underline, block, outline, and verticalBar.
Default: underline.

jexer.Swing.mouseStyle
----------------------

Used by jexer.backend.SwingTerminal.  Selects the mouse pointer
(java.awt.Cursor) style to use.  Valid values are: none, default,
hand, crosshair, move, and text.  Default: none.

jexer.Swing.mouseImage
----------------------

Used by jexer.backend.SwingTerminal.  Filename containing an image to
use as the mouse pointer.  Filename must be on the classpath.  The hot
spot will be in the middle of the image.

jexer.Swing.tripleBuffer
------------------------

Used by jexer.backend.SwingTerminal.  If true, use triple-buffering
which reduces screen tearing but may also be slower to draw on slower
systems.  If false, use naive Swing thread drawing, which may be
faster on slower systems but also more likely to have screen tearing.
Default: true.

jexer.TEditor.hideMouseWhenTyping
---------------------------------

Used by jexer.TEditorWindow.  If true, suppress the text-based mouse
pointer after a user presses a key within a text editor window.  Mouse
motion will restore the pointer.  Default: true.

jexer.TTerminal.closeOnExit
---------------------------

Used by jexer.TTerminalWindow.  If true, close the window when the
spawned shell exits.  Default: false.

jexer.TTerminal.hideMouseWhenTyping
-----------------------------------

Used by jexer.TTerminalWindow.  If true, suppress the text-based mouse
pointer after a user presses a key within a terminal window.  Mouse
motion will restore the pointer.  Default: true.

jexer.TTerminal.ptypipe
-----------------------

Used by jexer.TTerminalWindow.  If true, spawn shell using the
'ptypipe' utility rather than 'script'.  This permits terminals to
resize with the window.  ptypipe is a separate C language utility,
available at https://gitlab.com/klamonte/ptypipe.  Default: false.

When jexer.TTerminal.ptypipe is true, and jexer.TTerminal.shell is not
set, then the command used for the terminal shell is
`ptypipe /bin/bash --login`

jexer.TTerminal.shell
---------------------

Used by jexer.TTerminalWindow.  If set, use this value to spawn the
shell.  If not set, the following commands are used based on the value
of the os.name system property:

| os.name starts with | Command used for terminal shell |
| ------------------- | ------------------------------- |
| Windows             | cmd.exe                         |
| Mac                 | script -q -F /dev/null          |
| Anything else       | script -fqe /dev/null           |

jexer.TTerminal.cmdHack
-----------------------

Used by jexer.TTerminalWindow.  If true, append a line feed (Ctrl-J,
hex 0x0a) after every enter/return keystroke (carriage return, Ctrl-M,
hex 0x0d).  This is needed for cmd.exe, but might not be for other
shells.  Default: true.

jexer.ECMA48.rgbColor
---------------------

Used by jexer.backend.ECMA48Terminal.  If true, emit T.416-style RGB
colors for normal system colors.  This is expensive in bandwidth, and
potentially terrible looking for non-xterms.  Default: false.

jexer.ECMA48.wideCharImages
---------------------------

Used by jexer.backend.ECMA48Terminal.  If true, draw wide characters
(fullwidth characters) as used by CJK and emoji as images.  This looks
better on terminals loaded without a CJK font, but requires sixel
support.  Default: true.

jexer.ECMA48.sixel
------------------

Used by jexer.backend.ECMA48Terminal.  If true, emit image data using
sixel, otherwise show blank cells where images could be.  This is
expensive in bandwidth, very expensive in CPU (especially for large
images), and will leave artifacts on the screen if the terminal does
not support sixel.  Default: true.

jexer.ECMA48.sixelPaletteSize
-----------------------------

Used by jexer.backend.ECMA48Terminal.  Number of colors to use for
sixel output.  Values are: 2 (black-and-white), 256, 512, 1024, or
2048.  Default: 1024.

jexer.cjkFont.filename
----------------------

Used by jexer.backend.GlyphMaker.  Filename containing the font to use
for CJK.  Filename must be on the classpath.  Default:
NotoSansMonoCJKtc-Regular.otf

Note that if the font is not found, NO ERROR IS REPORTED.

jexer.emojiFont.filename
------------------------

Used by jexer.backend.GlyphMaker.  Filename containing the font to use
for emojis.  Filename must be on the classpath.  Default:
OpenSansEmoji.ttf

Note that if the font is not found, NO ERROR IS REPORTED.

jexer.fallbackFont.filename
---------------------------

Used by jexer.backend.GlyphMaker.  Filename containing the font to use
as a last resort when no other font has the codepoint.  Filename must
be on the classpath.  Default: ""

Note that if the font is not found, NO ERROR IS REPORTED.
