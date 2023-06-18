# VR Ambilight (WORK IN PROGRESS)

## Introduction

The VR Ambilight is a project that enhances the immersive experience of virtual reality (VR) by creating dynamic ambient lighting that synchronizes with the on-screen content. This guide will walk you through the process of building your own VR Ambilight system.


## Features

Dynamic ambient lighting synchronized with VR content.

Adjustable color and brightness settings.

Support for Valve Index.


## Materials

Arduino Nano

WS2812b Individually Addressable led Strip 144Pixels/m

Soldering equipment

Defusion sheet (recomended)


## Wiring Diagram

Ensure that the LED strip you are using operates at a voltage of **5V**.
![Wiring.jpg](https://github.com/Statonwest/VR_Ambilight/blob/01b49622970872a12339bb632445c691a10369d1/Wiring%20Digram.jpg)
Typically, for larger LED strip setups, it would require a separate power supply unit (PSU). However, in this case, the number of LEDs is small enough to be powered directly from the Arduino board itself.


## Arduino Setup

Download and install the Arduino IDE from the official Arduino website (https://www.arduino.cc/en/software).

Install the [FastLED libruary](https://github.com/FastLED/FastLED/releases).

Clone or download the project files from the GitHub repository:
[VR_Ambient_light.ino](https://github.com/Statonwest/VR_Ambilight/blob/4264298c710a5be8f2513a294410e2fc3ae0b779/VR_Ambient_light.ino)

The original repository can be found here.
[adalight.ino](https://github.com/hyperion-project/hyperion.ng/blob/master/assets/firmware/arduino/adalight/adalight.ino)


## Building the VR Ambilight

Cut two LED strips, each with 9 LEDs.

Solder the two individual strips together using wire lengths that are long enough to route around to each side of the face gasket.

Connect the data line, GND, and the 5V of the LED strip to the Arduino. Connect the DIN (data input) pin of the LED strip to digital pin 6 on the Arduino.

Double-check all the connections to ensure they are secure.

Position the LED strip on the sides of your face gasket, ensuring an even distribution of light. Refer to the image below for reference:

[PIC of face gasket wired]

Choose a wire routing method that works best for you. I opted to route the wires from underneath and over the top of the gasket, but there are other possible arrangements. Adjust your Prismatik settings accordingly to match your wire placement. 

Mount the Arduino Nano securely at the front of the index. Connect the Arduino Nano to the USB port for power and data transmission.

[PIC of arduino placement]


## Diffusion Sheet

Cut out the diffusion sheet according to the provided template Diffusion Template. You can use an old display's diffusion sheet or parchment paper as a substitute.

Use two polarizing layers and place the top diffusion sheet on top of them for optimal results.

[PIC of diffusion sheets]


## Prismatik

[Prismatik](https://github.com/psieg/Lightpack/releases) 
is the software we will utilize to capture the screen content and send the data to the Arduino.

Launch Prismatik and go through the initial setup process. Follow the on-screen instructions to configure the display settings.

Configure the output settings to match your Arduino connection. Select the correct COM port corresponding to the Arduino Nano.

Adjust any additional settings in Prismatik according to your preferences, such as color correction, brightness, and capture area.
[PIC of Prismatik settings]
