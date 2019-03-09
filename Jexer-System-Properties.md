System Properties
=================

The following properties control features of Jexer:

jexer.Swing
-----------

Used only by jexer.demos.Demo1 and jexer.demos.Demo4.  If true, use the Swing interface for the demo application.  Default: true on Windows (os.name starts with "Windows") and Mac (os.name starts with "Mac"), false on non-Windows and non-Mac platforms.

jexer.Swing.cursorStyle
-----------------------

Used by jexer.backend.SwingTerminal.  Selects the cursor style to draw.  Valid values are: underline, block, outline.  Default: underline.

jexer.Swing.tripleBuffer
------------------------

Used by jexer.backend.SwingTerminal.  If true, use triple-buffering which reduces screen tearing but may also be slower to draw on slower systems.  If false, use naive Swing thread drawing, which may be faster on slower systems but also more likely to have screen tearing.  Default: true.

jexer.TTerminal.ptypipe
-----------------------

Used by jexer.TTerminalWindow.  If true, spawn shell using the 'ptypipe' utility rather than 'script'.  This permits terminals to resize with the window.  ptypipe is a separate C language utility, available at https://gitlab.com/klamonte/ptypipe.  Default: false.

jexer.TTerminal.closeOnExit
---------------------------

Used by jexer.TTerminalWindow.  If true, close the window when the spawned shell exits.  Default: false.

jexer.ECMA48.rgbColor
---------------------

Used by jexer.backend.ECMA48Terminal.  If true, emit T.416-style RGB colors for normal system colors.  This is expensive in bandwidth, and potentially terrible looking for non-xterms.  Default: false.

jexer.ECMA48.sixel
------------------

Used by jexer.backend.ECMA48Terminal.  If true, emit image data using sixel, otherwise show blank cells where images could be.  This is expensive in bandwidth, very expensive in CPU (especially for large images), and will leave artifacts on the screen if the terminal does not support sixel.  Default: true.
