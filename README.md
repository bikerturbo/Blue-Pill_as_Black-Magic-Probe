# Blue Pill as Black Magic Probe
[Blue Pill](BluePill_wiki.pdf) is a very good universal development board. Now is JTAG/SWD and virtual COM port!
Is it very easy. (original instructions is here https://stm32duinoforum.com/forum/viewtopic_f_37_t_2801.html).

*Note: You must have Python installed on your favorite linux OS ;-)*

## The procedure is simple
1. Download this repository (and extract it to your favorite folder)
2. Connect your Blue Pill with a USB-serial converter ([view here](connection2bluepill.jpg)). 
3. Set BOOT0 jumper on the board to 1 and press reset.
4. Open Terminal and run (*USB-serial converter is on /dev/ttyUSB0*)

```
 sudo python ./Blue-Pill_as_Black-Magic-Probe/stm32loader.py -p /dev/ttyUSB0 -e -w -v -g 0x0 ./Blue-Pill_as_Black-Magic-Probe/blackmagic.bin
```

5. Now you view

```
  Bootloader version 22
  Chip id: 0x410 (STM32 Medium-density)
  Write 256 bytes at 0x8000000
  Write 256 bytes at 0x8000100
  Write 256 bytes at 0x8000200
  ...
  ...
  Read 256 bytes at 0x8000000
  Read 256 bytes at 0x8000100
  Read 256 bytes at 0x8000200
  ...
  ...
  Read 256 bytes at 0x800ED00
  Verification OK
```

6. Disconnect the USB-serial converter and set BOOT0 jumper on the board to 0.
7. Copy this [file](50-black-magic-blue-pill.rules) (it's driver for BMC) to /etc/udev/rules.d/ and restart the system.

**That is all. Congratulations. Now you have JTAG/SWD and virtual COM port!**


### How to connect your new toy?

Now your new BMP is connected to your computer using a USB cable.

*Note: When using the lsusb command, BMP is marked as ID 1d50:6018 OpenMoko, Inc. It's alright.*

Serial Wire Debug Pins are connected to: (*view as /dev/ttyACM0*)

    PB14 is SWDIO
    PA5 is SWCLK

the Virtual Com Port pins are connected to: (*view as /dev/ttyACM0*)

    PA2 is TX
    PA3 is RX



... to be continued :-)
