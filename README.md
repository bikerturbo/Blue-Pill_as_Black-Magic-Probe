# Blue Pill as Black Magic Probe
Blue Pill is a very good universal development board. Now is JTAG/SWD and virtual COM port!
Is it very easy. (original instructions is here https://stm32duinoforum.com/forum/viewtopic_f_37_t_2801.html) 

## Step 1:
Connect your Blue Pill with a USB-to-Serial Converter ([view here](connection2bluepill.jpg)). Set BOOT0 jumper on the board to 1 and press reset.

## Step 2:
(on Linux)

Open Terminal and run: sudo python stm32loader.py -p /dev/ttyUSB0 -e -w -v -g 0x0 blackmagic.bin

... to be continued :-)
