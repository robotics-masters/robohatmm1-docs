## Arduino

* [Introduction](#introduction)
    - [Setup](#setup)
* [Examples](#examples)
    - [Blink - example](#blink-example)
#Introduction

## Setup

###Additional Boards Manager URLS
---
**STEP 1:**
Open preference from your Arduino IDE find the "Additional Boards Manager URLS" section add following URL into the box:

```
https://raw.githubusercontent.com/peterpanstechland/mm1-hat-arduino/peter/custom_board/package_robohat_index.json
```

**STEP 2:**
Find the Boards Manager from tools>Board:>Boards Manager, search for "Robo HAT", select current version V0.0.24 and click install

# Examples

## Blink - example

This example blinks the on board LED forever.

```
void setup() {
  // initialize digital pin LED_BUILTIN as an output.
  pinMode(LED_BUILTIN, OUTPUT);
}

// the loop function runs over and over again forever
void loop() {
  digitalWrite(LED_BUILTIN, HIGH);   // turn the LED on (HIGH is the voltage level)
  delay(1000);                       // wait for a second
  digitalWrite(LED_BUILTIN, LOW);    // turn the LED off by making the voltage LOW
  delay(1000);                       // wait for a second
}

```
Head to [Arduino API](/guide/Arduino%20API/Arduino_API/) for more information about the pins and library.
