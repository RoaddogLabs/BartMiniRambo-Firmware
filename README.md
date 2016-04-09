### Roaddog Labs Bart 24 volt Mini Rambo Firmware
### 


This fork is configured specifically for the Roaddog Labs Bart with a 24 volt Mini Rambo controller.  It's based on Marlin 1.1.0-RC3 that was pushed 01 Dec, 2015.  This build is configured for a Mini Rambo controller using 200 mm x 200 mm PCB heated print bed and Reprap Discount Full Graphic Smart Controller.


Details and specs for the Mini Rambo are at http://reprap.org/wiki/MiniRambo

__How to Use__

The settings are preconfigured for the stock configuration as shipped from Roaddog Labs.  There are a few things to know that vary from a Marlin/RAMPS setup.

The stepper motor driver current settings are controlled using PWM.  Those settings are in the [pins_MINIRAMBO.h](./BartMiniRambo/pins_MINIRAMBO.h) file.  It's set for what we use in the Roaddog Labs bot farm. 

`#define DEFAULT_PWM_MOTOR_CURRENT  {900, 900, 850} // XY Z E0 `

The motor currents can be set during run time using the mcode M907 in Marlin. Recommended for testing purposes only.

`M907 X100 Z100 E100 ;Max 255`


Due to SPI interface issues in the firmware the `#pragma GCC optimize` setting in line 9 of the file [ultralcd_st7920_u8glib_rrd.h](./BartMiniRambo/ultralcd_st7920_u8glib_rrd.h)

`#pragma GCC optimize (3)`

To:

`#pragma GCC optimize (0)`


*Note: This fix is only for the Graphical LCD. The bug is caused by the firmware sending the data too fast over the software implementation  of SPI.


Windows platforms need the [Rambo driver](http://reprap.org/wiki/File:RAMBo_USBdriver.zip)


The Rambo board config needs to be installed in the Arduino IDE.



The [original README.md](Orig_README.md) from the fork.