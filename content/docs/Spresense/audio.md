---
title: 5. Audio Processing
linkTitle: 5. Audio Processing
---
# Audio Processing with Spresense

## Overview
This tutorial will guide you through the audio processing capabilities of the Sony Spresense board. You will learn how to record and playback audio, and implement basic audio processing algorithms.

## Prerequisites
- Sony Spresense board
- USB cable
- Computer with Arduino IDE installed
- Microphone for audio input
- Speakers or headphones for audio output

## Objectives
By the end of this tutorial, you will:
1. Connect a microphone and speaker to the Sony Spresense board.
2. Record audio and save it to the board.
3. Playback the recorded audio.
4. Implement basic audio processing algorithms.

## 1. Setting Up the Audio Hardware

### Connecting the Microphone
1. Connect the microphone to the appropriate input pins on the Spresense board. 
   - For example, connect the microphone output to the AIN (Analog IN) pin, power to 3.3V, and ground to GND.

### Connecting the Speaker
1. Connect the speaker or headphones to the appropriate output pins on the Spresense board.
   - For example, connect the speaker to the AUDIO_OUT pins.

## 2. Recording Audio

### Writing the Sketch for Audio Recording
1. Open the Arduino IDE.
2. Create a new sketch by going to **File > New**.
3. Enter the following code to record audio:

```cpp
#include <Audio.h>

// Define the audio input and output pins
const int micPin = AIN; // Change to the correct pin for your microphone
const int spkPin = AUDIO_OUT; // Change to the correct pin for your speaker

AudioClass audio;

void setup() {
  // Initialize serial communication
  Serial.begin(9600);

  // Initialize the audio library
  if (!audio.begin()) {
    Serial.println("Failed to initialize audio");
    while (1);
  }

  // Configure the audio input and output
  audio.inputSelect(AS_MIC);
  audio.outputSelect(AS_SPK);
}

void loop() {
  // Start recording audio
  if (audio.startRecord("/audio.wav")) {
    Serial.println("Recording started");

    // Record for 10 seconds
    delay(10000);

    // Stop recording
    audio.stopRecord();
    Serial.println("Recording stopped");
  } else {
    Serial.println("Failed to start recording");
  }

  // Wait before next recording
  delay(10000);
}
```
#### Uploading the Sketch
1. Connect your Sony Spresense board to your computer using a USB cable.
2. Select the correct board and port from Tools > Board and Tools > Port.
3. Click the Upload button (right arrow) in the Arduino IDE.
4. Wait for the sketch to compile and upload.
#### Verifying the Recording
1. The audio recording will be saved as "audio.wav" on the Spresense board.
2. Check the serial monitor for confirmation messages.
### 3. Playing Back Audio
#### Writing the Sketch for Audio Playback
1. Open the Arduino IDE.
2. Create a new sketch by going to File > New.
3. Enter the following code to playback audio:
```cpp
#include <Audio.h>

AudioClass audio;

void setup() {
  // Initialize serial communication
  Serial.begin(9600);

  // Initialize the audio library
  if (!audio.begin()) {
    Serial.println("Failed to initialize audio");
    while (1);
  }

  // Play the recorded audio file
  if (audio.startPlay("/audio.wav")) {
    Serial.println("Playback started");

    // Wait for the playback to finish
    while (audio.isPlaying()) {
      delay(100);
    }

    Serial.println("Playback finished");
  } else {
    Serial.println("Failed to start playback");
  }
}

void loop() {
  // Nothing to do here
}

```
#### Uploading the Sketch
1. Connect your Sony Spresense board to your computer using a USB cable.
2. Select the correct board and port from Tools > Board and Tools > Port.
3. Click the Upload button (right arrow) in the Arduino IDE.
4. Wait for the sketch to compile and upload.
#### Verifying the Playback
1. The recorded audio will play back through the connected speaker.
2. Check the serial monitor for confirmation messages.
### 4. Implementing Basic Audio Processing
#### Example: Audio Amplification
1. Modify the recording sketch to include a basic audio amplification algorithm:
```cpp
#include <Audio.h>

// Define the audio input and output pins
const int micPin = AIN; // Change to the correct pin for your microphone
const int spkPin = AUDIO_OUT; // Change to the correct pin for your speaker

AudioClass audio;

void setup() {
  // Initialize serial communication
  Serial.begin(9600);

  // Initialize the audio library
  if (!audio.begin()) {
    Serial.println("Failed to initialize audio");
    while (1);
  }

  // Configure the audio input and output
  audio.inputSelect(AS_MIC);
  audio.outputSelect(AS_SPK);
}

void loop() {
  // Start recording audio
  if (audio.startRecord("/audio.wav")) {
    Serial.println("Recording started");

    // Record for 10 seconds with amplification
    for (int i = 0; i < 1000; i++) {
      int16_t sample = audio.readSample();
      sample = min(max(sample * 2, -32768), 32767); // Amplify the sample
      audio.writeSample(sample);
      delay(10);
    }

    // Stop recording
    audio.stopRecord();
    Serial.println("Recording stopped");
  } else {
    Serial.println("Failed to start recording");
  }

  // Wait before next recording
  delay(10000);
}
```
#### Uploading and Testing
1. Follow the previous steps to upload and verify the modified sketch.
2. The recorded audio should now be amplified during playback.
### Troubleshooting
- No audio recorded: Ensure the microphone is connected correctly and check the input pin configuration.
- No audio playback: Ensure the speaker is connected correctly and check the output pin configuration.
### Conclusion
You've successfully recorded and played back audio using the Sony Spresense board, and implemented a basic audio processing algorithm. This opens up many possibilities for developing advanced audio applications.
### Next Steps
Proceed to the next tutorial, Camera Integration, to learn how to connect a camera module and capture and process images with the Sony Spresense board.