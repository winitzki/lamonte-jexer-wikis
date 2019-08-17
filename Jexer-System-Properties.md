System Properties
=================

The following properties control features of Jexer:

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

jexer.TTerminal.ptypipe
-----------------------

Used by jexer.TTerminalWindow.  If true, spawn shell using the
'ptypipe' utility rather than 'script'.  This permits terminals to
resize with the window.  ptypipe is a separate C language utility,
available at https://gitlab.com/klamonte/ptypipe.  Default: false.

jexer.TTerminal.closeOnExit
---------------------------

Used by jexer.TTerminalWindow.  If true, close the window when the
spawned shell exits.  Default: false.

jexer.TTerminal.hideMouseWhenTyping
-----------------------------------

Used by jexer.TTerminalWindow.  If true, suppress the text-based mouse
pointer after a user presses a key within a terminal window.  Mouse
motion will restore the pointer.  Default: true.

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
