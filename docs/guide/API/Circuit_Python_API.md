## Circuit Python API


#Introduction

## The lib folder

Inside your CIRCUITPY drive there will be a folder called `lib`.  This folder will contain any libraries you want to use with CircuitPython.  It is similar to the Python site-packages folder.

To add a new library you just download the corresponding python file (usually `.mpy`) and paste it into the `lib` folder.

CircuitPython supports many common libraries and devices.  You can find them all on their [GitHub](https://github.com/adafruit) page or alternatively download the [CircuitPython Bundle](https://github.com/adafruit/Adafruit_CircuitPython_Bundle/releases) which contains many of the common hardware you find.


## The code.py file

All the code you want to run on a CircuitPython board must be placed into the `code.py` file.  CircuitPython runs the `code.py` file when the board restarts.

You are able to import other Python files but remember that `code.py` is the file that gets run similar to how you would do it on the command line.

```
python3 code.py
```

# Examples

## Blink - example

This example blinks the on board LED forever.

```
import board
import digitalio
import time

led = digitalio.DigitalInOut(board.LED)
led.direction = digitalio.Direction.OUTPUT

while True:
    led.value = True
    time.sleep(0.5)
    led.value = False
    time.sleep(0.5)

```


## Servos - Example

This example moves the servo motor attached to SERVO1 pin in a pan motion.  It will continue doing this over and over until you stop it.

For this example you are required to download and copy the adafruit_motor library into the lib/ folder located on the RoboHAT MM1.  It can be downloaded from [here](https://github.com/adafruit/Adafruit_CircuitPython_Motor/releases).


```
import board
import digitalio
import time
import pulseio
from adafruit_motor import servo

# set up LED
led = digitalio.DigitalInOut(board.LED)
led.direction = digitalio.Direction.OUTPUT


# set up SERVO1
pwm = pulseio.PWMOut(board.SERVO1, duty_cycle=2 ** 15, frequency=60)
my_servo = servo.Servo(pwm)


while True:
    led.value = True
    time.sleep(0.5)
    for angle in range(0, 180, 5):
        my_servo.angle = angle
        time.sleep(0.05)
    for angle in range(180, 0, -5):
        my_servo.angle = angle
        time.sleep(0.05)
    led.value = False
    time.sleep(0.5)

```


Make sure you check out the [Adafruit Learn Guide](https://learn.adafruit.com/welcome-to-circuitpython/overview) to get further information about CircuitPython and how to use all the libraries.




