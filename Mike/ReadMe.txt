Arduino Based LaserTag System
** Note this project is still a work in progress **

I'm using a Teensy 3.2 as the extra processing power will come in handy when I later add a colour TFT display and a sound processor.



Parts List

MicroController (I am using a Teensy 3.2 - An Arduino nano will do fine)
5 momentary pushbuttons (e.g. Rapid Order Code: 51-0712 )
IR Emitter (Vishay TSAL6200 5mm 940nm IR Transmitter Diode) Rapid Order Code:  49-4513
IR Reciever (38kHz) (Vishay TSOP4838 950nm IR Receiver Module 38kHz) Rapid Order Code:49-4728 
5 x High Value Resistors (for buttons) 1K+
3 x Current Limiting Resistor for RGB LED (Depends on your LED datasheet - See https://www.sparkfun.com/tutorials/219) 
Clear Blue LED(s) for Muzzle Flash
Red LED for HIT
RGB LED for Health/Team
16x2 LCD Display with HD44780 Controller (e.g. Rapid Order Code or use eBay)
10k Potentiometer (for LCD contrast)
Piezo Buzzer



Pins used

Trigger button on Pin 2
Reload Button on Pin 6
RGB LED on Pins, 21, 22, 23
IR LED (20 degree) on Pin 5
Piezo Buzzer on Pin 4
16x2 LCD DIsplay on pins 11,12,10,9,8,7
Muzzle Flash LED's on Pin 3
Up menu button on Pin 14
Down menu button on Pin 13
Enter menu button on pin 15
IR Receiver on Pn 16
HIT LED on Pin 17

All buttons must be pulled to ground when not pressed. 



The data packet is 32 bits:

0..6     7-bit  : Damage (using a 128 element look-up table for damage) 
7..12     6-bit  : Player ID (64 Players per team)
13..15    3-bit  : Team ID (8 teams - Red, Blue, Green, Yellow, Cyan, magenta, White, Solo)
16..31   16-bit : CRC-16



Required libraries:

<LiquidCrystal.h>  Stock Arduino library
<Button.h>         https://github.com/JChristensen/Button
<IRRemote.h>       https://github.com/z3t0/Arduino-IRremote
<FastCRC.h>        https://github.com/FrankBoesing/FastCRC




