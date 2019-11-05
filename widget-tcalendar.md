TCalendar
=========

TCalendar is a date picker widget.  It displays a calendar with the
day's date highlighted, and can optionally execute a TAction when
double-clicked or the user presses enter.


Screenshots
-----------

![calendar_1](uploads/0458653e9a6f2d865a76ca460e1924a3/calendar_1.png)

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

API
---

[TCalendar API](https://jexer.sourceforge.io/apidocs/api/jexer/TCalendar.html)
