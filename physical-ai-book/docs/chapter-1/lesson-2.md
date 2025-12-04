---
id: chapter-1-lesson-2
sidebar_label: "Lesson 2: Hardware Components and Platforms"
sidebar_position: 2
---

# Lesson 2: Hardware Components and Platforms

This lesson explores the essential hardware components used in Physical AI systems, such as microcontrollers, single-board computers, various sensors (e.g., cameras, lidar, IMUs), and actuators (e.g., motors, servos). It will also introduce common development platforms like Arduino, Raspberry Pi, and ROS.

## Hands-on Exercise: Blinking an LED with Arduino

This exercise will guide you through setting up an Arduino board and making an LED blink, a classic "Hello World" for embedded systems.

**Objectives:**
1. Connect an LED to your Arduino board.
2. Upload a simple program to make the LED blink.
3. Understand the basic structure of an Arduino sketch.

**Required Setup:**
*   Arduino Uno board (or compatible)
*   USB cable
*   Breadboard
*   LED
*   220-ohm resistor
*   Jumper wires
*   Arduino IDE installed on your computer.

**Instructions:**
1.  **Hardware Connection:**
    *   Connect the long leg (anode) of the LED to a digital pin on the Arduino (e.g., Pin 13) through the 220-ohm resistor.
    *   Connect the short leg (cathode) of the LED to the GND pin on the Arduino.
2.  **Arduino Sketch:**
    *   Open the Arduino IDE.
    *   Copy and paste the following code into a new sketch:

    ```cpp title="blink.ino"
    void setup() {
      pinMode(13, OUTPUT);
    }

    void loop() {
      digitalWrite(13, HIGH);   // turn the LED on (HIGH is the voltage level)
      delay(1000);              // wait for a second
      digitalWrite(13, LOW);    // turn the LED off by making the voltage LOW
      delay(1000);              // wait for a second
    }
    ```

3.  **Upload to Arduino:**
    *   Select your Arduino board from `Tools > Board`.
    *   Select the correct port from `Tools > Port`.
    *   Click the "Upload" button (right arrow icon) in the Arduino IDE.

**Expected Outcome:**
Your LED should start blinking with a one-second delay between ON and OFF states.