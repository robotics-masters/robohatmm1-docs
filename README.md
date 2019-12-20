# Robo HAT MM1 Docs

![Robo HAT MM1 image](robohatmm1.png)

The Robotics Masters Robo HAT MM1 is an open source robotics controller board for Raspberry Pi. It is education focused but works in many applications. The Robo HAT provides all the hardware you need in one simple, easy-to-use form factor. It removes the initial barriers to starting any robotics project.

With support for Adafruit CircuitPython, Arduino IDE, and other libraries the Robo HAT is able to act as a single solution for all projects great and small.

This is the starting point for anyone who has the Robo HAT MM1 and is looking to build great projects!

## Hardware

 - [SAMD21G18](https://www.microchip.com/wwwproducts/en/ATsamd21g18) Processor or [SAMD51G19A](https://www.microchip.com/wwwproducts/en/ATSAMD51G19A).  This is the same chip(s) used in many Adafruit Feather designs.
 - Built-in USB battery charger. Charges at 900mA maximum.
 - 8MB Flash Storage for CircuitPython
 - 8 x 16 Bit PWM Outputs
 - 4 x Analog Inputs
 - 5V 2.5A power supply.  Powers Raspberry Pi and board peripherals.
 - INA219 Current Sensor
 - MPU9250 IMU
 - SPI, GPS and UART available connections
 - 5 x Serial communication ports
 - SeeedStudio GROVE System connector
 
## Purchase

Available on [Crowd Supply Campaign Page](https://www.crowdsupply.com/robotics-masters/robo-hat-mm1)


## Software Development

### Robotics Masters Forks and Dev Branches

- [Arduino](https://github.com/robotics-masters/mm1-hat-arduino)
- [ArduPilot](https://github.com/robotics-masters/ardupilot)
- [Bootloader](https://github.com/robotics-masters/mm1-hat-bootloader)
- [CircuitPython](https://github.com/robotics-masters/mm1-hat-cpy-native)
- [Donkey Car](https://github.com/robotics-masters/donkeycar)
- [SeeSaw](https://github.com/robotics-masters/seesaw)

### Official Repositories

- [ArduPilot by ArduPilot](https://github.com/ArduPilot/ardupilot/)
- [Bootloader by Adafruit](https://github.com/adafruit/uf2-samdx1/)
- [Bootloader by Microsoft](https://github.com/Microsoft/uf2-samdx1)
- [CircuitPython by Adafruit](https://github.com/adafruit/circuitpython)
- [Donkey Car](https://github.com/autorope/donkeycar)
- [SeeSaw by Adafruit](https://github.com/adafruit/seesaw)

## Developers

- [@wallarug](https://github.com/wallarug)
- [@hmic](https://github.com/hmic)
- [@peterpanstechland](https://github.com/peterpanstechland)


## Select a Firmware

Depending on what you are doing, you will want to select the right Firmware.  There are currently three different options.

* CircuitPython:  Donkey Car (RC Control), IMU Robot Arm, Sensors
* SeeSaw (SAMD21 Only): ArduPilot, Donkey Car (no RC control), Voice Robot Arm
* Arduino IDE: backwards support for sensors

## License

GNU GENERAL PUBLIC LICENSE
