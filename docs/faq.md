# FAQ
---------
I have relieved a lot of questions about the Robo HAT MM1 and the different software options.
I'm going to answer all the questions to the best that I know.   There was a lot of them.
This document is a work in progress.  Updated: 10/05/2020.

# General FAQ
> Where can I buy a Robo HAT MM1?

You can currently buy them from Crowd Supply from [here](https://www.crowdsupply.com/robotics-masters/robo-hat-mm1).  

The Robo HAT is now also available from [robocarstore.com](https://www.robocarstore.com/products/robo-hat-mm1). 

Both ship world-wide.

# Software FAQ
> Which firmware should I choose?

There are two options that you can go with at the moment.  [CircuitPython](firmwares/circuitpython) or [Arduino IDE](firmwares/arduino).
If you want to use CircuitPython, you can download it from the CircuitPython.org website and follow the guide here - [Getting Started with Robo HAT MM1 (CircuitPython)](https://www.hackster.io/wallarug/getting-started-with-robohat-mm1-circuitpython-d3ee77).   This option is ideal if you are planning on using any of the below:
- Python Language Variant
- The Donkey Car Platform - Guide for [Raspberry Pi](https://www.hackster.io/wallarug/autonomous-cars-with-robo-hat-mm1-8d0e65), Guide for [Jetson Nano](https://www.hackster.io/wallarug/donkey-car-with-jetson-nano-robo-hat-mm1-e53e21)
- Sensors - [IMU](https://github.com/wallarug/CircuitPython_MPU9250), GPS, [Current Sensor](https://github.com/adafruit/Adafruit_CircuitPython_INA219), etc
- Experimenting with RM EDU Car Kit - [GitHub](https://github.com/robotics-masters/EduCar).

If you want to use Arduino IDE, you need to follow the Getting Started with Robo HAT MM1 (Arduino) Guide.  This option is good if you are planning on:
- C++ Language Variant
- Firmata Firmware
- Multiple Serial Ports for GPS or need USB Serial Native Support
- Using already available Arduino Libraries - such as GPS, CharLCD, etc.

> When should I update the Arduino or CircuitPython Firmware?

The Arduino firmware rarely will be updated.  Robotics Masters Limited will put up an update notice on [Twitter]() and [Facebook]() when this is updated.
The CircuitPython firmware is updated every week by Adafruit Industries.  It is best to check for a new version of CircuitPython every month and only use the stable firmware from [CircuitPython.org](https://circuitpython.org/).   The Robotics Masters team will send out updates on Social Media when it is time to update.
If you are concerned, you can always send me a message directly and I can let you know.

> Where can I find the latest CircuitPython Firmware?

You can always download the latest CircuitPython firmware from the CircuitPython website - https://circuitpython.org/board/robohatmm1_m4/.  You do not need to compile it, just upload onto the board using the UF2 File Format.

> Where can I find the latest Arduino Firmware?

Arduino IDE downloads firmware a little bit strangely.  You need to follow the [Getting Started with Arduino IDE](https://www.hackster.io/wallarug/getting-started-with-robohat-mm1-arduino-ide-1d1954) guide to ensure that you have the latest firmware.

> Do protocols like PPM or SBUS work on Robo HAT?

This is a software limitation.  I am yet to test and see these protocols working because we have focused on CircuitPython.  There are already Arduino libraries available that perform these.  There are no hardware limitations of Robo HAT MM1 to see these features work (one day).

> Why can I not see the CIRCUITPY drive under linux?

CircuitPython has a limitation where it sometimes does not mount under a linux filesystem.
See this [Adafruit Learn Guide](https://learn.adafruit.com/welcome-to-circuitpython/the-circuitpy-drive#renaming-circuitpy-on-linux-6-10) for more information.

# Hardware FAQ
> What is the Processor Speed of the Robo HAT MM1?

The Robo HAT MM1 has a SAMD51J19 on-board.  This processor is clocked at 120 MHz.  [More information here](https://www.microchip.com/wwwproducts/en/ATSAMD51J19A).

> What sensors are on-board the Robo HAT MM1?

The Robo HAT MM1 has two on-board sensors.
The IMU is a MPU9250 which includes an accelerometer, gyroscope and magnetometer.
The Current Sensor is a INA219 with the ability to measure a wide range of current sensing, voltage and power features.
If you want to use sensors like a GPS or barometer, you need to add these using the expansion ports.

> Can you use USB Serial with Robo HAT MM1 on Raspberry Pi?

Yes.  It will show up as a serial tty port.  Be careful to not confuse this with the Hardware Serial port on the Raspberry Pi.