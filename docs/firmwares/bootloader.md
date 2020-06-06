#Bootloader

**Summary**

* [Overview](#overview)
* [Enter Bootloader Mode](#enter-bootloader-mode)
* [Update Bootloader](#update-bootloader)
* [Custom Boards](#custom-boards)

## Overview

The Bootloader launches when you start the device and is a special operating system software that knows how to operating the hardware and software stored on the MCU.

We selected UF2 bootloader as it is easy to use, the UF2 is stands for [USB Flashing Format](https://github.com/Microsoft/uf2) which is developed by Microsoft, it is designed for programming microcontrollers by enumerate it as a mass storage device over USB.

We used the [Adafruit fork](https://github.com/adafruit/uf2-samdx1/) of the UF2 code which supports SAMD51G19 microcontroller which is used on the RoboHAT MM1.

##Enter Bootloader Mode

To enter the Bootloader Mode on RoboHAT MM1.

**1**: Please plugin the Micro-USB cable to your computer,

**2**: Double press the reset button located on the right bottom side of the board and above the Grove connecter.

Then you will see the on board Red LED blink in breathing mode, then you will see a ROBOM4BOOT drive on the your computer.

CONGRATULATIONS!!! Your RoboHAT MM1 is currently in the bootloader mode.

##Update Bootloader

To update the bootloader

**1**: Please download the latest Bootloader update file with file extension as UF2 from our [Latest Bootloader UF2 file](https://circuitpython.org/board/robohatmm1_m4/).

**2**: Drag & Drop the latest Bootloader update file you have downloaded from above to the ROBOM4BOOT drive.(note: this is drive only show up in Bootloader mode)


##Custom Boards

Important: Not recommend for beginners.

Please head to our [bootloader github repo](https://github.com/robotics-masters/mm1-hat-bootloader) for more information

There is also a guide - [UF2 Bootloader: Creating Custom Boards](https://www.hackster.io/wallarug/uf2-bootloader-creating-custom-boards-c9620c) - that you can follow and use if you want to build your own custom bootloader.