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
  <version>0.3.0</version>
</dependency>
```

Binary release downloads are also available on [SourceForge.](https://sourceforge.net/projects/jexer/files/jexer/)

Documentation
-------------

* [API docs](https://jexer.sourceforge.io/apidocs/api/index.html)
* Jexer's [high-level design.](high-level-design)
* Jexer [java.lang.System properties.](system-properties)
* [Known limitations.](limitations)



Examples
--------

* Prototype [tiling window manager.](example-tiling-wm)
* Prototype [file viewer.](example-image-viewer)
* The [official demo.](demo-application)


Widget Gallery
--------------

* [TButton](widget-tbutton)
* [TCalendar](widget-tcalendar)
* [TCheckBox](widget-tcheckbox)
* [TComboBox](widget-tcombobox)
* [TDirectoryList](widget-tdirectorylist)
* [TEditor](widget-teditor)
* [TField](widget-tfield)
* [TFileOpenBox](widget-tfileopenbox)
* [TFontChooserWindow](widget-tfontchooserwindow)
* [TImage](widget-timage)
* [TInputBox](widget-tinputbox)
* [TLabel](widget-tlabel)
* [TList](widget-tlist)
* [TMessageBox](widget-tmessagebox)
* [TPasswordField](widget-tpasswordfield)
* [TProgressBar](widget-tprogressbar)
* [TRadioGroup](widget-tradiogroup)
* [TSpinner](widget-tspinner)
* [TTable](widget-ttable)
* [TTerminalWindow](widget-tterminalwindow)
* [TText](widget-ttext)
* [TWindow](widget-twindow)



Other
-----

[TODOs](Wiki-TODO-List)
