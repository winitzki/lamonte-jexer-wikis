Internal Design:

  * Flow of events from Backend to TApplication to Screen
  * Threading between primary/secondary
  * God classes: TApplication, TWidget, TWindow

Platform Specifics:

  * POSIX: using ptypipe to achieve resizable TTerminalWindows
  * Linux console: using LCXterm for mouse support

Widgets Gallery
  * Widget template:
    * Screenshot(s)
    * Example usage
    * Link to Javadoc
  * For each widget:
    * Fix PMD warnings
    * Fix checkstyle issues

Howto's:

  * ~~Hello World~~
  * ~~Prototype tiling WM~~
  * ~~Prototype file viewer~~
  * Dialog boxes: TMessageBox, TInputBox, TFileOpenDialog
  * MultiScreen / MultiBackend
  * Using TWindowBackend to run an application inside a window
  * Using a Backend alone (like jermit's Qodem UI)

