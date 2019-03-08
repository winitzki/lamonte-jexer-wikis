Jexer's High-Level Design
=========================

Jexer has three major areas of function: user-facing input/output (events and screen), window management (TApplication), and widgets (TWidget) and windows (TWindow).  This document describes in a general manner what these pieces do and how they communicate.

The Big Picture
---------------

```mermaid
graph RL;
  X(Physical Keyboard) --> T(ECMA48Terminal / SwingTerminal)
  Y(Physical Mouse) --> T
  T -- flushPhysical --> Z(Physical Screen);
  T -- getEvents --> B(Backend);
  B -- TInputEvent --> C(TApplication);
  C --> TH1((Primary Thread));
  C --> TH2((Secondary Thread));
  TH1 -- onKeyboard --> W1[Window 1];
  TH1 -- onMouseDown --> W2[Window 2];
  TH1 -- onMouseMotion --> W3[ ... ... ... ];
  TH1 -- onResize --> W4[ Window N ];
  TH1 -- drawAll --> DA{Draw To Screen}
  DA --> W1;
  DA --> W2;
  DA --> W3;
  DA --> W4;
  W1 -- draw --> E(Screen);
  W2 -- draw --> E;
  W3 -- draw --> E;
  W4 -- draw --> E;
  E --> T;
  B -- getScreen --> C;
```

Events And Screen
-----------------


Window Management
-----------------



Widgets And Windows
-------------------

