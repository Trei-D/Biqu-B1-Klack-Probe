# KlackEnder-Probe Installation Guide for Biqu B1

## Prerequisites
- All printed parts from the STL directory
- Required hardware components ([See BOM](https://kevinakasam.com/klack-bom/))
- Klipper firmware installed and operational
- Basic knowledge of Klipper configuration

## Hardware Assembly
Follow these guides in order:
1. [Probe Mount Assembly](https://kevinakasam.com/lets-build-the-probe-mount/)
2. [Probe Retainer Assembly](https://kevinakasam.com/lets-build-the-probe-retainer/)
3. [Probe Dock Assembly](https://kevinakasam.com/lets-build-the-probe-dock/)

## Software Configuration

### 1. Installing Demon Klipper Essential Unified & KlackB1-Probe Macros

1. Install [Demon_Klipper_Essentials_Unified](https://github.com/3DPrintDemon/Demon_Klipper_Essentials_Unified/tree/main)
   - Follow the repository's installation instructions
   - Pay special attention to the [Klicky Probe setup section](https://github.com/3DPrintDemon/Demon_Klipper_Essentials_Unified/blob/main/Documentation/INSTALL_INSTRUCTIONS/General%20_Setup_For_All_Printers/INSTALL_INSTRUCTIONS.md#unless-youre-using-klicky-probe)

2. Set up KlackB1-Probe Macros:
   - Create a new directory in config folder with the name KlackB1
   - Copy the macros from this [repository](https://github.com/Trei-D/KlackB1-Probe-Macros) into KlackB1 folder


3. Edit your `printer.cfg`:
   ```yaml
   [include KlackB1/klicky-probe.cfg]
   ```

### 2. Configuring KevinAkaSam Firmware

1. Add the following to your `printer.cfg`:
   ```yaml
   [include KlackB1.cfg]
   
   [stepper_z]
   endstop_pin: probe:z_virtual_endstop   # Enable probe as Z-endstop
   #position_endstop: 0                   # Comment out or remove this line
   position_min: -10                      # Set to negative probe z_offset value
   
   [stepper_x]
   position_max: 235                      # Ensures full probe dock access
   ```

2. Create `KlackB1.cfg` in your config directory

## Important Notes

- If using the probe as Z-endstop, you may remove the stock Z-endstop
- If the X-axis screw interferes with the metal plate, rotate the screw 180 degrees
- Always test probe attachment and docking at low speeds initially
- Back up your configuration files before making changes

## Verification Steps

After completing the installation:
1. Verify all probe connections
2. Test probe attachment/detachment manually
3. Perform a test probe accuracy check
4. Create and verify bed mesh

## Support

If you encounter issues:
- Check the [Troubleshooting Guide](link-to-troubleshooting)
- Visit the [Project Discussion Board](link-to-discussions)
- Review [Common Problems & Solutions](link-to-faq)

## License

This modification is released under the same license as the original KlackEnder-Probe project.