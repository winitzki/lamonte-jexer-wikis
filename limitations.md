Known Issues / Arbitrary Decisions
==================================

Some arbitrary design decisions had to be made when either the obviously expected behavior did not happen or when a specification was ambiguous.  This section describes such issues.

- Sixel output on the bottom row (usually the status line) will cause xterm to scroll the window.  This affects double / full-width characters (such as CJK) and images.

- See jexer.tterminal.ECMA48 for more specifics of terminal emulation limitations.

- TTerminalWindow uses cmd.exe on Windows.  Output will not be seen until enter is pressed, due to cmd.exe's use of line-oriented input (see the ENABLE_LINE_INPUT flag for GetConsoleMode() and SetConsoleMode()).

- TTerminalWindow by default launches 'script -fqe /dev/null' or 'script -q -F /dev/null' on non-Windows platforms.  This is a workaround for the C library behavior of checking for a tty: script launches $SHELL in a pseudo-tty.  This works on Linux and Mac but might not on other Posix-y platforms.

- Closing a TTerminalWindow without exiting the process inside it may result in a zombie 'script' process.

- When using the Swing backend, and not using 'ptypipe', closing a TTerminalWindow without exiting the process inside it may result in a SIGTERM to the JVM causing it to crash.  The root cause is currently unknown, but is potentially a bug in more recent releases of the 'script' utility from the util-linux package.

- TTerminalWindow can only notify the child process of changes in window size if using the 'ptypipe' utility, due to Java's lack of support for forkpty() and similar.  ptypipe is available at https://gitlab.com/klamonte/ptypipe.

- Java's InputStreamReader as used by the ECMA48 backend requires a valid UTF-8 stream.  The default X10 encoding for mouse coordinates outside (160,94) can corrupt that stream, at best putting garbage keyboard events in the input queue but at worst causing the backend reader thread to throw an Exception and exit and make the entire UI unusable.  Mouse support therefore requires a terminal that can deliver either UTF-8 coordinates (1005 mode) or SGR coordinates (1006 mode).  Most modern terminals can do this.

- jexer.session.TTYSession calls 'stty size' once every second to check the current window size, performing the same function as ioctl(TIOCGWINSZ) but without requiring a native library.

- jexer.backend.ECMA48Terminal calls 'stty' to perform the equivalent of cfmakeraw() when using System.in/out.  System.out is also (blindly!) put in 'stty sane cooked' mode when exiting.

- jexer.backend.ECMA48Terminal uses a single palette containing MAX_COLOR_REGISTERS colors for all sixel images.  These colors are generated in the SixelPalette.makePalette() method with bits for hue, saturation, and luminance, and the two extremes set to pure black and pure white.  This provides a reasonable general-purpose palette light on CPU, but at a cost that individual images do not look as good as the terminal is actually capable of.

