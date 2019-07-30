TImage
======

TImage renders a piece of a bitmap image on screen.

Screenshots
-----------

Examples
--------

```Java
    BufferedImage image = ImageIO.read(file);
    TImage imageField = new TImage(this, 0, 0, getWidth() - 2, getHeight() - 2,
        image, 0, 0, null);
```

