#  X-Mas-WTree!

This is a simple Chrismas tree project inspired by [bluqesh](https://www.instructables.com/PCB-Christms-Tree/). I've updated its design adding slots for board to board connection and addressable RGB leds.

At that point I've also switched the MCU to an ESP8266 to add WiFi capability, and using the amazing [WLED](https://github.com/Aircoookie/WLED) project to control everything.

Project files are available in the `Project Outputs for xMas-Tree` directory.
In the 3DModel folder there is the 3D model and the "textures", and some photos.

### Features

 - USB C Compatible, it negotiate 5V@900mA
 - IR Remote receiver
 - WiFI controllable
 - Full PCB is 10cm x 10cm so it fit the 2$ JLCPCB option.
 - Most of the components are available from LCSC.**\***
 - Different patterns and animations
 - More info on [WLED](https://github.com/Aircoookie/WLED) project

**\*The ESP8266-12 and the LEDs have to be bought separately**

## Soldering

While placing the `0603` components is not that hard if you have SMD skills soldering the LEDs is quite **difficult!** Mostly due to the VIAs to give the pads more rigidity. I'm still experimenting a way to easily solder the LEDs, probably using a stencil and low temp solder with hot air is the best solution.

Right now I'm soldering the second tree.

For now my assembly procedure (without hot plate soldering and solder paste) is:

 1. Solder all the `0603` excpet the one near the USB C contacts.
 2. Solder the USB C
 3. Solder the 5.1K resistor skipped on step 1.
 4. Solder the ICs.
 5. Solder the LEDs, make sure that they are firmly soldered.
 6. Solder the ESP module.
 7. Check for shorts and program the ESP. Test if first 6 leds are working.
 8. Snap the boards and solder them together
 9. Check again for shorts and enjoy!

Probably with hot air and a low melting point solder paste step 1-6 can be done in a single jump. 
Right now I only have flux, and 60/40 solder.

## PCB Errors
 - The USB FUSE seems to be not working as expected, so a 0OHM link is
   required.

## PROGRAMMING

The touch button is connected to the `BOOT0` pin, so you have to press that while you start the sketch upload process.
A FTDI 3.3V module with `RESET` is required, I didnt had one so I temporary connected a wire to ground while also pressing the TOUCH button.

The FW can be found under the [WLED](https://github.com/Aircoookie/WLED/releases) repository, I'm using a ESP12, so `d1_mini` is the right platform to choose.
