# Lab 1: Maksim Migulia

### Morse code

1. Listing of C code which repeats one "dot" and one "comma" (BTW, in Morse code it is letter `A`) on a LED. Always use syntax highlighting, meaningful comments, and follow C guidelines:

```c
#define LED_GREEN 13  
#define SHORT_DELAY 250 
#define LONG_DELAY 500 
#ifndef F_CPU
# define F_CPU 16000000 
#endif
#include <avr/io.h>    
#include <util/delay.h> 
#include "Arduino.h"        

int main(void)
{
    // Set pin where on-board LED is connected as output
    pinMode(LED_GREEN, OUTPUT);

    // Infinite loop
    while (1)
    {
        // Generate a lettre `A` Morse code

      digitalWrite(LED_GREEN, LOW);
        _delay_ms(SHORT_DELAY);
        digitalWrite(LED_GREEN, HIGH);
        _delay_ms(SHORT_DELAY);
        digitalWrite(LED_GREEN, LOW);
        _delay_ms(SHORT_DELAY);
        digitalWrite(LED_GREEN, HIGH);
        _delay_ms(LONG_DELAY);

    }

    // Will never reach this
    return 0;
}
```

2. Scheme of Morse code application, i.e. connection of AVR device, LED, resistor, and supply voltage. The image can be drawn on a computer or by hand. Always name all components and their values!

![image](https://user-images.githubusercontent.com/99403646/193651481-118604da-09d6-40f4-919f-b21c7f8a4d47.png)


