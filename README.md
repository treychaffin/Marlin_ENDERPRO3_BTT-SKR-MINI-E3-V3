# Marlin Configuration

This is my configuration for my 3D printer, primarily used for printing PLA and PETG

## Machine Set-up

- [Ender Pro 3](https://www.creality3dofficial.com/products/creality-ender-3-pro-3d-printer)
    - [Spare Hotend](https://www.amazon.com/Creality-3D-Assembled-Extruder-Capricorn/dp/B07WNQP916/)
- [Bigtreetech SKR Mini E3 V3](https://www.amazon.com/BIGTREETECH-Control-TMC2209-Stepper-Upgrade/dp/B09LC34SCK/)
- [BLtouch](https://www.amazon.com/ANTCLABS-BLTouch-Leveling-Premium-Extension/dp/B076PQG1FF)
    - [BLtouch Mount for Ender 3](https://www.amazon.com/gp/product/B08G8B23L7/)
- [Micro Swiss Bowden Dual Gear Extruder](https://www.amazon.com/dp/B09K1CNP6L)
    - [Spare Brass Compression Ferrule Rings - 4MM](https://www.amazon.com/gp/product/B07P7GJCGF/)
- [Glass Sheet: used as print bed, cut to 235mm x 235mm](https://www.menards.com/main/doors-windows-millwork/millworkacrylic-glass-hidden/standard-acrylic-glass/amerilux-0-093-thick-clear-glass-sheets/clg10x12/p-1564036106427-c-1513288675243.htm)
    - [Glass Cutting Tool Set](https://www.menards.com/main/tools/hand-tools/hand-saws-saw-blades/glass-cutting-tool-set-3-piece/czgc3/p-1444428122412-c-9123.htm)
    - [Aqua Net Hairspray: used for coating bed before each print, helps with bed adhesion and print removal](https://www.amazon.com/Extra-Super-Professional-Spray-Unscented/dp/B00908551C)

## Cura Configuration

In cura, I use the stock configuration for Creality Ender 3.

The line `G1 X117 Y235 Z60 ; Move to clean position` has been added to the stock Ender 3 Custom Start G-code, as shown in the picture below. 

![Custom Start G-code](/pics/custom-start-g-code.PNG)

This raises the hotend, moves the hotend to the center, and pushes the bed forward. This allows the user to clean the bed and apply bed coating while the bed and hotend heats up.

### Printing with PETG

I've had trouble printing with PETG using the stock configuration and I'm currently experimenting with settings to optimize results. The nozzle often clogs and has underextrusion, extruder skipping, or no extrusion. 

![PETG-Problems](/pics/PETG-problems.jpg)

I'm experimenting with adjusting the cooling settings, as I think it may be causing the filament to cool and clog the nozzle.

![Cura-PETG-Cooling-Settings](/pics/cura-PETG-cooling-setting.PNG)

I've also am trying adjusting the print speed settings.

![Cura-PETG-Print-Speed-Settings](/pics/cura-PETG-print-speed-settings.PNG)