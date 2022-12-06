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
   │   └── lcd
   │        └── lcd.definitions.h
   │        └── lcd.h
   │        └── lcd.c
   ├── src             // Source file(s)
   │   └── main.c
   └── platformio.ini  // Project Configuration File
   ```

### Team members

* Maksim Migulia (233261)
* Anna Litovska (231581)

## Hardware description

### Joy-stick

* GND to GND 
* +5V to +5V
* Vrx and Vry we connect to analog pins A0, A1 

### Digilent PmodCLP LCD modul 

* GND to GND 
* VCC to +5V J2
* pins 7,10 to digital pins 4, 7
* RW to GND
* Rs and En to digital pins 8 and 9

![image](https://user-images.githubusercontent.com/99403646/205863718-c15f8ad5-0dea-43c7-92e9-262a9b21254c.png)
Obr. 1 - Schéma zapojení v SimulIDE

![image](https://user-images.githubusercontent.com/99403646/205864286-3a4a17cd-4702-49ea-a2d2-6c1e31e3c709.png)
Obr. 2 - Schéma zapojení v reálu

## Software description

Put flowchats of your algorithm(s). Write descriptive text of your libraries and source files. Put direct links to these files in `src` or `lib` folders.

## Video
https://youtu.be/-JzXT4BKrfg
