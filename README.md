# Klipper Firmware

> ### WARNING!
> This repo is for my own personal use so that I have a backup of my Klipper config.  Copying this config as-is
> to use as your own could worst case cause damage to your printer.  If you are using this as a base to define
> your own configuration, make sure that you also read the [official Klipper examples](https://github.com/KevinOConnor/klipper/blob/master/config/example-extras.cfg) to understand what the 
> settings mean, and more importantly what they need to be set for your particular printer.
>
> Use at your own risk!

Klipper config for MakerFarm Pegasus 8" printer with the following modifications that impact firmware configuration:
- SKR 1.4 board
- TMC2209 drivers on XYZ
- A4988 driver on E0
- Pegasus Direct Drive Extruder
- E3D Lite6 hotend
- 12V PSU

Includes the following macros
- START_PRINT : to be called at start of each print.  Homes, loads the bed mesh profile, then calls PRIME_LINE
- PRIME_LINE : called by START_PRINT to draw a couple of primes before the print to prime the nozzle
- END_PRINT : to be called at the end of each print.  Turns off heaters and motors
- M600 : Load filament macro (calls PAUSE_MACRO then UNLOAD macros)
- PAUSE_MACRO : Saves the gcode state, calls PAUSE, then PARK_MACRO
- PARK_MACRO : Moves the nozzle to a safe location
- UNLOAD : Retracts the filament
- PURGE : Purges 45mm of filament
- LOAD_FILAMENT : Loads filament
- RESUME_MACRO : Loads the gcode state that was saved during PAUSE_MACRO, then calls RESIME
- G29 : Automatic bed levelling

Other points to note:
TODO
