# PortalGun
Code to control a Portal Gun (From Rick and Morty)

##Libraries
Download and install the following libraries:

- [ClickEncoder](https://github.com/0xPIT/encoder)
- [Adafruit_GFX](https://github.com/adafruit/Adafruit-GFX-Library)
- [Adafruit_LEDBackpack](https://github.com/adafruit/Adafruit-LED-Backpack-Library)

## Pin Definitions
If you deviate from the following definitions, you will have to change the firmware to account for that.

| LED Display | Feather 328P Pin |
|--------|--------|
|   SCL  |   A5 (SCL)   |
|	SDA  | 	 A4 (SDA)  |
|	GND  | 	 GND  |
|	Vcc  |   3.3V   |
|   Vi2c |   3.3V	  |


| Rotary Encoder | Feather 328P Pin |
|--------|--------|
|    A    |   A1  |
|    B    |   A0  |
|   GND   |  GND  |
| Button  |   A2  |

| FX SoundBoard | Feather 328P Pin |     Sound Effect   |
|---------------|-----------------|--------------------|
|    0          |   10            | Portal Shot        |
|    1          |   11 (MOSI)           | Encoder Tick       |
|    2          |   12 (MISO)            | Reset Dimension    |
|    3          |   13 (SCK)            | Dimension Rollover |
|    4          |    4            |   Power Up         |
|	 5	        |    7            |  Power Down        |
|	 VOL +	        |    A3            |  Volume Up      |


| LED | Feather 328P Pin |
|-------------|---------|
|Top Bulb +     |    9    |
|Front Right + |    3    |
|Front Center + |    5    |
|Front Left +  |    6    |
| All LEDS -   |    GND (Thru resistors)    |

I soldered everything onto a Proto Featherwing so the 328P can be removed and swapped out as needed.

## Installing Firmware
First, [set up the Arduino IDE according to Adafruit](https://learn.adafruit.com/adafruit-feather-328p-atmega328-atmega328p/arduino-ide-setup). THe Feather 328P is a little troublesome to program in my experience, so you'll probably need to hold the reset button while connecting the Feather 328P to the computer, and then let go of it a few seconds after hitting the upload button. YMMV.

##Installing SFX

Warning: The FX board schematic indicates that there are protection diodes seperating VIN from VBUS, but I recommend removing the Feather 328P from the socket when programming the FX board as a precaution since the Feather runs at 3.3V. I am not responsible if you fry your board(s).

You should be able to just connect the FX board to the computer, and drop the files in the "sfx" folder onto it. The files do follow a naming convention ([see here](https://learn.adafruit.com/adafruit-audio-fx-sound-board/triggering-audio)), so don't change the file names unless you know what you're doing.
