TComboBox
=========

TComboBox is a combobox that has a drop-down list and an edit field.  A TAction can also be executed when the field is updated.  Alt-Down can be used to show the drop-down; kbEsc will close the drop-down.

Screenshots
-----------

![combobox_1](uploads/3f9872cf156289ae244e65bc8fa7680d/combobox_1.png)

![combobox_2](uploads/2c4aeb88cc2ac89a30e32abf53cd1073/combobox_2.png)

Examples
--------

```Java
TComboBox comboBox = addComboBox(x, y, 12, comboValues, 2, 6,
    new TAction() {
        public void DO() {
            messageBox("ComboBox", "You chose: " + comboBox.getText(),
                TMessageBox.Type.OK);
        }
    }
);
```

