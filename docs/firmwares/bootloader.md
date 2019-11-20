#Bootloader

* [Overview](#Overview)
* [Install Bootloader](#Flash Bootloader):
* [Update Bootloader](#Update Bootloader):
* [Enter Bootloader Mode](#Enter Bootloader Mode):
* [Developer](#Developer):

## Overview

Bootloader is ...

We selected UF2 bootloader as it is easy to use, the UF2 is stands for [USB Flashing Format](https://github.com/Microsoft/uf2) which is developed by Microsoft, it is designed for programming microcontrollers by enumerate it as a mass storage device over USB.

## Install Bootloader

## Update Bootloader

## Enter Bootloader Mode

To enter the bootloader mode on RoboHAT MM1, please plugin the Micro-USB cable to your computer, then double press the reset button located on the right bottom side of the board and above the Grove connecter.
Then you will see the on board Red LED blink in breath mode, then you will see a RoboBoot drive on the your computer, CONGRATULATION your mm1 is currently in the bootloader mode.

## Developer

We used the Adafruit fork of the UF2 code which support both SAMD21 and SAMD51 microcontroller.
