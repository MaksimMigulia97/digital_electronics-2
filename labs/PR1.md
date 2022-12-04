# Project 1

Application of analog joy-stick (2 ADC channels, 1 push button), rotary encoder, and Digilent PmodCLP LCD module.



## GitHub repository structure

   ```c
   PROJECT        // PlatfomIO project
   ├── include
   │  └── timer.h       
   ├── lib             // Libraries
   │  └── gpio
   │       └── gpio.c
   │       └── gpio.h
   │
   │   └── lcd
   │        └── lcd.definitions.h
   │        └── lcd.h
   │        └── lcd.c
   │
   ├── src             // Source file(s)
   │   └── main.c
   └── platformio.ini  // Project Configuration File
   ```

## Recommended README.md file structure

### Team members

* Maksim Migulia (233261)
* Anna Litovska (______)

## Hardware description

### Joystick

* GND to GND 
* +5V to +5V
* Vrx and Vry we connect to analog pins A0, A1 

### Rotation encoder

* GND to GND
* +5V to +5V
* CLK and DT to digital pins 11, 12
* SW to digital pin 2

### Digilent PmodCLP LCD modul 

* GND to GND 
* VCC to +5V J2
* pins 7,10 to digital pins 4, 7
* RW to GND
* Rs and En to digital pins 8 and 9

## Software description

Put flowchats of your algorithm(s). Write descriptive text of your libraries and source files. Put direct links to these files in `src` or `lib` folders.

## Video
https://youtu.be/-JzXT4BKrfg
