---
title: Working with Sensors
linkTitle: Working with Sensors
---
# Working with Sensors

## Overview
This tutorial will guide you through connecting and interfacing various sensors with the Sony Spresense board. You will learn how to read sensor data and display it on the serial monitor.

## Prerequisites
- Sony Spresense board
- USB cable
- Computer with Arduino IDE installed
- Sensor (e.g., temperature sensor, light sensor, etc.)
- Breadboard and jumper wires (optional)

## Objectives
By the end of this tutorial, you will:
1. Connect a sensor to the Sony Spresense board.
2. Write a sketch to read data from the sensor.
3. Display the sensor data on the serial monitor.

## 1. Connecting the Sensor

### Choosing a Sensor
For this tutorial, we'll use a simple analog temperature sensor (e.g., TMP36). You can use any other analog or digital sensor following a similar approach.

### Connecting the Sensor
1. Place the TMP36 sensor on the breadboard.
2. Connect the middle pin of the TMP36 to an analog input pin on the Spresense board (e.g., A0).
3. Connect one of the outer pins to GND and the other outer pin to 3.3V on the Spresense board.

## 2. Writing the Sketch

### Reading Sensor Data
1. Open the Arduino IDE.
2. Create a new sketch by going to **File > New**.
3. Enter the following code to read and display the temperature sensor data:

```cpp
// Define the analog pin for the temperature sensor
const int sensorPin = A0;

void setup() {
  // Start the serial communication
  Serial.begin(9600);
}

void loop() {
  // Read the analog value from the sensor
  int sensorValue = analogRead(sensorPin);
  
  // Convert the analog value to voltage
  float voltage = sensorValue * (3.3 / 1023.0);
  
  // Convert the voltage to temperature in Celsius
  float temperatureC = (voltage - 0.5) * 100.0;
  
  // Print the temperature value to the serial monitor
  Serial.print("Temperature: ");
  Serial.print(temperatureC);
  Serial.println(" C");
  
  // Wait for a second before taking another reading
  delay(1000);
}
```
#### Uploading the Sketch
1. Connect your Sony Spresense board to your computer using a USB cable.
2. Select the correct board and port from Tools > Board and Tools > Port.
3. Click the Upload button (right arrow) in the Arduino IDE.
4. Wait for the sketch to compile and upload.
#### Viewing Sensor Data
1. Open the serial monitor by going to Tools > Serial Monitor in the Arduino IDE.
2. Set the baud rate to 9600.
3. You should see the temperature readings displayed in the serial monitor.
### 3. Using Other Sensors
You can use a similar approach to connect and read data from other sensors. Here are some examples:
#### Light Sensor (e.g., LDR)
1. Connect the LDR sensor to an analog input pin (e.g., A1).
2. Use a similar sketch to read the analog value from the light sensor and display it on the serial monitor.
#### Digital Sensor (e.g., DHT11)
1. Connect the DHT11 sensor to a digital input pin (e.g., D2).
2. Use a library like "DHT" to read temperature and humidity data from the sensor and display it on the serial monitor.
### Troubleshooting
- No data on serial monitor: Ensure the correct baud rate is set and the sensor connections are secure.
- Incorrect sensor readings: Check the sensor specifications and ensure correct wiring and code logic.
### Conclusion
You've successfully connected a sensor to the Sony Spresense board, read data from the sensor, and displayed it on the serial monitor. This knowledge allows you to integrate various sensors into your projects.
### Next Steps
Proceed to the next tutorial, Audio Processing with Spresense, to learn about the audio capabilities of the Sony Spresense board and how to record and process audio.