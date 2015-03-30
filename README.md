# Introduction

This add-on to [Arduino] {at least 1.6.2} adds support for ATMEL's XMEGA
line of microcontrollers.

Most of the hard work has been done by [Xmegaduino] folks. But I just
wanted an add-on to regular [Arduino] IDE.

I've added support for USB enabled atxmega chips (at the moment, one
-A4U board).

## Caveats (for USB boards)

- USB support is alpha quality - so may be quite buggy.
- Only DFU bootloaded boards for now.
- Autoreset is not implemented - you need to put your board into DFU
  mode manually before uploading.
- Various third-party libraries might (and most probably do) need some
  adjustments to work with XMEGAs.

# Installation

Download zip (button on the right) and unpack to your
`ARDUINO_SKETCHES_FOLDER/hardware`. Restart IDE.

# Usage

Select one of the Xmega boards in your IDE. Enjoy!

# Remarks and ramblings

- Only USB support present at the moment is for Serial (e.g. like the
  standard Arduino Leonardo). So no Keyboard, Mouse ... (like
  [Teensyduino]) support yet.
- The USB stack is based on my quick-and-dirty XMEGA-USB code, based
  originally on Nonolith Labs' [USB-XMEGA] {so not on
  Dean Camera's excellent [LUFA] library - mainly because I didn't want
  to have to deconstruct [LUFA]'s complicated build system}. So quite
  possibly it's buggy. However it should be good enough for some basic
  Serial support.
- The build settings assume DFU bootloader. The flashing is done with
  [dfu-programmer], supplied in the zip (tested on Mac OS X, Linux (i386
  and x86_64 - you'll need to install dfu-programmer manually on arm).
- I've only tested it on [X-A4U-stick] - I don't have any other XMEGA
  boards.



[Teensyduino]: https://www.pjrc.com/teensy/teensyduino.html
[LUFA]: http://www.fourwalledcubicle.com/LUFA.php
[Xmegaduino]: https://github.com/akafugu/Xmegaduino
[Arduino]: http://arduino.cc
[X-A4U-stick]: https://flabbergast.github.io/X-A4U-r2
[dfu-programmer]: https://dfu-programmer.github.io/
[USB-XMEGA]: https://dfu-programmer.github.io/
