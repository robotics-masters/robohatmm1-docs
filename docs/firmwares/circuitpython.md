#CircuitPython Firmware

* [Overview](#overview)
* [Enter Bootloader Mode](#bootloader-mode)
* [Download latest CircuitPython](#download)
* [Flash CircuitPython](#flash)

## Overview
Thanks to Adafruit for the implementation of [CircuitPython](https://learn.adafruit.com/welcome-to-circuitpython/what-is-circuitpython)![donkey](/assets/logos/rpi_logo.png)

CircuitPython is a programming language designed to simplify experimenting and learning to program on low-cost microcontroller boards. It makes getting started easier than ever with no upfront desktop downloads needed. Once you get your board set up, open any text editor, and get started editing code. It's that simple.

CircuitPython ships pre-installed on all RoboHAT MM1 boards.  This section is only if you wish to update to the latest CircuitPython firmware, or if you want to switch back to CircuitPython firmware after play around with other firmwares.

##Bootloader Mode

First you need to put the board into Bootloader Mode.  This allows you to upload new firmware to the RoboHAT MM1.

To enter the Bootloader Mode on RoboHAT MM1.

**1**: Please plugin the Micro-USB cable to your computer,

**2**: Double press the reset button located on the right bottom side of the board and above the Grove connecter.

Then you will see the on board Red LED blink in breathing mode, then you will see a ROBOM4BOOT drive on the your computer.

[More Information](/firmwares/bootloader/#enter-bootloader-mode)

##Download

Please visit Adafruit CircuitPython [firmware download page](https://circuitpython.org/board/robohatmm1_m4/)
Please choose the relevant language you want to use for the CircuitPython REPL and then click DOWNLOAD .UF2 NOW button, you will have a file with name like this "adafruit-circuitpython-robohatmm1_m4-en_US-5.0.0-beta.0.uf2".

The latest CircuitPython version is: 5.1

##Flash

To flash the firmware just simply drag and drop the firmware file you have downloaded above with .uf2 to the "ROBOM4BOOT" USB drive.  

Then wait for the circuitPython firmware to boot up, then you will see the Red LED blinks for a bit and then stop blinking, then you will see a "CIRCUITPY" USB drive show up on you computer.

##Custom Boards
Important: Not recommend for beginners.

Please head to our [circuitpython github repo](https://github.com/robotics-masters/mm1-hat-cpy-native) for more information

There is also a guide - [CircuitPython: Creating Custom Boards](https://www.hackster.io/wallarug/circuitpython-creating-custom-boards-8e979e) - that you can follow and use if you want to build your own custom board or firmware.

## Next: [Programming in CircuitPython](/guide/circuitpython/).
