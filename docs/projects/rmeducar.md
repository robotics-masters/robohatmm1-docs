# Robotics Masters EduCar

The Robotics Masters EDUCar was part of the Crowd Supply Campaign in 2019.  It provided a sensor kit that could be programed by kids.  It uses the Robo HAT MM1 has the core controller for a varienty of educational programming challenges.

This guide will help you set up the car and get you started.

## Parts Included

### Bluetooth Serial Adaptor

The UART to Bluetooth Bridge Adaptor allows you to use your phone to control the car.  The data rate is locked to 9600 baud.  There are no drivers or additional software packages required for this adaptor to work.

| Robo HAT | Bluetooth |
|----------|-----------|
| GPS_TX   | RXD |
| GPS_RX   | TXD |
| 5V | VCC |
| GND | GND |

Example - CircuitPython
```
import board
import busio

# set up the bluetooth serial to uart device
bluetooth = busio.UART(board.TX, board.RX, baudrate=9600)

# read one byte
bluetooth.read(1)

# write bytes
bluetooth.write(b'Hello, World!')
```

### Pressure Sensor

BMP280 is a popular pressure sensor module that supports both I2C and SPI operation.  It sends back information to your program about the environment.  It requires the [Adafruit BMP280 CircuitPython](https://github.com/adafruit/Adafruit_CircuitPython_BMP280) driver to work.

| Robo HAT | Pressure Sensor |
|----------|-----------------|
| 3V3   | VIN |
| GND   | GND |
| SCL   | SCK |
| SDA   | SDI |

NOTE:  This sensor is 3V and the Robo HAT MM1 only provides 5V outputs.  You may require a level shifter.

Example - CircuitPython
```
import board
import digitalio
import busio
import time
from adafruit_bmp280 import adafruit_bmp280

# Create library object using our Bus I2C port
i2c = busio.I2C(board.SCL, board.SDA)
bmp280 = adafruit_bmp280.Adafruit_BMP280_I2C(i2c)

# OR create library object using our Bus SPI port
#spi = busio.SPI(board.SCK, board.MOSI, board.MISO)
#bmp_cs = digitalio.DigitalInOut(board.D10)
#bmp280 = adafruit_bmp280.Adafruit_BMP280_SPI(spi, bmp_cs)

# change this to match the location's pressure (hPa) at sea level
bmp280.seaLevelhPa = 1013.25

while True:
    print("\nTemperature: %0.1f C" % bmp280.temperature)
    print("Pressure: %0.1f hPa" % bmp280.pressure)
    print("Altitude = %0.2f meters" % bmp280.altitude)
    time.sleep(2)
```

### Infrared Line Finder

This sensor allows the car to follow lines.  It outputs digital signals that can be used to tell the car to change direction to stay on the line.  It includes a 74HC14D shift register for keeping track of the state of all the infrared sensors.



### Optical Rotary Encoder

MD-1358



### Ultrasonic Distance Sensor

The commonly used HC-SR04 Distance Sensor is used for measuring distances between 2 centimeters up to 4 meters.   It sends out a 'sound pulse' and 'listens' for a response.   


### Other Components

There are a number of other parts included

- Motor Driver
- Light Dependant Resistor
- Resistors
- Battery Holder
- Motors
- Solderless Breadboard



