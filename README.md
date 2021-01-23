# RPi Pico Hello World

Assuming you aren't using the official setup script on a Raspian system, you'll
need to get CMake, ARM GCC, and, optionally, Doxygen from somewhere.  On Arch,

```
pacman -S cmake arm-none-eabi-gcc arm-none-eabi-newlib arm-none-eabi-gdb doxygen
```

Clone this repository and then run:

```
git submodule update --init
(cd pico-sdk && git submodule update --init)
cd build && cmake .. && make
```

(Don’t be tempted to run a single `git submodule update --init --recursive`
from the root; you’ll pull in 2Gb+ of tinyurl submodules that you don’t need.)

This should generate `hello_world.uf2`

The Pico presents as a USB disk; flashing it just involves copying the UF2 file
onto the disk.

Plug the Pico in while holding down the button.  If it isn’t automounted on
your system run `lsblk` and look for a 128M disk.

Mount the drive and copy `hello_world.uf2` across to it.  As soon as you
unmount the disk the LED on the board should start blinking.
