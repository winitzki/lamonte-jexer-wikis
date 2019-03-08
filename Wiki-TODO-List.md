Acknowledgments:

  * nikiroo for TTable inspiration

Internal Design:

  * Flow of events from Backend to TApplication to Screen
  * Threading between primary/secondary
  * God classes: TApplication, TWidget, TWindow

Platform Specifics:

  * Supported terminals list for ECMA48 backend
  * POSIX: using ptypipe to achieve resizable TTerminalWindows
  * Linux console: using LCXterm for mouse support

Widgets Gallery

Howto's:

  * Hello World
  * Dialog boxes
  * Prototype tiling WM
  * Prototype file viewer
  * MultiScreen / MultiBackend
  * Using a Backend alone (like jermit)

