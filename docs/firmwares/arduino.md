# Arduino

* [Overview](#overview)
* [Install Board Files](#install-robo-hat-mm1)
* [Flash CircuitPython](#flash)
* [Custom Boards](#custom-boards)

##Overview

Arduino IDE is a very popular C++ based programming interface for the Arduino Platform.  It also supports custom boards and is used by many makers around the world.


##Install Robo HAT MM1

**STEP 1**

Copy and paste the following URL into the File > Preferences > "Additional Boards Manager URLS" textbox.

```HTTP
https://raw.githubusercontent.com/robotics-masters/mm1-hat-arduino/master/custom_board/package_robohat_index.json
```

**STEP 2**

You need to install the Robo HAT Board Library to be able to push sketches to the Robo HAT MM1.  Make sure to also install the Arduino SAMD Library at the same time.

Go to Tools > "Board:" > "Boards Manager".  Search for "Robo HAT" and click the "Install" button that appears next to the description.

The latest version is 0.0.26

Go to Tools > "Board:" > "Boards Manager".  Search for "SAMD".  Look for "Arduino SAMD Boards (32-bits ARM Cortex M0+)" and click the "Install" button that appears next to the description.  

The latest version is 1.8.3

**STEP 3**

Select the Robo HAT MM1 as you would a normal Arduino Board from the "boards" menu.  Then compile a sketch (blink is a good example) to ensure everything is working as expected.


##Custom Boards

Important: Not recommend for beginners.

Please head to our [arduino github repo](https://github.com/robotics-masters/mm1-hat-arduino) for more information

There is also a guide - [Arduino IDE: Creating Custom Boards](https://www.hackster.io/wallarug/arduino-ide-creating-custom-boards-89f7a6) - that you can follow and use if you want to build your own custom board or firmware.