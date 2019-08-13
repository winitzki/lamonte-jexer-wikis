Porting Jexer
=============

One of Jexer's design goals is to be straightforward to port to
another language.  To that end, the following things were done:

* Jexer's license is MIT, enabling anyone to freely create their own
  open- or closed-source derivative works.

* Nearly all of Jexer's API, including private members and functions,
  is documented via Javadoc.

* Jexer uses no low-level C functions directly.  Instead it spawns
  'stty' and 'script' (or 'ptypipe') to accomplish the same tasks as
  termios, forkpty, and ioctl.  If a language can spawn a program and
  read/write to its standard in/out (stdin/stdout), then it can be
  made to do everything Jexer can do.

This document outlines the locations of Jexer's key features, and a
potential roadmap for porting it to another language.  Jexer itself
has gone through this process before: it started its life as a D
language project.

Location Of Key Features
------------------------

| Feature                  | Source files / methods                         |
| ------------------------ | ---------------------------------------------- |
| xterm: mouse input       | backend.ECMA48Terminal.parseMouse()            |
| xterm: mouse input (SGR) | backend.ECMA48Terminal.parseMouseSGR()         |
| xterm: keyboard input    | backend.ECMA48Terminal.processChar()           |
| xterm: sixel output      | backend.ECMA48Terminal.toSixel(), SixelPalette |
| xterm: set raw/cooked termios | backend.ECMA48Terminal.doStty()           |
| xterm: get screen size   | backend.TTYSessionInfo.sttyWindowSize()        |
| xterm: screen output     | backend.ECMA48Terminal.flushString()           |
| terminal: xterm widget   | tterminal.ECMA48                               |
| terminal: sixel input    | tterminal.Sixel                                |
| screen: output functions | backend.LogicalScreen                          |
| screen: CJK output       | backend.GlyphMaker, backend.LogicalScreen.putFullwidthChar() |
| screen: mouse cursor     | TApplication.invertCell()                      |
| input: keyboard          | TKeypress, event.TKeypressEvent                |
| input: mouse             | event.TMouseEvent                              |
| widget hierarchy root    | TWidget                                        |
| window movement/sizing   | TWindow                                        |
| drop-down menus          | TApplication, menu.TMenu, menu.TMenuItem       |
| cell colors              | bits.CellAttributes, bits.Color                |
| cell character / image   | bits.Cell                                      |
| CP437 to Unicode map     | bits.GraphicsChars                             |
| Swing color palette      | backend.SwingTerminal.setDOSColors()           |
| xterm color palette      | backend.ECMA48Terminal.rgbColor()              |


Porting Sequence
----------------

1. Basic Hello World.  Port CellAttributes, Cell, Color, Screen,
   LogicalScreen, ECMA48Terminal, TTYSessionInfo, TKeypress,
   TKeypressEvent, and TMouseEvent.  This gets you a screen to draw
   on, mouse and keyboard input, and raw termios.  If you don't want a
   full windowing system, you can stop here.

2. Basic windowing system.  Port TWidget, TWindow, Backend,
   GenericBackend, ECMA48Backend, and TApplication.  In TApplication,
   strip out the menu management and secondary widget handler code.
   In TWidget, comment out the convenvience widget constructors
   (addLabel, addField, etc.) for now.

3. Add some widgets.  Port TLabel, TButton, and TField.  Build a demo
   application with static text, buttons, and editable text.

4. Add menus.  Port TMenu, TMenuItem, etc.  Put the menu handling back
   into TApplication.

5. Add system-modal widgets.  Port TMessageBox, TInputBox, and
   TFileOpenBox, and modify TApplication's primary/secondary event
   handlers.  System-modal widgets are very handy because they permit
   code in the primary thread to pause, ask for input (handled by the
   secondary thread), and continue on.  The infrastructure for this
   may not be a straightforward port in the target language.  For
   Java, I use two threads pulling off a common input queue; for D, I
   used two fibers that yielded to each other.  You might choose to
   push/pop worker threads/fibers on a stack rather than just have the
   two like Jexer.  Regardless, this may take some effort to work out
   the kinks.

6. Add the remaining widgets at leisure.  Pick and choose which
   widgets you want to have, and port them.  Many are small and easy
   (TPasswordField, TRadioButton, TCheckBox), but some are more
   complex (TTerminal, TTableWidget, TTreeView).

