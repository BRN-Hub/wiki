---
title: 2. Getting Started
linkTitle: 2. Getting Started
---
# Getting Started with Sony Spresense

## Overview
This tutorial will guide you through the initial setup of the Sony Spresense board, including installing the necessary software and configuring the development environment.

## Prerequisites
- Sony Spresense board
- USB cable
- Computer with internet access

## Objectives
By the end of this tutorial, you will:
1. Unbox and set up your Sony Spresense board.
2. Install the required software and drivers.
3. Set up the development environment.

## 1. Unboxing and Setting Up the Board

### Unboxing
1. Carefully unbox your Sony Spresense board.
2. Inspect the board for any physical damage.

### Connecting the Board
1. Connect the Sony Spresense board to your computer using a USB cable.
2. Ensure the connection is secure and the board is powered on.

## 2. Installing Required Software

### Installing Arduino IDE
1. Download the Arduino IDE from the [official website](https://www.arduino.cc/en/software).
2. Install the Arduino IDE following the instructions for your operating system.

### Adding Sony Spresense Board to Arduino IDE
1. Open the Arduino IDE.
2. Go to **File > Preferences**.
3. In the "Additional Board Manager URLs" field, add the following URL:
```bash
https://developer.sony.com/develop/spresense/docs/arduino_set_up_en.html
```
4. Click **OK** to save the settings.

### Installing Spresense Board Package
1. Go to **Tools > Board > Boards Manager**.
2. Search for "Spresense" in the Boards Manager.
3. Click **Install** next to the "Spresense by Sony" entry.

## 3. Setting Up the Development Environment

### Configuring the Board
1. Connect your Sony Spresense board to your computer using a USB cable.
2. Open the Arduino IDE.
3. Go to **Tools > Board** and select **Spresense**.
4. Go to **Tools > Port** and select the appropriate COM port for your Spresense board.

### Installing Drivers
1. If prompted, install any necessary drivers for the Sony Spresense board.
2. Follow the on-screen instructions to complete the driver installation.

## 4. Uploading Your First Sketch

### Blinking an LED
1. Open the Arduino IDE.
2. Go to **File > Examples > 01.Basics > Blink**.
3. Verify the sketch by clicking the checkmark button.
4. Upload the sketch to your board by clicking the right arrow button.

### Verifying the Blink
1. After the sketch is uploaded, you should see the onboard LED start to blink.
2. If the LED blinks, your setup is successful.

## Troubleshooting
- **Board not recognized**: Ensure the USB cable is properly connected and try a different USB port.
- **Upload error**: Check the selected board and port in the Arduino IDE.

## Conclusion
You've successfully set up your Sony Spresense board, installed the necessary software, and uploaded your first sketch. You are now ready to start developing applications with the Sony Spresense board.

## Next Steps
Proceed to the next tutorial, **Blinking an LED**, to learn more about basic GPIO operations and writing your first custom sketch.
