# EssaiBiblio
Repository d'essai pour ma bibliothèque

This library allows you to easily create light animations
from an Arduino board or an ATtiny microcontroller (traffic lights,
chaser, shopkeeper sign, etc.)

The LEDs are connected to the digital outputs of the Arduino board or the
microcontroller with a resistor limiting the current in the LED.
The resistor value depends on the color of the LED and must take into account
the current limitation of the digital output and the possibilities of the card.

The LEDs can be connected to the digital outputs by their anode or else
by their cathode, but all LEDs must be connected in the same way.
In addition, the digital outputs used must follow each other in ascending order
of their numbering.
Caution: do not confuse digital output number and microcontroller's pin number
(see the card or microcontroller documentation).

The library uses delay() function, which does not allow to use it in a
program doing something other than managing light effects.

## How to use the library 
--------------------------
Include the library at the beginning of the program with
#include <LightEffect.h>

Instantiate one or more light effects by giving a name to the object and specifying
the position of the first LED, the number of LEDs and the logic level to light them.
LightEffect mySign (4, 6, LOW);
The 6 LEDs are connected by their cathode since a LOW level lights them, the first
LED is on digital output 4.

If several light effects are created, the sequences are played one after the others
and must be cleverly chosen to give the impression of independence of each light effect
(see the example given Electric_sign).

# How to call the sequences 
-----------------------------
The sequences are called with the following syntax : objectName.function ();
objectName is the name given to the object and function() one of the functions of the
library (see below) with or without arguments. Example:
mySign.onRight ();

