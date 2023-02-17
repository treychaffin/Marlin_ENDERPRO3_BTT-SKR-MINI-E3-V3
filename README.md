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

# Cura Configuration

In cura, I use the stock configuration for Creality Ender 3.

The line `G1 X117 Y235 Z60 ; Move to clean position` has been added to the stock Ender 3 Custom Start G-code, as shown in the picture below. 

![Custom Start G-code](/pics/custom-start-g-code.PNG)

This raises the hotend, moves the hotend to the center, and pushes the bed forward. This allows the user to clean the bed and apply bed coating while the bed and hotend heats up.

# Octoprint Configuration

[OctoPrint](https://octoprint.org/)

Hardware Used:

- [Raspberry Pi 3 Model B+](https://www.raspberrypi.com/products/raspberry-pi-3-model-b-plus/)

## Plugins Used:
- [Bed Visualizer](https://plugins.octoprint.org/plugins/bedlevelvisualizer/)
    - GCODE Commands for Mesh Update Process:
        ```
        M190 S80 ; Start heating the bed, wait until target temperature reached
        G28
        @BEDLEVELVISUALIZER
        G29 T
        ```
- [BetterHeaterTimeout](https://plugins.octoprint.org/plugins/BetterHeaterTimeout/)
- [CustomBackground](https://plugins.octoprint.org/plugins/custombackground/)
- [DisplayLayerProgress](https://plugins.octoprint.org/plugins/DisplayLayerProgress/)
- [Navbar Temp](https://plugins.octoprint.org/plugins/navbartemp/)
- [Octolapse](https://plugins.octoprint.org/plugins/octolapse/)
- [OctoPrint-Display-ETA](https://plugins.octoprint.org/plugins/display_eta/)
- [Print History](https://plugins.octoprint.org/plugins/printhistory/)
- [OctoPrint-PrintTimeGenius](https://plugins.octoprint.org/plugins/PrintTimeGenius/)
- [Terminal Commands Extended](https://plugins.octoprint.org/plugins/terminalcommandsextended/)
    - Custom Commands:
        - MOVE NOZZLE TO CLEAN POSITION
            - ```
                G1 X117 Y235 Z60
                ```
        - CLEAN EXTRUDER
            - ```
                G1 X117 Y235 Z60;
                M109 S240;
                G91;
                M83;
                G1 E200 F300;
                M82;
                G90;
                M104 S0;
                ```
        - PID AUTOTUNE HOTEND 275
            - ```
                M303 C15 E0 S275 U1
                ```
        - PID AUTOTUNE HOTEND 240
            - ```
                M303 C15 E0 S240 U1
                ```
        - PID AUTOTUNE HOTEND 250
            - ```
                M303 C15 E0 S250 U1
                ```
        - PID AUTOTUNE BED 80
            - ```
                M303 C15 E-1 S80 U1
                ```
        - SAVE SETTINGS TO EEPROM
            - ```
                M500
                ```
        - MARLIN TRAMMING ASSISTANT
            - ```
                G35 S40
                ```
- [Themeify](https://plugins.octoprint.org/plugins/themeify/)
    - Configuration:

    | Selector | CSS-Rule | Value |
    |----------|----------|-------|
    | .navbar-inner | background-color | #2f3136 |
    | .accordion | background-color | #2f3136 |
    | .span8 | width | 70% |
    | .container | width | 100% |
    | .span4 | width | 25% |
    | .row | margin-left | 0 |