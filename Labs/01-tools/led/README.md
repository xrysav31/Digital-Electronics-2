# Lab 1: Ondřej Ryšavý

Link to your `Digital-electronics-2` GitHub repository:

   [https://github.com/...](https://github.com/xrysav31/Digital-Electronics-2)


### Blink example

1. What is the meaning of the following binary operators in C?
   * `|`    OR
   * `&`    AND
   * `^`    XOR
   * `~`    NOT 
   * `<<`   left shift
   * `>>`   right shift

2. Complete truth table with operators: `|`, `&`, `^`, `~`

| **b** | **a** |**b or a** | **b and a** | **b xor a** | **not b** |
| :-: | :-: | :-: | :-: | :-: | :-: |
| 0 | 0 | 0 | 0 | 0 | 1 |
| 0 | 1 | 1 | 0 | 1 | 1 |
| 1 | 0 | 1 | 0 | 1 | 0 |
| 1 | 1 | 1 | 1 | 0 | 0 |


### Morse code

1. Listing of C code with syntax highlighting which repeats one "dot" and one "comma" (BTW, in Morse code it is letter `A`) on a LED:

```c
...
#define LED_GREEN   PB5 // AVR pin where green LED is connected
#define SHORT_DELAY 300 // Delay for short break
#define LONG_DELAY 1500 // for long break (between letters)
#define DOT 100         // dot 
#define DASH 500       // dash 
...

int dot(void)
{
    PORTB = PORTB ^ (1<<LED_GREEN);
    _delay_ms(DOT);
    PORTB = PORTB ^ (1<<LED_GREEN);
    _delay_ms(SHORT_DELAY);
    return 0;
}

int dash(void)
{
    PORTB = PORTB ^ (1<<LED_GREEN); //on
    _delay_ms(DASH);
    PORTB = PORTB ^ (1<<LED_GREEN);
    _delay_ms(SHORT_DELAY);
    return 0;
}

int break_l(void) //between letters
{
    _delay_ms(LONG_DELAY);
    return 0;
}

int main(void)
{
    // Set pin as output in Data Direction Register
    // DDRB = DDRB or 0010 0000
    DDRB = DDRB | (1<<LED_GREEN);

    // Set pin LOW in Data Register (LED off)
    // PORTB = PORTB and 1101 1111
    PORTB = PORTB & ~(1<<LED_GREEN);

    // Infinite loop
    while (1)
    {
        break_l();
        dot();
        dot();
        dot();
        break_l();
        dash();
        dash();
        dash();
        break_l();
        dot();
        dot();
        dot();
        break_l();
    }

    // Will never reach this
    return 0;
}
}
```


2. Scheme of Morse code application, i.e. connection of AVR device, LED, resistor, and supply voltage. The image can be drawn on a computer or by hand. Always name all components and their values!

   ![your figure](https://github.com/xrysav31/Digital-Electronics-2/blob/main/Labs/01-tools/led/Arduino.png)
