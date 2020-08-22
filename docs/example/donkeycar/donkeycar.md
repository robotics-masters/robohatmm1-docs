# Robotics Masters Donkey&reg; Car build

---
Hardware Parts
---

### Raspberry Pi Build

| Modules | Spec | Purchase link |
|---|---|---|
| **Raspberry Pi**| model 3B or above | [3b]() [3b+]() 4b [[1G](), [2G](), [4G]()] |
| **Camera module** | recommend 5 Megapixel wide angle lens | [5 Megapixel fisheye]()
| **SD Card** | recommend 16Gb or above | [SD card]()  |
| **RoboHAT MM1 Pi HAT** | add-on controller board| [Pre-order]() |
| **RC Car Chassis**  | recommend HSP RC Car 1:16 4WD High Speed Off-road Monster Truck | [HSP Monster Truck]()  |
| **RC Controller & Receiver**| recommend to use the RC controller & Receiver come with the Car |  |
| **Roll Cage** | 3D printed Parts can be purchased from our online shop | [3D print STL file]() or <br> [Buy online]()  |
| **Battery**  | 11.1V 3S Li-Po with 7000mAH - 10000mAH 25C  | [Battery]()  |

### Jetson Nano Build

| Modules | Spec | Purchase link |
|---|---|---|
| **Jetson Nano** | Nvidia Jetson Nano GPU Development Board | [Jetson Nano]() |
| **Camera module** | recommend Pi Camera V2.0 camera module with Sony IMX219 | [Pi camera V2.0]()|
| **SD Card** | recommend 16Gb or above| [SD card]()  |
| **RoboHAT MM1 Pi HAT** | add-on controller board | [Pre-order]() |
| **RC Car Chassis** | recommend HSP RC Car 1:16 4WD High Speed Off-road Monster Truck | [HSP Monster Truck]()  |
| **RC Controller & Receiver** | recommend to use the RC controller & Receiver come with the Car |  |
| **Roll Cage** | 3D printed Parts can be purchased from our online shop  | [3D print STL file]() or <br> [Buy online]()  |
| **Battery**  | 11.1V 3S Li-Po with 7000mAH - 10000mAH 25C  | [Battery]() |

---

Software Setup
---

### Raspberry Pi
* Setup [RaspberryPi](robot_sbc/setup_raspberry_pi.md)
![donkey](/assets/logos/rpi_logo.png)

### Jetson Nano
* Setup [Jetson Nano](robot_sbc/setup_jetson_nano.md)
![donkey](/assets/logos/nvidia_logo.png)

---

## Robo HAT MM1 Setup

Set ```HAVE_ROBOHAT = True``` in your __myconfig.py__ if you have a Robo HAT MM1 board.   Also set the following variables according to your setup.  Most people will be using the below values, however, if you are using a Jetson Nano, please set `MM1_SERIAL_PORT = '/dev/ttyTHS1'`

```python3
#ROBOHAT MM1
HAVE_ROBOHAT = False            # set to true when using the Robo HAT MM1 from Robotics Masters.  This will change to RC Control.
MM1_STEERING_MID = 1500         # Adjust this value if your car cannot run in a straight line
MM1_MAX_FORWARD = 2000          # Max throttle to go fowrward. The bigger the faster
MM1_STOPPED_PWM = 1500
MM1_MAX_REVERSE = 1000          # Max throttle to go reverse. The smaller the faster
MM1_SHOW_STEERING_VALUE = False
# Serial port 
# -- Default Pi: '/dev/ttyS0'
# -- Jetson Nano: '/dev/ttyTHS1'
# -- Google coral: '/dev/ttymxc0'
# -- Windows: 'COM3', Arduino: '/dev/ttyACM0'
# -- MacOS/Linux:please use 'ls /dev/tty.*' to find the correct serial port for mm1 
#  eg.'/dev/tty.usbmodemXXXXXX' and replace the port accordingly
MM1_SERIAL_PORT = '/dev/ttyS0'  # Serial Port for reading and sending MM1 data (raspberry pi default)

# adjust controller type as Robohat MM1
CONTROLLER_TYPE='MM1'

# adjust drive train for web interface
DRIVE_TRAIN_TYPE = 'MM1'
```

The Robo HAT MM1 uses a RC Controller and CircuitPython script to drive the car during training. You must put the CircuitPython script onto the Robo HAT MM1 with your computer before you can continue.

1.  Download the CircuitPython Donkey Car Driver for Robo HAT MM1 to your computer from [here](https://github.com/autorope/donkeycar/blob/dev/donkeycar/contrib/robohat/code.py)
2.  Connect the MicroUSB connector on the Robo HAT MM1 to your computer's USB port.
3.  A __CIRCUITPY__ device should appear on the computer as a USB Storage Device
4.  Copy the file downloaded in Step 1 to the __CIRCUITPY__ USB Storage Device.  Rename the file __code.py__.
5.  Unplug USB Cable from the Robo HAT MM1 and place on top of the Raspberry Pi, as you would any HAT.


You may need to enable the hardware serial port on your Raspberry Pi.  On your Raspberry Pi...

1.  Run the command ```sudo raspi-config```
2.  Navigate to the __5 - Interfaceing options__ section.
3.  Navigate to the __P6 - Serial__ section.
4.  When asked: __Would you like a login shell to be accessible over serial?__  NO
5.  When asked: __Would you like the serial port hardware to be enabled?__ YES
6.  Close raspi-config
7.  Restart


If you would like additional hardware or software support with Robo HAT MM1, there are a few guides published on Hackster.io.  They are listed below.

[Raspberry Pi + Robo HAT MM1](https://www.hackster.io/wallarug/autonomous-cars-with-robo-hat-mm1-8d0e65)

[Jetson Nano + Robo HAT MM1](https://www.hackster.io/wallarug/donkey-car-with-jetson-nano-robo-hat-mm1-e53e21)

[Simulator + Robo HAT MM1](https://www.hackster.io/wallarug/donkey-car-simulator-with-real-rc-controller-628e77)
