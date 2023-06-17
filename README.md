# VR Ambilight
## Introduction

The VR Ambilight is a project that enhances the immersive experience of virtual reality (VR) by creating dynamic ambient lighting that synchronizes with the on-screen content. This guide will walk you through the process of building your own VR Ambilight system.
Features

    Dynamic ambient lighting synchronized with VR content.
    Adjustable color and brightness settings.
    Support for Valve Index.

## Materials

Before you begin, make sure you have the following materials:

    Arduino Nano.
    WS2812b Individually Addressable led Strip 144Pixels/m.
    Soldering equipment.
    Computer with Arduino IDE installed.
    Defusion sheet (recomended)

## Wiring Diagram
Follow this wiring diagram to connect the components correctly:

Ensure that the LED strip you are using operates at a voltage of **5V**.
![Wiring.jpg](https://github.com/Statonwest/VR_Ambilight/blob/4eb2b8151044abd69c027892ab7f479d03757838/Wiring.jpg)
Typically, for larger LED strip setups, you would require a separate power supply unit (PSU). However, in this case, the number of LEDs is small enough to be powered directly from the Arduino board itself.

## Arduino Setup

To set up the software, follow these steps:

Download and install the Arduino IDE from the official Arduino website (https://www.arduino.cc/en/software).

Install the FastLED libruary.

Clone or download the project files from the GitHub repository:
[VR_Ambient_light.ino](https://github.com/Statonwest/VR_Ambilight/blob/4264298c710a5be8f2513a294410e2fc3ae0b779/VR_Ambient_light.ino)

The original repository can be found here.
[adalight.ino](https://github.com/hyperion-project/hyperion.ng/blob/master/assets/firmware/arduino/adalight/adalight.ino)

## Building the VR Ambilight

Follow these steps to assemble the VR Ambilight system:

Cut two LED strips with 9 LEDs each.

Solder the two indoviual strips together with lenghs of wire long enough to rout around to each side of the face gasket.

Connect the data line of the LED strip to the Arduino. Connect the DIN (data input) pin of the LED strip to any digital pin on the Arduino (e.g., pin 6).

Connect the GND and the 5V.

Double-check all the connections and make sure they are secure.

Plug in the USB, and the LED strip should light up.

Position the LED strip around the perimeter of your face gasket, ensuring an even distribution of light.

Cut out the defusion sheet accroding to the template ##[ADD Diffusion Template HERE]##. The deffusion sheet I used was from an old display.
But parchment paper can work in a pinch.

## Hyperion

Setup Hyperion [Hyperion](https://docs.hyperion-project.org/en/user/Installation.html#fedora)
##add more here##

Test the VR Ambilight by running a VR application or video content.
##Add more here##

Adjust the color and brightness settings according to your preference in Hyperion.
##add more here##
