TCalendar
=========

TCalendar is a date picker widget.  It displays a calendar with the day's date highlighted, and can optionally execute a TAction when double-clicked or the user presses enter.


Screenshots
-----------



Examples
--------

```Java
TCalendar calendar = addCalendar(x, y,
    new TAction() {
         public void DO() {
            messageBox("Calendar", "You selected " + calendar.getValue(),
                TMessageBox.Type.OK);
        }
    }
);
```

