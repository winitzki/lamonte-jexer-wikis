Jexer Image Sequence
====================

Version: 1



Summary
-------

Jexer is a text-based windowing toolkit with widgets for many common
functions such as lists, comboboxes, text fields, radioboxes, and so
on.  Jexer also supports image data in its cells, and uses this for a
variety of functions: images, sixel support in its terminal widget,
and additional font support.

The most widely supported image format for ECMA48-type terminals (DEC
VT series, xterm, other terminal emulators) is sixel, a palette-based
format with a typical limit of 256-1024 colors.  Sixel encoding is
expensive in both CPU and bandwidth, and a single color palette does
not generalize well to all kinds of images.  Jexer therefore desires a
24-bit color image format to overcome these limitations.

A group including developers of several widely-used terminal emulators
has been working on defining the needs and limitations for a standard
that can be implemented in current-generation terminal emulators.  The
discussion has been primarily captured here:
https://gitlab.freedesktop.org/terminal-wg/specifications/issues/12

This document outlines Jexer's current solution.  In researching this
area, one interesting surprise discovery was that the CPU overhead for
encoding/decoding image data to wire format had a much smaller effect
on total throughout versus collecting the image data from the DCS/OSC
sequence in the ECMA48 state parser.  In other words, wire formats
with fewer bytes to transfer win out strongly over image formats with
fewer CPU cycles to compute.  Because of this result, Jexer's default
image format is JPG.



Detection
---------

Jexer detects terminal support for this protocol via the Primary
Device Attributes (DA) / DECID (ESC Z, or 0x9A) sequence.  A terminal
that support this feature will respond by including the parameter
"444" for images.  A recap of the parameters xterm supports is listed
below, with the Jexer images feature response included:

| VT220 (and higher) Response | Description                                |
|-----------------------------|--------------------------------------------|
| 1                           | 132-columns                                |
| 2                           | Printer                                    |
| 3                           | ReGIS graphics                             |
| 4                           | Sixel graphics                             |
| 6                           | Selective erase                            |
| 8                           | User-defined keys                          |
| 9                           | National Replacement Character sets        |
| 1 5                         | Technical characters                       |
| 1 6                         | Locator port                               |
| 1 7                         | Terminal state interrogation               |
| 1 8                         | User windows                               |
| 2 1                         | Horizontal scrolling                       |
| 2 2                         | ANSI color, e.g., VT525                    |
| 2 8                         | Rectangular editing                        |
| 2 9                         | ANSI text locator (i.e., DEC Locator mode) |
| 4 4 4                       | Jexer Images Version 1                     |



Wire Protocol
-------------

The following new sequences are used to transfer image data from
Jexer's ECMA48Terminal backend to the terminal:

| Sequence                                   | Description                 |
|--------------------------------------------|-----------------------------|
| OSC 4 4 4 ; 0 ; Pw ; Ph ; Ps ; {data} BEL  | Display RGB image at cursor |
| OSC 4 4 4 ; 0 ; Pw ; Ph ; Ps ; {data} ST   | Display RGB image at cursor |
| OSC 4 4 4 ; 1 ; Ps ; {data} BEL            | Display PNG image at cursor |
| OSC 4 4 4 ; 1 ; Ps ; {data} ST             | Display PNG image at cursor |
| OSC 4 4 4 ; 2 ; Ps ; {data} BEL            | Display JPG image at cursor |
| OSC 4 4 4 ; 2 ; Ps ; {data} ST             | Display JPG image at cursor |



For the OSC 4 4 4 sequence:

* Pw is the width in pixels.  Valid range is 1 to 10000.

* Ph is the height in pixels.  Valid range is 1 to 10000.

* Ps is the scrolling option.  Valid values are 1 (scroll) or 0 (no scroll).

* The image is processed as shown below:

  - The pixels are drawn starting at the upper-left corner of the text
    cursor position.

  - All pixels in the text cells that are not covered by the image
    itself are set to black (RGB 0/0/0).

  - If Ps is 1, then:

    a. The screen is scrolled up if the image overflows into the
       bottom text row.

    b. The cursor's final position is on the same column as the
       starting cursor position, and on the row immediately below the
       image.

  - If Ps is 0, then:

    a. The screen is never scrolled.

    b. Pixels that would be drawn below the visible region on screen
       are discarded.

    c. The cursor's final position is at the same column and row as
       the starting cursor position, i.e. the cursor does not move at
       all.

  - Pixels that would be drawn to the right of the visible region on
    screen are discarded.

* If the first parameter is 0, then {data} is a base64-encoded string
  of big-endian 8-bit red/blue/green values.  Every 3 octets denotes
  one pixel.  Data must contain a total of Pw * Ph * 3 octets.

* If the first parameter is 1, then {data} is a base64-encoded string
  of a PNG file.

* If the first parameter is 2, then {data} is a base64-encoded string
  of a JPG file.

* If any field is invalid, then nothing is drawn and the cursor is not
  moved.



Implementation Notes
--------------------

Jexer's terminal widget is capable of decoding any image format
supported by javax.image.ImageIO, but scans the file data for PNG and
JPG headers before attempting decoding.  Additional image formats may
be supported in the future.  At this time ImageIO supports the
following formats: PNG, JPG, BMP, WBMP, and GIF.

Jexer's ECMA48 backend always defines scroll=0, i.e. no scrolling.

