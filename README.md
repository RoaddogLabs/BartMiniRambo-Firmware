### Roaddog Labs Bart 24 volt Mini Rambo Firmware
### 


This fork is configured specifically for the Roaddog Labs Bart with a 24 volt Mini Rambo controller.  It's based on Marlin 1.1.0-RC3 that was pushed 01 Dec, 2015.  This build is configured for a Mini Rambo controller using 200 mm x 200 mm PCB heated print bed and Reprap Discount Full Graphic Smart Controller.


Details and specs for the Mini Rambo are at http://reprap.org/wiki/MiniRambo

__How to Use__

The settings are preconfigured for the stock configuration as shipped from Roaddog Labs.  There are a few things to know that vary from a Marlin/RAMPS setup.

The stepper motor driver current settings are controlled using PWM.  Those settings are in the [pins_MINIRAMBO.h](./BartMiniRambo/pins_MINIRAMBO.h) file.  It's set for what we use in the Roaddog Labs bot farm.  Details on metering the board to set the current are at [Mini Rambo Reprap Wiki page](http://reprap.org/wiki/MiniRambo#Changing_Motor_Current_.28similar_to_Trimpot.2FDigipot.29).

Due to I2C interface differences with the Mini Rambo the `#pragma GCC optimize` setting in line 9 of the file [ultralcd_st7920_u8glib_rrd.h](./BartMiniRambo/ultralcd_st7920_u8glib_rrd.h)

Details at http://reprap.org/wiki/MiniRambo#REPRAP_DISCOUNT_FULL_GRAPHIC_SMART_CONTROLLER 






The [original README.md](Orig_README.md) from the fork.