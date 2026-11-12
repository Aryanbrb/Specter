# Dolivo LGA64 · Interface draft A4

The module outline is **26 × 16.7 mm** (434.2 mm²), an **8.8% area reduction** from the 28 × 17 mm A3 outline. This revision preserves the current positions, rotations, land patterns and nets of all 37 fitted/optional components. Only the board outline and underside interface geometry change. The earlier A3, A2 and 25 × 25 mm carrier footprints are mechanically incompatible with A4.

The 64 contacts sit in **four inset, two-row groups** underneath the component field. Each land is a **0.8 × 0.8 mm rounded square**, with **1.5 mm row and column pitch within each group**, and a 0.05 mm solder-mask expansion on each side. Pad centres are paired outer-row first, then inner-row, progressing counterclockwise in the component-side top view. West has 13 contacts, south 19, east 16 and north 16; the incomplete west and south pairs are intentional. The groups are positioned for the existing circuit regions, rather than forced onto one global matrix. All A3 pad numbers and signal assignments are retained.

The central underside is left without LGA lands to allow ground stitching and routing, including beneath the MCU exposed pad. LGA copper is at least 1.2 mm inside the board edge. The project retains its **0.508 mm / 20 mil minimum copper-to-edge rule**; the closest existing component copper is R7 at 0.5175 mm from the north edge. The west and east limits are set by R3 and Y1. U2's south courtyard and silkscreen limit further height reduction. A smaller rectangle would require moving components or reducing these margins.

Coordinates below use the new module centre as origin, looking through the module from the component side. Positive X points right and positive Y points down. Both footprints use this same top-view frame; the physical underside view is mirrored. Place the module interface footprint unflipped: copper is already on B.Cu, mask on B.Mask, and there are no module paste openings. The carrier footprint uses F.Cu/F.Mask/F.Paste, with provisional 1:1 paste apertures. For carrier schematics use the library symbol, override its footprint to SoM:Dolivo_LGA64_Carrier and enable its BOM entry. F.Fab shows the 26 × 16.7 mm outline; the carrier courtyard adds 0.25 mm per side. J1's PCB origin is now (100.9, 91.85) mm; component coordinates have not moved.

GPIO and control signals use the module's 3.3 V I/O domain. GPIO40–47 double as ADC0–7. GPIO0 selects onboard PSRAM. Connect all nine grounds. Populate only R7 for the 5 V build or only R8 for the regulated 3.3 V build. RUN and BOOTSEL_N are active low. USB_N and USB_P remain adjacent lands and retain their differential-pair names.

Power, BOOTSEL, USB and GPIO1–3 use the west group; GPIO4–20 the south group; GPIO21–32, SWD and RUN the east group; GPIO33–47 the north group. The schematic and its wiring are unchanged.

J1, its 64 board pads and its outline graphics are locked in the PCB editor. The Edge.Cuts board outline is also locked. Unlock deliberately in item properties before making mechanical changes.

## Routing and assembly status

This is a custom PCB module interface inspired by depopulated LGA arrays, not a qualified molded SiP package or an industry-standard pinout. KiCad reports no geometric DRC violations at this placement stage; all 160 existing unconnected items remain to be routed. Both mating footprints have matching pad positions and dimensions.

Plan ordinary dog-bone escapes into the spaces between lands. Reserve their drill locations against the components on the opposite side before routing; top-to-bottom pad overlap alone is not a conflict, but a through via can be. Keep open vias out of solderable LGA lands, or explicitly specify filled and capped via-in-pad fabrication. The open centre does not yet contain routed ground copper or stitching vias.

The inset joints need an assembly and inspection plan, including stencil thickness, solder volume, module flatness, reflow and X-ray access. The south flash is close to the outline, so plan routed panel rails/tabs clear of components; do not assume V-scoring. Fabrication clearances alone do not qualify assembly yield. Routing, carrier stencil and assembly validation are still required before ordering.

Reference principles: [NXP LGA assembly guidelines, AN2265](https://www.nxp.com/docs/en/application-note/AN2265.pdf) discuss depopulated arrays, land/mask design, via solder wicking and inspection. [JLCPCB capabilities](https://jlcpcb.com/capabilities/pcb-capabilities) provide the fabrication and via-process limits. The specific A4 land dimensions are a provisional Dolivo design choice, not a footprint endorsed by those sources.

## Pad coordinates

| Pad | Module net | X (mm) | Y (mm) |
|---:|---|---:|---:|
| 1 | GND | -11.4 | -4.85 |
| 2 | VCC_IN_5V | -9.9 | -4.85 |
| 3 | VCC_IN_3V3 | -11.4 | -3.35 |
| 4 | GND | -9.9 | -3.35 |
| 5 | BOOTSEL_N | -11.4 | -1.85 |
| 6 | GND | -9.9 | -1.85 |
| 7 | USB_N | -11.4 | -0.35 |
| 8 | USB_P | -9.9 | -0.35 |
| 9 | GND | -11.4 | 1.15 |
| 10 | GPIO1 | -9.9 | 1.15 |
| 11 | GPIO2 | -11.4 | 2.65 |
| 12 | GPIO3 | -9.9 | 2.65 |
| 13 | GND | -11.4 | 4.15 |
| 14 | GPIO4 | -5.4 | 6.6 |
| 15 | GPIO5 | -5.4 | 5.1 |
| 16 | GPIO6 | -3.9 | 6.6 |
| 17 | GPIO7 | -3.9 | 5.1 |
| 18 | GPIO8 | -2.4 | 6.6 |
| 19 | GND | -2.4 | 5.1 |
| 20 | GPIO9 | -0.9 | 6.6 |
| 21 | GPIO10 | -0.9 | 5.1 |
| 22 | GPIO11 | 0.6 | 6.6 |
| 23 | GPIO12 | 0.6 | 5.1 |
| 24 | GPIO13 | 2.1 | 6.6 |
| 25 | GPIO14 | 2.1 | 5.1 |
| 26 | GPIO15 | 3.6 | 6.6 |
| 27 | GPIO16 | 3.6 | 5.1 |
| 28 | GND | 5.1 | 6.6 |
| 29 | GPIO17 | 5.1 | 5.1 |
| 30 | GPIO18 | 6.6 | 6.6 |
| 31 | GPIO19 | 6.6 | 5.1 |
| 32 | GPIO20 | 8.1 | 6.6 |
| 33 | GPIO21 | 11.1 | 4.65 |
| 34 | GPIO22 | 9.6 | 4.65 |
| 35 | GPIO23 | 11.1 | 3.15 |
| 36 | GPIO24 | 9.6 | 3.15 |
| 37 | GPIO25 | 11.1 | 1.65 |
| 38 | GPIO26 | 9.6 | 1.65 |
| 39 | GPIO27 | 11.1 | 0.15 |
| 40 | GND | 9.6 | 0.15 |
| 41 | SWCLK | 11.1 | -1.35 |
| 42 | SWDIO | 9.6 | -1.35 |
| 43 | RUN | 11.1 | -2.85 |
| 44 | GPIO28 | 9.6 | -2.85 |
| 45 | GPIO29 | 11.1 | -4.35 |
| 46 | GPIO30 | 9.6 | -4.35 |
| 47 | GPIO31 | 11.1 | -5.85 |
| 48 | GPIO32 | 9.6 | -5.85 |
| 49 | GPIO33 | 7.1 | -6.5 |
| 50 | GPIO34 | 7.1 | -5 |
| 51 | GPIO35 | 5.6 | -6.5 |
| 52 | GPIO36 | 5.6 | -5 |
| 53 | GPIO37 | 4.1 | -6.5 |
| 54 | GPIO38 | 4.1 | -5 |
| 55 | GPIO39 | 2.6 | -6.5 |
| 56 | GND | 2.6 | -5 |
| 57 | GPIO40 | 1.1 | -6.5 |
| 58 | GPIO41 | 1.1 | -5 |
| 59 | GPIO42 | -0.4 | -6.5 |
| 60 | GPIO43 | -0.4 | -5 |
| 61 | GPIO44 | -1.9 | -6.5 |
| 62 | GPIO45 | -1.9 | -5 |
| 63 | GPIO46 | -3.4 | -6.5 |
| 64 | GPIO47 | -3.4 | -5 |
