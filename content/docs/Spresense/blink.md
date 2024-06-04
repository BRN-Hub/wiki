---
title: Blinking an LED
linkTitle: Blinking an LED
---
# Blinking an LED

## Overview
This tutorial will guide you through creating a basic LED blinking application using the Sony Spresense board. This is a fundamental exercise that helps you get familiar with GPIO (General-Purpose Input/Output) operations.

## Prerequisites
- Sony Spresense board
- USB cable
- Computer with Arduino IDE installed (covered in the previous tutorial)
- An external LED and a 220-ohm resistor (optional for external LED setup)

## Objectives
By the end of this tutorial, you will:
1. Understand basic GPIO operations.
2. Write and upload a sketch to blink the onboard LED.
3. Connect and control an external LED.

## 1. Blinking the Onboard LED

### Understanding GPIO
The Sony Spresense board has several GPIO pins that can be used to control external devices like LEDs, sensors, and more. The onboard LED is connected to one of these GPIO pins.

### Writing the Sketch
1. Open the Arduino IDE.
2. Go to **File > New** to create a new sketch.
3. Enter the following code to blink the onboard LED:

```cpp
// Define the LED pin
const int ledPin = 13; // Onboard LED is connected to pin 13

void setup() {
  // Initialize the digital pin as an output
  pinMode(ledPin, OUTPUT);
}

void loop() {
  // Turn the LED on (HIGH is the voltage level)
  digitalWrite(ledPin, HIGH);
  // Wait for a second
  delay(1000);
  // Turn the LED off by making the voltage LOW
  digitalWrite(ledPin, LOW);
  // Wait for a second
  delay(1000);
}
```
#### Uploading the Sketch
1. Connect your Sony Spresense board to your computer using a USB cable.
2. Select the correct board and port from Tools > Board and Tools > Port.
3. Click the Upload button (right arrow) in the Arduino IDE.
4. Wait for the sketch to compile and upload.
#### Verifying the Blink
1. Once uploaded, you should see the onboard LED start to blink with a 1-second interval.
2. If the LED blinks, the sketch is working correctly.
### 2. Controlling an External LED (Optional)
#### Connecting the LED
1. Connect the long leg (anode) of the LED to a 220-ohm resistor.
2. Connect the other end of the resistor to pin 7 on the Spresense board.
3. Connect the short leg (cathode) of the LED to one of the GND (ground) pins on the Spresense board.
#### Modifying the Sketch
1. Open the Arduino IDE.
2. Modify the sketch to control the external LED:
```cpp
Copy code
// Define the LED pin
const int ledPin = 7; // External LED is connected to pin 7

void setup() {
  // Initialize the digital pin as an output
  pinMode(ledPin, OUTPUT);
}

void loop() {
  // Turn the LED on (HIGH is the voltage level)
  digitalWrite(ledPin, HIGH);
  // Wait for a second
  delay(1000);
  // Turn the LED off by making the voltage LOW
  digitalWrite(ledPin, LOW);
  // Wait for a second
  delay(1000);
}
```
#### Uploading and Testing the Sketch
1. Connect your Sony Spresense board to your computer using a USB cable.
2. Select the correct board and port from Tools > Board and Tools > Port.
3. Click the Upload button (right arrow) in the Arduino IDE.
4. Wait for the sketch to compile and upload.
5. Verify that the external LED blinks with a 1-second interval.
### Troubleshooting
- LED not blinking: Check the connections and ensure the LED and resistor are properly connected.
- Upload error: Ensure the correct board and port are selected in the Arduino IDE.
### Conclusion
You've successfully written and uploaded a sketch to blink both the onboard and an external LED using the Sony Spresense board. This fundamental exercise helps you understand basic GPIO operations and prepares you for more advanced projects.
### Next Steps
Proceed to the next tutorial, Working with Sensors, to learn how to connect and read data from various sensors using the Sony Spresense board.
