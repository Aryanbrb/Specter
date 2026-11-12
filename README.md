# Specter

Specter is a compact, solder-down system-on-module built around the Raspberry Pi RP2350B. It is designed for carrier boards that need the MCU, flash, PSRAM, clock, and core power supply in one assembly. Specter uses its own 64-contact inset LGA with a provisional 26 × 16.7 mm outline.

## Hardware

- 16 MB Winbond W25Q128JVPIQ QSPI flash and 8 MB AP Memory APS6404L-3SQR-ZR PSRAM share the QSPI bus. GPIO0 selects the PSRAM.
- A 12 MHz crystal provides the clock. USB, SWD, RUN, and BOOTSEL signals are intended for programming and recovery from the carrier.
- The default assembly takes 5 V through an AP2112K regulator. Fit R7 for this variant. A carrier with regulated 3.3 V uses R8 instead. Populate exactly one link.
- GPIO1 through GPIO47 are labeled in the schematic. The draft [carrier pinout](LGA-Pinout.md) assigns all 47 to module lands.

## Design status

The schematic and prototype BOM are in development. The A4 interface symbol and mating footprints are available for placement trials. The underside contacts use four inset, two-row groups with 0.8 mm square lands at 1.5 mm pitch. The new outline reduces board area by 8.8% while retaining all component placements; earlier carrier footprints must be replaced with A4. Routing, assembly and hardware verification are pending.

## Project files

Open [the KiCad project](RP2350%20SoM.kicad_pro) in KiCad 10 to inspect the [schematic](RP2350%20SoM.kicad_sch). Keep the project footprint table and [local footprint library](SoM.pretty/) together so KiCad can resolve the core regulator inductor.

The [BOM and prototype budget](Memory-BOM.md) document component selections, assembly options, and estimated costs for ten modules.

Keep the [project 3D models](3dmodels/README.md) alongside the PCB for the RP2350B and inductor. Install KiCad 10's standard 3D model libraries for the remaining components.

## Open hardware

Specter is preparing its first hardware revision for OSHWA certification. The original hardware is licensed under CERN-OHL-W-2.0 and the original documentation under CC BY 4.0. See the [licensing scope and third-party notices](LICENSING.md) and the [Rev A release checklist](OPEN-HARDWARE.md). Certification is pending a completed release and application.
