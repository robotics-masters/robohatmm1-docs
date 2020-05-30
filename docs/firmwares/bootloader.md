#Bootloader

* [Overview](#overview)
* [Install Bootloader](#install-bootloader)
* [Update Bootloader](#update-bootloader)
* [Enter Bootloader Mode](#enter-bootloader-mode)
* [Developer](#developer)

## Overview

Bootloader is ...

We selected UF2 bootloader as it is easy to use, the UF2 is stands for [USB Flashing Format](https://github.com/Microsoft/uf2) which is developed by Microsoft, it is designed for programming microcontrollers by enumerate it as a mass storage device over USB.

## Install Bootloader

Not recommend for beginners.

Please head to our [bootloader github repo](https://github.com/robotics-masters/mm1-hat-bootloader) for more information

## Enter Bootloader Mode

To enter the Bootloader Mode on RoboHAT MM1.

**STEP 1**: Please plugin the Micro-USB cable to your computer,

**STEP 2**: Double press the reset button located on the right bottom side of the board and above the Grove connecter.

Then you will see the on board Red LED blink in breath mode, then you will see a ROBOM4BOOT drive on the your computer.

CONGRATULATION!!! your RoboHAT MM1 is currently in the bootloader mode.

## Update Bootloader

To update the bootloader

**STEP 1**: Please download the latest Bootloader update file with file extension as UF2 from our [Latest Bootloader UF2 file](https://circuitpython.org/board/robohatmm1_m4/).

**STEP 2**: Drag & Drop the latest Bootloader update file you have downloaded from above to the ROBOM4BOOT drive.(note: this is drive only show up in Bootloader mode)

## Developer

We used the Adafruit fork of the UF2 code which supports SAMD51G19 microcontroller which is used on the RoboHAT MM1.
