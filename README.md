## Introduction

The VR Ambilight is a project that enhances the immersive experience of virtual reality (VR) by creating dynamic ambient lighting that synchronizes with the on-screen content. This guide will walk you through the process of building your own VR Ambilight system.

![V1](https://github.com/Statonwest/VR_Ambilight/blob/902ad8909392518a5abd3fa233c36712d24bf2b6/Photos/V1.gif)

It performs exceptionally well for games that feature vibrant colors, like Beat Saber.

## Features

Dynamic ambient lighting synchronized with VR content.

Adjustable color and brightness settings.

Support for Valve Index.


## Materials

Arduino Nano

WS2812b Individually Addressable led Strip 144Pixels/m

Soldering equipment

Defusion sheet

---
Alternative 3D printed diffuser:

Clear filament

Paper

Glue


## Wiring Diagram

Ensure that the LED strip you are using operates at a voltage of **5V**.
![Wiring Digram](https://github.com/Statonwest/VR_Ambilight/blob/e8cd4434b4d7c3b75dffecd37ce002222edb5176/Photos/Wiring%20Digram.jpg)
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

![Leds](https://github.com/Statonwest/VR_Ambilight/blob/e8cd4434b4d7c3b75dffecd37ce002222edb5176/Photos/LEDs.jpg)

Connect the data line, GND, and the 5V of the LED strip to the Arduino. Connect the DIN (data input) pin of the LED strip to digital pin 6 on the Arduino.

Double-check all the connections to ensure they are secure.

Position the LED strip on the sides of your face gasket, ensuring an even distribution of light. Refer to the image below for reference:

![Face Gasket wireing](https://github.com/Statonwest/VR_Ambilight/blob/4c1be2d51b12fa2441cf016311f411c63fe154cb/Photos/Face%20Gasket%20with%20LEDs.jpg)

Choose a wire routing method that works best for you. I opted to route the wires from underneath and over the top of the gasket, but there are other possible arrangements. Adjust your Prismatik settings accordingly to match your wire placement. 

Mount the Arduino Nano securely at the front of the index. Connect the Arduino Nano to the USB port for power and data transmission.

![Arduino mounted](https://github.com/Statonwest/VR_Ambilight/blob/a482895b87d1890fa9621ab019c8c148d78b8f43/Photos/Arduino%20Mounted.jpg)


## Diffusion Sheet

Cut out the diffusion sheet using the provided [Diffusion Template](https://github.com/Statonwest/VR_Ambilight/blob/3fd8a4334da56437a4c84d81b834a9e21e1f1194/Diffusion%20sheet%20template.png). I used an old display's diffusion and polarizing sheets.

Obtain two polarizing layers and place them parallel to each other. On top of these layers, position the diffusion sheet for optimal results. The order of arrangement should be as follows: "Vertical polarizing filter," "Horizontal polarizing filter," and "Diffusion Sheet."

Cut the tab off the middle sheet and hold all the layers together by using a small amount of tape along the edges.

Fold the tab and secure it with a dab of hot glue. Please note that the diffusion sheet may not easily stick to the glue, so scuff it up a bit before applying the adhesive.
![Diffusion Sheet Ex](https://github.com/Statonwest/VR_Ambilight/blob/fae2cbfcd293879b9292f5b8e32a33429b3695bb/Photos/Diffusion%20Sheet%20applied.jpg)

The bent tab provides a bit of "spring" action, allowing the filter to move along with the lenses to accommodate different [IPDs](https://en.wikipedia.org/wiki/Pupillary_distance)


## Prismatik

[Prismatik](https://github.com/psieg/Lightpack/releases) 
is the software we will utilize to capture the screen content and send the data to the Arduino.

Launch Prismatik and go through the initial setup process. Follow the on-screen instructions to configure the display settings.
![Prismatik settings](https://github.com/Statonwest/VR_Ambilight/blob/e728cd80f0c3ad1413558759991a7cd0a77fd714/Photos/Prismatik%20Settings.jpg)

Configure the output settings to match your Arduino connection. Select the correct COM port corresponding to the Arduino Nano.

Adjust any additional settings in Prismatik according to your preferences, such as brightness (e.g. 10%), and capture area (e.g. Screen 1).


## Steam VR / Auto Launch

Open Steam VR and choose the option "Display VR View" to enable viewing through both eyes.

Next, download the file [Auto_Launch.bat](https://github.com/Statonwest/VR_Ambilight/blob/d64d81af95ce442ccbf9eab3ec971fdd34c03d08/Auto_Launch.bat) and ensure it is placed in the identical directory as Steam VR. Usually, this directory can be found at "C:\Program Files (x86)\Steam\steamapps\common\SteamVR".

Make sure that the locations of both Prismatik and Steam VR installations are consistent.

Finally, include the following [Launch Option](https://help.steampowered.com/en/faqs/view/7d01-d2dd-d75e-2955) in Steam VR: "Auto_Launch.bat %COMMAND%".


## Alternative 3D printed diffuser

The 3D printed diffuser version was designed to provide better color-depth and ease of maintenance.

Both an STL and a Step file have been provided for printing and modification. Mirror the diffuser for the left side.

![Parts](https://github.com/Nemernemer/VR_Ambilight/blob/main/Photos/3D%20printed%20diffuser/Parts.jpg)

The diffusers are held in place by the face gasket and silicone membrane around the lenses.
![Parts assembled](https://github.com/Nemernemer/VR_Ambilight/blob/main/Photos/3D%20printed%20diffuser/Parts%20assembled.jpg)

Instead of mounting the LEDs to the face gasket, they are instead glued to the headset, pushed up against the edge on each side.
![Alternative LED mounting](https://github.com/Nemernemer/VR_Ambilight/blob/main/Photos/3D%20printed%20diffuser/LED%20mounting.jpg)

Glue more layers of paper onto the outside of the 3D print for more diffusion and light reduction. This example uses 2 layers of paper, allowing Prismatik to run at 50% brightness or 7 bits worth of color depth, resulting in less flashing.
![Diffuser example](https://github.com/Nemernemer/VR_Ambilight/blob/main/Photos/3D%20printed%20diffuser/Diffuser%20example.jpg)

Notes for the 3D print in example:

- Filament: Clear ABS

- Extrusion width: 0.86 (0.6 nozzle)

- Layer height: 0.16  (smaller layers recommended to avoid layers concentrating light into lines)

- Temperature: Below manufacturer recommendation for a matte finish



## To do

- [ ] Better diffusion

- [ ] Set Prismatik to only capture Steam VR window

- [ ] Better Prismatik Settings

- [ ] Better Mount for arduino

- [ ] Auto close Prismatik with Steam VR

- [ ] Quest 2 Support
