# About (by Felix)

I started with my brand new arduino uno and had some big problems with the
original arduino ide as it simply won't write the flash due to "identity
something". Therefore i searched the web in order to find a Makefile which
would actually work for me.

I had to change the baud rate in the makefile but otherwise it stayed the
same. This project will be used to finally start with arduino and use the
knowledge of this 1 evening session in order to get code of other people
running on my UNO.


# About (by Mark Hellewell)

I was having some trouble getting avr-gcc to compile arduino sketches on Arch Linux using the Makefile from ardunio.cc.  This is my modified Makefile, that now works OK.  I'm using [the Arduino AUR package](http://aur.archlinux.org/packages.php?ID=8388 "AUR package for arduino").

The first time you use this Makefile you'll need to run a `sudo make` - or `su` equivalent - the permissions on the AUR package directory (rightly) do not permit user writes, and the Makefile needs to create the initial versions of some libraries.

I also found it necessary to apply the diff from comment 3 of [this thread](http://code.google.com/p/arduino/issues/detail?id=104 "Google Code comment") against `Print.cpp` and `Print.h` in the arduino core directory installed by the AUR package (changes the diff makes to files other than these two can be ignored).  Otherwise there will be warnings about the `Print.o` library.

Now `make` and `make upload` should work properly!

## Changes

You will have to change the `MCU=atmega328p` line if you're not on a Duemilanove like me.
