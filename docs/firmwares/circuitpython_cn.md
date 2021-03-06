#Circuit Python Firmware

* [Overview](#overview)
* [Enter Bootloader Mode](#bootloader-mode)
* [Download latest MM1 CircuitPython firmware](#download-firmware)
* [Flash Firmware](#flash-firmware)

## Overview
Thanks to Adafruit for the implementation of [CircuitPython](https://learn.adafruit.com/welcome-to-circuitpython/what-is-circuitpython)![donkey](/assets/logos/rpi_logo.png)

CircuitPython is a programming language designed to simplify experimenting and learning to program on low-cost microcontroller boards. It makes getting started easier than ever with no upfront desktop downloads needed. Once you get your board set up, open any text editor, and get started editing code. It's that simple.

CircuitPython ships pre-installed on all RoboHAT MM1 boards.  This section is only if you wish to update to the latest CircuitPython firmware, or if you want to switch back to CircuitPython firmware after play around with other firmwares.

##Bootloader Mode

first you need to put the board into Bootloader Mode.  This allows you to upload new firmware to the RoboHAT MM1.

To enter Bootloader Mode please follow [Enter Bootloader Mode](/firmwares/bootloader/#enter-bootloader-mode) guide

##Download Firmware

Please visit Adafruit CircuitPython [firmware download page](https://circuitpython.org/board/robohatmm1_m4/)
Please choose the relevant language you want to use for the CircuitPython REPL and then click DOWNLOAD .UF2 NOW button, you will have a file with name like this "adafruit-circuitpython-robohatmm1_m4-en_US-5.0.0-beta.0.uf2".

The latest CircuitPython version is: 5.0.0

##Flash Firmware

To flash the firmware just simply drag and drop the firmware file you have downloaded above with .uf2 to the "ROBOM4BOOT" USB drive.  

Then wait for the circuitPython firmware to boot up, then you will see the Red LED blinks for a bit and then stop blinking, then you will see a "CIRCUITPY" USB drive show up on you computer.

## Next: [Programming in CircuitPython](/guide/circuitpython/).
