---
layout: page
title: Quick overview.
show_on_index: true
---

### Lab: make sure hardware and toolchain is working.

We'll use different variations of a blinky light using GPIO 20.

#### 1. Make sure hardware is working:
  1. Connect the USB-to-TTL Serial cable's power (red) and ground  (black)
     wires to the pi.
  2. Plug into your USB port.
  3. Hook your LED up to ground and power to make sure it's wired correctly.
  If it doesn't go on, reverse it.  If still doesn't go on, plug someone
  else's working version into your computer.  If that doesn't work, ask.

#### 2.  Make sure you're able to install firmware, etc:

  1. Unplug the USB-to-pi.
  2. Plug SD card into computer.
  3. Copy the files from firmware/ onto it.
  4. copy part1/blink.bin in this directory to the SD card as kernel.img.
  5. unmount the SD card (don't just pull it out!  data may not be written out.)
  6. connect the LED to GPIO20 and ground. 
     Use docs/gpio.png to figure out which this is.
  7. Plug the SD card into your pi
  8. plug in the USB-to-PI to your USB

It should be blinking.  If you get this working, help anyone else that
is stuck.

Troubleshooting:
   1.  If it's not blinking, swap in someone else's card that is working.
   2. If that works, compare their SD card to yours.
   3. If that doesn't work, try your card in their rpi.  

#### 2.  Use bootloader.

  1. Copy bootloader.bin on your SD card to kernel.img.
  2. Hook the white wire from the TTL to pin 14, and the green to 15.
  3. Run cs49n/bin/rpi-install.py /dev/ttyUSB0 blink.bin

Things should be blinking.

Troubleshooting: pip install {pyserial,xmodem}

#### 3.  make sure your toolchain is working.

Install the toolchain:
   -  For a mac: http://cs107e.github.io/guides/mac_toolchain/
   - For ubuntu/linux:

           sudo add-apt-repository ppa:team-gcc-arm-embedded/ppa
           sudo apt-get update
           sudo apt-get install gcc-arm-none-eabi

   [via https://github.com/eistec/mulle/wiki/Installing-toolchain-%28GCC%29]

Compile blink.s in part2/

   1. Run make.sh
   2. reset pi, use bootloader to load blink.bin
   3. as before: unmount, plug sd card back into pi, plug in TTY-to-USB.

#### 4. make sure you can read and write GPIO memory.

You'll have to write some code by filling in blink.c in part3/.
First test that the code will blink using GPIO16 (it's the pin above GPI20).  
Change the code to work with GPIO20.

   1. look at the broadcom document: docs/BCM2835-ARM-Peripherals.pdf
   pages 90--95. 
   2. write code to set and unset GPIO 20 off and on.
   3. compile, copy to kernel.img, load and run.

Hint:
  1. You write GPFSELn register (pages 91 and 92) to set up a pin as an
  output or input. You'll have to set GPIO 20 in GPFSEL1 to output.

  2. You'll turn it off and on by writing to the GPSET0 and GPCLR0
  registers on page 95.  We write to GPSET0 to set a pin (turn it on)
  and write to GPCLR0 to clear a pin (turn it off).

Troubleshoot as before.

If you get this working, change the code to work with any GPIO pin.

#### Additional information

More links:
	1. useful baremetal information: (http://www.raspberrypi.org/forums/viewtopic.php?t=16851)
	2. more baremetalpi: (https://github.com/brianwiddas/pi-baremetal)

	3. And even more bare metal pi: (http://www.valvers.com/embedded-linux/raspberry-pi/step01-bare-metal-programming-in-cpt1)


