Porting Jexer
=============

One of Jexer's design goals is to be straightforward to port to another language.  To that end, the following things were done:

* Jexer's license is MIT, enabling anyone to freely create their own open- or closed-source derivative works.

* Nearly all of Jexer's API, including private members and functions, is documented via Javadoc.

* Jexer uses no low-level C functions directly.  Instead it spawns 'stty' and 'script' (or 'ptypipe') to accomplish the same tasks as termios, forkpty, and ioctl.  If a language can spawn a program and read/write to its standard in/out (stdin/stdout), then it can be made to do everything Jexer can do.

This document outlines the locations of Jexer's key features, and a potential roadmap for porting it to another language.  Jever itself has gone through this process before: it started its life as a D language project.
