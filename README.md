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


### Finer density LED Strips by [OfficerSkidmark](https://github.com/OfficerSkidmark)

![Dense Leds Strip](https://private-user-images.githubusercontent.com/110629277/324322049-5840d202-70ce-44e8-97b2-7244db645ca2.jpg?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NDMxMjkwMzksIm5iZiI6MTc0MzEyODczOSwicGF0aCI6Ii8xMTA2MjkyNzcvMzI0MzIyMDQ5LTU4NDBkMjAyLTcwY2UtNDRlOC05N2IyLTcyNDRkYjY0NWNhMi5qcGc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwMzI4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDMyOFQwMjI1MzlaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT0xOTkzM2VjNTY1ZmI3N2M0MTJiMWFiNTMyMWVlOTZiMjI5ODc0ZDZiYWNmMzc0YjIzODRjYjE4ZDZiMzY5MjhjJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.BkFI0sxHjXNRvRNbiCjlrL9kP9Zi84itNVZxc4steGE)

Officer Skidmark used 1,035 LEDs rather than the WS2812b. This provides a much higher resolution while reducing power draw and decreasing the brightness to a more appropriate level.

![Dens Led Strip](https://private-user-images.githubusercontent.com/110629277/323023932-c4211543-2685-4ae9-8bd2-9ce1fb209e6c.jpg?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NDMxMjkzMTIsIm5iZiI6MTc0MzEyOTAxMiwicGF0aCI6Ii8xMTA2MjkyNzcvMzIzMDIzOTMyLWM0MjExNTQzLTI2ODUtNGFlOS04YmQyLTljZTFmYjIwOWU2Yy5qcGc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwMzI4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDMyOFQwMjMwMTJaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1hNjY0NGIxZDBkNjgwNTdhMjk5ZTkxZWNiYTY3Mzg4ZTRlNWRmZGNmZDAwM2IwZWMzMzM1ZGRkZjRjZTI3YWJmJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.ayrqzSDeLkF-sk-InqSGFH6IGerjj5OXWEopvYScf-s)

## Diffusion Sheet

Cut out the diffusion sheet using the provided [Diffusion Template](https://github.com/Statonwest/VR_Ambilight/blob/3fd8a4334da56437a4c84d81b834a9e21e1f1194/Diffusion%20sheet%20template.png). I used an old display's diffusion and polarizing sheets.

Obtain two polarizing layers and place them parallel to each other. On top of these layers, position the diffusion sheet for optimal results. The order of arrangement should be as follows: "Vertical polarizing filter," "Horizontal polarizing filter," and "Diffusion Sheet."

Cut the tab off the middle sheet and hold all the layers together by using a small amount of tape along the edges.

Fold the tab and secure it with a dab of hot glue. Please note that the diffusion sheet may not easily stick to the glue, so scuff it up a bit before applying the adhesive.
![Diffusion Sheet Ex](https://github.com/Statonwest/VR_Ambilight/blob/fae2cbfcd293879b9292f5b8e32a33429b3695bb/Photos/Diffusion%20Sheet%20applied.jpg)

The bent tab provides a bit of "spring" action, allowing the filter to move along with the lenses to accommodate different [IPDs](https://en.wikipedia.org/wiki/Pupillary_distance)


## Alternative 3D Printed Diffuser by [Nemernemer](https://github.com/Nemernemer)

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


## Sampler / Screen Capture
[OpenVR Ambient Light](https://github.com/Rectus/openvr_ambient_light) is the control software for ambient LED lighting in virtual reality headsets. Unlike most other control software that sample the desktop, OpenVR Ambient Light directly samples the VR headset view. This provides accurate light estimation based on the content actually shown by the headset, and prevents other windows on the desktop from interfering.

## <strike>Screen Capture (Legacy)
[Prismatik](https://github.com/psieg/Lightpack/releases) serves as the primary software solution for our guild's needs, although there are several alternative options available, such as [Firefly Luciferin](https://github.com/sblantipodi/firefly_luciferin). Firefly is recognized for its lower computational resource requirements.

The software is used for screen content capture and data transmission to the Arduino.

Launch Prismatik and go through the initial setup process. Follow the on-screen instructions to configure the display settings.
![Prismatik settings](https://github.com/Statonwest/VR_Ambilight/blob/e728cd80f0c3ad1413558759991a7cd0a77fd714/Photos/Prismatik%20Settings.jpg)

Configure the output settings to match your Arduino connection. Select the correct COM port corresponding to the Arduino Nano.

Adjust any additional settings in Prismatik according to your preferences, such as brightness (e.g. 10%), and capture area (e.g. Screen 1).
</strike>


## To do

- [x] Better diffusion

- [ ] Better Mount for arduino
