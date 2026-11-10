# Specter LGA64 · Rev A placement draft

The trial outline is 25 × 25 mm. Four rows of 16 contacts on 1 mm pitch leave the center available for routing. Land centers sit 1 mm inside the nominal edge. Each copper land measures 1.0 mm radially by 0.6 mm tangentially. Pin 1 is near the northwest corner on the west edge.

Coordinates below use the module center as origin, looking through the module from the component side. Positive X points right and positive Y points down. Both footprints use this same top-view coordinate frame. Place the module interface footprint unflipped on the module board: its copper is already on B.Cu and it has no paste openings. Place the carrier footprint on F.Cu; paste is on the carrier. For carrier schematics use the library symbol, override its footprint to SoM:Specter_LGA64_Carrier and enable its BOM entry. The F.Fab square is a placement outline. The module PCB has a matching closed 25 × 25 mm perimeter on Edge.Cuts.

GPIO and control signals use the module’s 3.3 V I/O domain. GPIO40–47 double as ADC0–7. GPIO0 selects the onboard PSRAM. Connect all grounds. Populate only R7 for the 5 V build or only R8 for the regulated 3.3 V build. RUN and BOOTSEL_N are active low. Validate escape routing, thermal return paths, land and stencil dimensions, alignment and solder joints before ordering.

| Pad | Module net | X (mm) | Y (mm) |
|---:|---|---:|---:|
| 1 | GND | -11.5 | -7.5 |
| 2 | VCC_IN_5V | -11.5 | -6.5 |
| 3 | GND | -11.5 | -5.5 |
| 4 | VCC_IN_3V3 | -11.5 | -4.5 |
| 5 | RUN | -11.5 | -3.5 |
| 6 | BOOTSEL_N | -11.5 | -2.5 |
| 7 | SWCLK | -11.5 | -1.5 |
| 8 | SWDIO | -11.5 | -0.5 |
| 9 | GND | -11.5 | 0.5 |
| 10 | USB_N | -11.5 | 1.5 |
| 11 | USB_P | -11.5 | 2.5 |
| 12 | GND | -11.5 | 3.5 |
| 13 | GPIO1 | -11.5 | 4.5 |
| 14 | GPIO2 | -11.5 | 5.5 |
| 15 | GPIO3 | -11.5 | 6.5 |
| 16 | GPIO4 | -11.5 | 7.5 |
| 17 | GPIO5 | -7.5 | 11.5 |
| 18 | GPIO6 | -6.5 | 11.5 |
| 19 | GPIO7 | -5.5 | 11.5 |
| 20 | GPIO8 | -4.5 | 11.5 |
| 21 | GND | -3.5 | 11.5 |
| 22 | GPIO9 | -2.5 | 11.5 |
| 23 | GPIO10 | -1.5 | 11.5 |
| 24 | GPIO11 | -0.5 | 11.5 |
| 25 | GPIO12 | 0.5 | 11.5 |
| 26 | GPIO13 | 1.5 | 11.5 |
| 27 | GPIO14 | 2.5 | 11.5 |
| 28 | GPIO15 | 3.5 | 11.5 |
| 29 | GPIO16 | 4.5 | 11.5 |
| 30 | GND | 5.5 | 11.5 |
| 31 | GPIO17 | 6.5 | 11.5 |
| 32 | GPIO18 | 7.5 | 11.5 |
| 33 | GPIO19 | 11.5 | 7.5 |
| 34 | GPIO20 | 11.5 | 6.5 |
| 35 | GPIO21 | 11.5 | 5.5 |
| 36 | GPIO22 | 11.5 | 4.5 |
| 37 | GPIO23 | 11.5 | 3.5 |
| 38 | GPIO24 | 11.5 | 2.5 |
| 39 | GND | 11.5 | 1.5 |
| 40 | GPIO25 | 11.5 | 0.5 |
| 41 | GPIO26 | 11.5 | -0.5 |
| 42 | GPIO27 | 11.5 | -1.5 |
| 43 | GPIO28 | 11.5 | -2.5 |
| 44 | GPIO29 | 11.5 | -3.5 |
| 45 | GPIO30 | 11.5 | -4.5 |
| 46 | GPIO31 | 11.5 | -5.5 |
| 47 | GPIO32 | 11.5 | -6.5 |
| 48 | GND | 11.5 | -7.5 |
| 49 | GPIO33 | 7.5 | -11.5 |
| 50 | GPIO34 | 6.5 | -11.5 |
| 51 | GPIO35 | 5.5 | -11.5 |
| 52 | GPIO36 | 4.5 | -11.5 |
| 53 | GPIO37 | 3.5 | -11.5 |
| 54 | GPIO38 | 2.5 | -11.5 |
| 55 | GPIO39 | 1.5 | -11.5 |
| 56 | GND | 0.5 | -11.5 |
| 57 | GPIO40 | -0.5 | -11.5 |
| 58 | GPIO41 | -1.5 | -11.5 |
| 59 | GPIO42 | -2.5 | -11.5 |
| 60 | GPIO43 | -3.5 | -11.5 |
| 61 | GPIO44 | -4.5 | -11.5 |
| 62 | GPIO45 | -5.5 | -11.5 |
| 63 | GPIO46 | -6.5 | -11.5 |
| 64 | GPIO47 | -7.5 | -11.5 |
