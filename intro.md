---
layout: page
title: Quick overview.
show_on_index: true
---

### Overview

This class is project-based.  The inital part will involve buying 
interesting devices, hooking them up to your r/pi B+, and writing the
cleanest, small code you can to initialize/use them.  You'll document
the code, take photos of the setup, and post these on github. 

I believe this is one of the simplest, real things you can do to get a
large number of people using your code --- there are so many devices out
there, and almost all have truly awful documentation, which can easily
take a day to decode, with uncertain chances of success.  Often the code
needed to drive them is 10-20 lines.   Your examples will let people
use a new device in minutes.


You can work either solo or with a small team.  The main goal is to
do interesting things.   After doing a few devices you can switch to
project-mode and build something based on the devs your group (or other
groups) have shown how to use.

Next class we'll get your pi booted up, and sending binaries across
the serial port.  To get up to speed:
  - [cs107e] (http://cs107e.github.io/guides/) cs107e's notes on
	setting up the pi.

  -  [Broadcom BCM2835 Peripherals Documentation](http://www.raspberrypi.org/wp-content/uploads/2012/02/BCM2835-ARM-Peripherals.pdf)

If you want to get a head start on devices, these sites are good places
to look:

 1.  [adafruit](https://www.adafruit.com)
 2.  [sparkfun](https://www.sparkfun.com)
 3.  [jameco](https://www.jameco.com) --- these guys
	have everything, but the previous two are significantly more
	beginner-friendly.

To start with, it's good to find ones that are cheap (say $1-$5) without
too many electrical wiring requirements.  After the first few, we can
look at fancier ones.   

Longer term, there's no need to stay with the R/Pi 1B (our initial
machine) but can branch out to versions (the pi 0 is a good, small
footprint one to use), or different manufacturers.

### Rust

As you write this code you'll likely discover that C, while fairly 
translucent also allows very difficult to track down bugs.  We may
switch halfway through to reimplement some amount of code in Rust,
a modern language that prevents many memory errors possible in C, 
while also giving powerful support for generics and a cleaner method of
semi-OO programming than C++ (low bar, I know).  Some good places to 
start:

 1. [the book](https://doc.rust-lang.org/std/)
 2. [a good podcast](https://soundcloud.com/oreilly-radar/jim-blandy-and-jason-orendorff-on-rust)
 3. [nice cliff notes](https://www.blaenkdenum.com/notes/rust/)

### Computer controlled fabrication (CNC)

In addition, a final topic may be the use of CNC machines to fabricate
actual atoms using code you write.   This is more speculative, since it
hinges on how to give you guys safe access to 12,000lb machines that can
destroy themselves despite you not having training in being machinists.
I believe this can be done, so we'll see how the quarter progresses.

  - [excerpt] (strap-cut.mp4)
