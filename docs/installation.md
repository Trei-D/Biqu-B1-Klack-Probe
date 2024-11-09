# Installation Guide

## Prerequisites
- Printed parts
- Required hardware (see [BOM.md](https://kevinakasam.com/klack-bom/))
- Klipper firmware installed

## Hardware Installation
1. [Probe Mount](https://kevinakasam.com/lets-build-the-probe-mount/)
2. [Probe Retainer](https://kevinakasam.com/lets-build-the-probe-retainer/)
3. [Probe Dock](https://kevinakasam.com/lets-build-the-probe-dock/)


## Software Setup
Klipper 

1. Demon Klipper Essential Unified + KlackB1-Probe Macros

1.1. Install [Demon_Klipper_Essentials_Unified](https://github.com/3DPrintDemon/Demon_Klipper_Essentials_Unified/tree/main) by following the [instructions](Documentation/INSTALL_INSTRUCTIONS/General _Setup_For_All_Printers/INSTALL_INSTRUCTIONS.md} from the repository.
1.2. Be sure to follow the instructions from this [step](https://github.com/3DPrintDemon/Demon_Klipper_Essentials_Unified/blob/main/Documentation/INSTALL_INSTRUCTIONS/General%20_Setup_For_All_Printers/INSTALL_INSTRUCTIONS.md#unless-youre-using-klicky-probe) 
1.3. Create a new directory in config folder with the name KlackB1
1.4. Copy the macros from this repository into KlackB1 folder
1.5. Edit printer.cfg by adding this line [include KlackB1/klicky-probe.cfg]

2. KevinAkaSam firmware

2.1. Open printer.cfg file and add the line [include KlackB1.cfg] and make these changes:
[stepper_z] endstop_pin: probe:z_virtual_endstop #if you want to use the Prove as z-endstop (You can unsinstall the stock z endstop then. If not, remove the [homing_override]) #position_endstop: 0 #remove this or uncomment it with a # position_min: -10 # set a negative value (minimum as the probe z_offset) [stepper_x] position_max: 235 #Your printhead have to move all the way to the right to pickup the probe. If your screw collides with the metal plate, simply flip it around.

2.2. Add KlackB1.cfg file in your config directory