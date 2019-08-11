Jexer - Java Text User Interface Library
========================================

Jexer is a text-based windowing system loosely reminiscent of Borland's [Turbo Vision](http://en.wikipedia.org/wiki/Turbo_Vision) system.  Jexer works on both command-line [Xterm-like terminals](terminals) and on X11/Mac/Windows GUI systems using Swing.

The screenshot below shows several open windows, widgets (buttons, input fields, checkboxes, radiobuttons), and a terminal window:

![Screenshot](https://gitlab.com/klamonte/jexer/raw/master/screenshots/screenshot1.png)



Obtaining Jexer
---------------

Jexer is available on Maven Central:

```xml
<dependency>
  <groupId>com.gitlab.klamonte</groupId>
  <artifactId>jexer</artifactId>
  <version>0.3.1</version>
</dependency>
```

Binary release downloads are also available on [SourceForge.](https://sourceforge.net/projects/jexer/files/jexer/)



Documentation
-------------

* [API docs](https://jexer.sourceforge.io/apidocs/api/index.html)
* Jexer's [high-level design.](high-level-design)
* Jexer [java.lang.System properties.](jexer system properties)
* [Known limitations.](limitations)
* [Supported terminals.](terminals)
* [Recommended fonts for Xterm.](fonts)
* [Porting Jexer to another language.](porting)


Examples
--------

* [Hello World.](hello-world)
* The [official demo.](demo-application)
* Prototype [tiling window manager.](example-tiling-wm)
* Prototype [file viewer.](example-image-viewer)



Widget Gallery
--------------

* [TButton](widget-tbutton)
* [TCalendar](widget-tcalendar)
* [TCheckBox](widget-tcheckbox)
* [TComboBox](widget-tcombobox)
* [TDirectoryList](widget-tdirectorylist)
* [TEditColorThemeWindow](widget-teditcolorthemewindow)
* [TEditorWidget](widget-teditorwidget)
* [TEditorWindow](widget-teditorwindow)
* [TExceptionDialog](widget-texceptiondialog)
* [TField](widget-tfield)
* [TFileOpenBox](widget-tfileopenbox)
* [TFontChooserWindow](widget-tfontchooserwindow)
* [THScroller](widget-thscroller)
* [TImage](widget-timage)
* [TImageWindow](widget-timagewindow)
* [TInputBox](widget-tinputbox)
* [TLabel](widget-tlabel)
* [TList](widget-tlist)
* [TMessageBox](widget-tmessagebox)
* [TPasswordField](widget-tpasswordfield)
* [TProgressBar](widget-tprogressbar)
* [TRadioGroup](widget-tradiogroup)
* [TScrollableWidget](widget-tscrollablewidget)
* [TScrollableWindow](widget-tscrollablewindow)
* [TSpinner](widget-tspinner)
* [TStatusBar](widget-tstatusbar)
* [TTableWidget](widget-ttablewidget)
* [TTableWindow](widget-ttablewindow)
* [TTerminalWindow](widget-tterminalwindow)
* [TText](widget-ttext)
* [TTreeView](widget-ttreeview)
* [TVScroller](widget-tvscroller)
* [TWindow](widget-twindow)

Other
-----

* [Applications Wishlist](apps-wishlist)
* [Jexer Features Wishlist](wishlist)
* [TODOs for this Wiki](Wiki-TODO-List)
