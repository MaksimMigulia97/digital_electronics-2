/* Includes ----------------------------------------------------------*/
#include <avr/io.h>         // AVR device-specific IO definitions
#include <avr/interrupt.h>  // Interrupts standard C library for AVR-GCC
#include <gpio.h>           // GPIO library for AVR-GCC
#include "timer.h"          // Timer library for AVR-GCC
#include <lcd.h>            // Peter Fleury's LCD library
#include <stdlib.h>         // C library. Needed for number conversions

int position;
int x;
int y;

int main(void)
{
    // Initialize display
    lcd_init(LCD_DISP_ON);
    lcd_gotoxy(1, 0); lcd_puts("joy:");
    lcd_gotoxy(1, 1); lcd_puts("encoder:");
    lcd_gotoxy(6, 0); lcd_puts("0");
    lcd_gotoxy(9,1); lcd_puts("0");
     ADMUX = ADMUX | (1<<REFS0);
     ADMUX = ADMUX & ~((1<<MUX3) | (1<<MUX2) | (1<<MUX1)| (1<<MUX0));
     ADCSRA |= (1<<ADEN);
    ADCSRA |= (1<<ADIE);
    ADCSRA |= (1<<ADPS2) | (1<<ADPS1) | (1<<ADPS0);
    TIM1_overflow_262ms();
    TIM1_overflow_interrupt_enable();
    sei();
    while (1)
    {
        /*  Ань я не понял зачем это надо? Если не нужно удали */
    }
    return 0;
}
ISR(TIMER1_OVF_vect)
{
    if (position == 0)
    {
      ADMUX |= (1<<MUX0);
      ADCSRA |= (1<<ADSC);
       y = ADC;
    }
    else
    {
      ADMUX = ADMUX &= ~ (1<<MUX0);
      ADCSRA |= (1<<ADSC);
      x = ADC;


    }

}
ISR(ADC_vect)
{
    uint16_t value;
    char string[4];
    itoa (x, string, 10);
    lcd_gotoxy(6,0);
    lcd_puts("    ");
    lcd_gotoxy(6,0);
    lcd_puts(string);
    lcd_gotoxy(10, 0);
    if (x >530 )
    {
     lcd_gotoxy(10, 0);
     lcd_puts("right");
    }
    else if (x < 100)
    {
      lcd_gotoxy(10, 0);
      lcd_puts("left ");
    }

   lcd_gotoxy(10, 0);
    if (y >530 )
      lcd_puts("up   ");
    else if (y < 100)
      lcd_puts("down ");
      if (position == 0)
      position = 1;
      else
      position = 0;

}
