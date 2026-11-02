# Specter LGA64 · Rev A placement draft

The trial outline is 20 × 20 mm. Four rows of 16 contacts on 1 mm pitch leave the center available for routing. Land centers sit 1 mm inside the nominal edge. Each copper land measures 1.0 mm radially by 0.6 mm tangentially. Pin 1 is near the northwest corner on the west edge.

Coordinates below use the module center as origin, looking through the module from the component side. Positive X points right and positive Y points down. Both footprints use this same top-view coordinate frame. Place the module interface footprint unflipped on the module board: its copper is already on B.Cu and it has no paste openings. Place the carrier footprint on F.Cu; paste is on the carrier. For carrier schematics use the library symbol, override its footprint to SoM:Specter_LGA64_Carrier and enable its BOM entry. The F.Fab square is a placement outline. Define the actual module perimeter on Edge.Cuts during the board trial.

GPIO and control signals use the module’s 3.3 V I/O domain. GPIO40–47 double as ADC0–7. GPIO0 selects the onboard PSRAM. Connect all grounds. Populate only R7 for the 5 V build or only R8 for the regulated 3.3 V build. RUN and BOOTSEL_N are active low. Validate escape routing, thermal return paths, land and stencil dimensions, alignment and solder joints before ordering.

| Pad | Module net | X (mm) | Y (mm) |
|---:|---|---:|---:|
| 1 | GND | -9 | -7.5 |
| 2 | VCC_IN_5V | -9 | -6.5 |
| 3 | GND | -9 | -5.5 |
| 4 | VCC_IN_3V3 | -9 | -4.5 |
| 5 | RUN | -9 | -3.5 |
| 6 | BOOTSEL_N | -9 | -2.5 |
| 7 | SWCLK | -9 | -1.5 |
| 8 | SWDIO | -9 | -0.5 |
| 9 | GND | -9 | 0.5 |
| 10 | USB_N | -9 | 1.5 |
| 11 | USB_P | -9 | 2.5 |
| 12 | GND | -9 | 3.5 |
| 13 | GPIO1 | -9 | 4.5 |
| 14 | GPIO2 | -9 | 5.5 |
| 15 | GPIO3 | -9 | 6.5 |
| 16 | GPIO4 | -9 | 7.5 |
| 17 | GPIO5 | -7.5 | 9 |
| 18 | GPIO6 | -6.5 | 9 |
| 19 | GPIO7 | -5.5 | 9 |
| 20 | GPIO8 | -4.5 | 9 |
| 21 | GND | -3.5 | 9 |
| 22 | GPIO9 | -2.5 | 9 |
| 23 | GPIO10 | -1.5 | 9 |
| 24 | GPIO11 | -0.5 | 9 |
| 25 | GPIO12 | 0.5 | 9 |
| 26 | GPIO13 | 1.5 | 9 |
| 27 | GPIO14 | 2.5 | 9 |
| 28 | GPIO15 | 3.5 | 9 |
| 29 | GPIO16 | 4.5 | 9 |
| 30 | GND | 5.5 | 9 |
| 31 | GPIO17 | 6.5 | 9 |
| 32 | GPIO18 | 7.5 | 9 |
| 33 | GPIO19 | 9 | 7.5 |
| 34 | GPIO20 | 9 | 6.5 |
| 35 | GPIO21 | 9 | 5.5 |
| 36 | GPIO22 | 9 | 4.5 |
| 37 | GPIO23 | 9 | 3.5 |
| 38 | GPIO24 | 9 | 2.5 |
| 39 | GND | 9 | 1.5 |
| 40 | GPIO25 | 9 | 0.5 |
| 41 | GPIO26 | 9 | -0.5 |
| 42 | GPIO27 | 9 | -1.5 |
| 43 | GPIO28 | 9 | -2.5 |
| 44 | GPIO29 | 9 | -3.5 |
| 45 | GPIO30 | 9 | -4.5 |
| 46 | GPIO31 | 9 | -5.5 |
| 47 | GPIO32 | 9 | -6.5 |
| 48 | GND | 9 | -7.5 |
| 49 | GPIO33 | 7.5 | -9 |
| 50 | GPIO34 | 6.5 | -9 |
| 51 | GPIO35 | 5.5 | -9 |
| 52 | GPIO36 | 4.5 | -9 |
| 53 | GPIO37 | 3.5 | -9 |
| 54 | GPIO38 | 2.5 | -9 |
| 55 | GPIO39 | 1.5 | -9 |
| 56 | GND | 0.5 | -9 |
| 57 | GPIO40 | -0.5 | -9 |
| 58 | GPIO41 | -1.5 | -9 |
| 59 | GPIO42 | -2.5 | -9 |
| 60 | GPIO43 | -3.5 | -9 |
| 61 | GPIO44 | -4.5 | -9 |
| 62 | GPIO45 | -5.5 | -9 |
| 63 | GPIO46 | -6.5 | -9 |
| 64 | GPIO47 | -7.5 | -9 |
