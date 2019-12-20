# About Robo HAT MM1

Robo HAT MM1  is an open source robotics controller board designed for Single Board Computers with standard 40pin GPIO(eg. Raspberry Pi, Jetson Nano etc.). It is education focused but works in many applications. The Robo HAT provides all the hardware you need in one simple, easy-to-use form factor. It removes the initial barriers to starting any robotics project.

---------
![Robo HAT MM1 image](robohatmm1.png)

## Features & Specifications

* **Processor**: 120 MHz [SAM D51G (M4)](http://ww1.microchip.com/downloads/en/DeviceDoc/60001507E.pdf)
* **Memory**: 192 KB SRAM
* **Storage:** 512 KB internal programmable flash + additional 8 MB SPI flash
* **Multi-product Compatibility**
    * Jetson Nano
    * Raspberry Pi: all models with 40 pin header
        * Model B+, 2B, 2B+, 3B and 3B+
        * Model A+ and 3A+
        * Zero and Zero W
* **Raspberry Pi Interfacing**  
    - Two (2) GPIO directly to Raspberry Pi (SW programming)  
    - Two (2) GPIO directly to Raspberry Pi (UART-serial console)  
    - I²C or SPI to Raspberry Pi  
    - EEPROM recognition   
* **Programmable I/O:** All are re-programmable to match a supported special function
    - Eight (8) x 16-bit servo output (programmable up to 24-bit)
    - Four (4) x 16-bit RC controller input
    - Two (2) x Serial console pass through
    - One (1) x NeoPixel output
    - Nine (9) x GPIO pins through SPI / GPS ports
* **Sensor Interfacing:** Also re-programmable as general IO pins
    * [Dronecode](https://wiki.dronecode.org/workgroup/connectors/start) Compatible Connectors
         - SPI
         - GPS
         - USART
         - I²C
* **Triple-redundant Power Supply Support**
    - Feedback through servo power rail (e.g., from ESC)
    - 5 V from on-board regulator powered through main battery
    - 5 V from on-board regulator power through backup LiPo battery + charger via USB  
* **Built-in Protection**
    - USB Port is protected from voltage spikes
    - All power rails are protected by reverse voltage protection circuits.
    - 5V Main power regulator is able to provide 5A continues and 8A peak.
* **Sensors**
    - [INA219](http://www.ti.com/lit/ds/symlink/ina219.pdf) current sensor
    - [MPU9250 9DoF](https://www.invensense.com/products/motion-tracking/9-axis/mpu-9250/) high-precision IMU
    - Add-on boards through I²C and SPI (such as pressure sensor, secondary IMU, etc)
* **Physical Dimensions**
    * Standard HAT format
    * Length: 65 mm
    * Depth: 56.5 mm
    * Height: 30 mm

----------------

# Get Started

Robo HAT MM1 support for [Adafruit CircuitPython](https://circuitpython.org/), [Arduino IDE](https://www.arduino.cc/), and other libraries the Robo HAT is able to act as a single solution for all projects great and small.

## Bootloader

[UF2 bootloader](firmwares/bootloader.md)

## Firmware Options
1. [CircuitPython](firmwares/circuitpython.md)
2. [Arduino](firmwares/arduino.md)
3. [SeeSaw](firmwares/seesaw.md) -- TO-DO
4. [Dronecode](firmwares/dronecode.md) -- TO-DO

# Board Pinout

![Pinout](/assets/pinout_map.jpg)

---------------

## Installation

<!-- [How to install](guide/install_software.md) -->

-----------------------
