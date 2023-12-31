TStatusBar
==========

TStatusBar implements a status line with clickable buttons and
associated shortcut keypresses.  Clicking on the status bar, or
pressing one of its shortcut keypresses, will generate an
application-level TCommandEvent.

TStatusBar is unique in many ways:

* It can only be "contained" in a TWindow.

* Its draw() method is called by TApplication, not TWidget's
  drawChildren().

* The status bar is hidden (and will not receive mouse events) if the
  System property "jexer.hideStatusBar" is "true".

* It is the only TWidget to generate TCommandEvent's.  The other
  TCommandEvent's are generated by: backends for disconnect
  notification; TApplication for clipboard cut/copy/paste/clear
  events.

Screenshots
-----------

![statusbar_1](uploads/5a556653f50f40fd64b0a2e66d38952f/statusbar_1.png)

Examples
--------

```Java
statusBar = newStatusBar("Editor");
statusBar.addShortcutKeypress(kbF1, cmHelp, "Help");
statusBar.addShortcutKeypress(kbF2, cmSave, "Save");
statusBar.addShortcutKeypress(kbF3, cmOpen, "Open");
statusBar.addShortcutKeypress(kbF10, cmMenu, "Menu");
```

API
---

[TStatusBar API](https://jexer.sourceforge.io/apidocs/api/jexer/TStatusBar.html)

😻