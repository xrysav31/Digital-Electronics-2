# Lab 6: YOUR_FIRSTNAME FAMILYNAME

Link to your `Digital-electronics-2` GitHub repository:

[https://github.com/your-github-account/repository-name/lab_name](https://github.com/...)


### LCD display module

1. In your words, describe what ASCII table is.
   * ASCII - Coding table of common characters used originally in teletype and printers. ASCII table also includes special characters (eg. backspace) and nonprintable characters (eg. blank space).

2. (Hand-drawn) picture of time signals between ATmega328P and LCD keypad shield (HD44780 driver) when transmitting three character data `De2`.  
`D` = 68 = 0x44 = 0b01000100  
`e` = 101 = 0x65 = 0b01100101  
`2` = 50 = 0x32 = 0b00110010
    
   ![diagram](images/diagram1.jpg)


### Stopwatch

1. Flowchart figure for `TIMER2_OVF_vect` interrupt service routine which overflows every 16&nbsp;ms but it updates the stopwatch LCD approximately every 100&nbsp;ms (6 x 16&nbsp;ms = 100&nbsp;ms). Display tenths of a second and seconds `00:seconds.tenths`. Let the stopwatch counts from `00:00.0` to `00:59.9` and then starts again. The image can be drawn on a computer or by hand. Use clear descriptions of the individual steps of the algorithms.

   ![flowchart](images/flowchart.png)


### Custom characters

1. Code listing with syntax highlighting of two custom character definition:

```c
/* Variables ---------------------------------------------------------*/
// Custom character definition
uint8_t customChar[16] = {
    0b00111,
    0b01110,
    0b11100,
    0b11000,
    0b11100,
    0b01110,
    0b00111,
    0b00011,
    0b00000,
	  0b00100,
	  0b00110,
	  0b00111,
	  0b00110,
	  0b00100,
	  0b00100,
    0b11111
};
```


### Kitchen alarm

Consider a kitchen alarm with an LCD, one LED and three push buttons: start, +1 minute, -1 minute. Use the +1/-1 minute buttons to increment/decrement the timer value. After pressing the Start button, the countdown starts. The countdown value is shown on the display in the form of mm.ss (minutes.seconds). At the end of the countdown, the LED will start blinking.

1. Scheme of kitchen alarm; do not forget the supply voltage. The image can be drawn on a computer or by hand. Always name all components and their values.

   ![scheme](images/schema.svg)
   ![scheme](images/04.svg) 
