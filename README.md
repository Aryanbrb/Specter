# Specter

Specter is a compact, solder-down system-on-module built around the Raspberry Pi RP2350B. It is designed for carrier boards that need the MCU, flash, PSRAM, clock, and core power supply in one assembly. The mechanical target is the 30 × 15 mm SGET OSM Size-0 form factor.

## Hardware

- 16 MB Winbond W25Q128JVPIQ QSPI flash and 8 MB AP Memory APS6404L-3SQR-ZR PSRAM share the QSPI bus. GPIO0 selects the PSRAM.
- A 12 MHz crystal provides the clock. USB, SWD, RUN, and BOOTSEL signals are intended for programming and recovery from the carrier.
- The default assembly takes 5 V through an AP2112K regulator. Fit R7 for this variant. A carrier with regulated 3.3 V uses R8 instead. Populate exactly one link.
- GPIO1 through GPIO47 are labeled in the schematic. The final carrier pin assignments depend on the OSM contact map and routing study.

## Design status

The schematic and prototype BOM are in development. The LGA pinout, module and carrier footprints, placement, and routing are pending. OSM compatibility and hardware operation still require verification.

## Project files

Open [the KiCad project](RP2350%20SoM.kicad_pro) in KiCad 10 to inspect the [schematic](RP2350%20SoM.kicad_sch). Keep the project footprint table and [local footprint library](SoM.pretty/) together so KiCad can resolve the core regulator inductor.

The [BOM and prototype budget](Memory-BOM.md) document component selections, assembly options, and estimated costs for ten modules. The [OSM Design Guide](https://sget.org/wp-content/uploads/2024/11/OSM_DG_V1.1.pdf) provides the carrier design reference.
