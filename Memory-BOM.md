# RP2350B module — MCU and memory BOM, rev A draft

Prototype BOM for the RP2350B, memories, power, recovery and clock circuits. All discrete resistors and capacitors use imperial 0402 (metric 1005).

| Site | Manufacturer | MPN | Distributor order number / buying link | Selection and limits |
|---|---|---|---|---|
| U1 | Raspberry Pi | SC1510-A4 | [2648-SC1510-A4CT-ND](https://www.digikey.in/en/products/detail/raspberry-pi/SC1510-A4/26241109) | RP2350B A4; QFN-80 exposed pad, 10 × 10 mm, 0.4 mm pitch; 3.3 V I/O target, separate core rail. |
| U2 | Winbond | W25Q128JVPIQ | [DigiKey](https://www.digikey.com/en/products/detail/winbond-electronics/W25Q128JVPIQ/6819668) | 16 MB, WSON-8, 6 × 5 mm, 1.27 mm pitch, 2.7–3.6 V, −40 to +85 °C. Center pad may float. |
| U3 | AP Memory | APS6404L-3SQR-ZR | [Mouser](https://www.mouser.com/ProductDetail/AP-Memory/APS6404L-3SQR-ZR) | 8 MB, USON-8, 3 × 2 mm, 0.5 mm pitch, 2.7–3.6 V, −25 to +85 °C. |
| C1, C2 | Yageo | CC0402KRX7R7BB104 | [DigiKey](https://www.digikey.com/en/products?keywords=CC0402KRX7R7BB104) | Two × 100 nF ±10%, X7R, 16 V, 0402 inch. Local bypass at each memory. |
| R1 | Yageo | RC0402FR-0710KL | [DigiKey](https://www.digikey.com/en/products?keywords=RC0402FR-0710KL) | 10 kΩ ±1%, 0.063 W, 0402 inch; pull-up on secondary chip select. |

Use 3.3 V QSPI I/O; CS0 boots flash and GPIO0 selects PSRAM. Start at 75 MHz serial clock from a 150 MHz system clock; qualify each flash density for boot, JEDEC ID, erase/write, address boundaries and correct firmware flash size. Validate PSRAM initialization, select/deselect timing and mixed flash/PSRAM traffic. The PSRAM and flash have different physical footprints. Confirm price and availability for the build quantity.

References: [Raspberry Pi reference wiring, §3.2](https://datasheets.raspberrypi.com/rp2350/hardware-design-with-rp2350.pdf), [AP Memory timing and package](https://www.apmemory.com/en/downloadFiles/032411212009597427), [RP2350B application using this PSRAM](https://resources.4dsystems.com.au/datasheets/rp2350/gen4-rp2350-mcu/).
## Module power, recovery and clock additions

Populate exactly one 0402 selector link. The default 5 V assembly fits R7 and omits R8. A regulated 3.3 V carrier uses R8 fitted and R7 omitted. U4 supplies the module only. At 200 mA the LDO dissipates approximately 0.34 W. Validate temperature at maximum sustained load and carrier ambient. Keep the core regulator input capacitor, inductor, output capacitor and PGND loop beside U1. Place each bypass capacitor beside its associated supply pin. Verify effective ceramic capacitance at operating bias and the inductor dot orientation before PCB release.

| References | Value | Manufacturer part number | DigiKey |
|---|---|---|---|
| U4 | 3.3 V LDO | Diodes AP2112K-3.3TRG1 | [Cut tape](https://www.digikey.com/en/products/detail/diodes-incorporated/AP2112K-3-3TRG1/4470746) |
| L1 | 3.3 µH shielded | Abracon AOTA-B201610S3R3-101-T | [Cut tape](https://www.digikey.com/en/products/detail/abracon-llc/AOTA-B201610S3R3-101-T/25621527) |
| C3–C7 | 4.7 µF, 10 V, X5R | Murata GRM155R61A475MEAAD | [MPN lookup](https://www.digikey.com/en/products?keywords=GRM155R61A475MEAAD) |
| C8–C21 | 100 nF | Same as C1 and C2 | CC0402KRX7R7BB104 |
| R2 | 33 Ω | Yageo RC0402FR-0733RL | [MPN lookup](https://www.digikey.com/en/products?keywords=RC0402FR-0733RL) |
| R3, R6 | 1 kΩ | Yageo RC0402FR-071KL | [MPN lookup](https://www.digikey.com/en/products?keywords=RC0402FR-071KL) |
| R4, R5 | 27 Ω | Yageo RC0402FR-0727RL | [MPN lookup](https://www.digikey.com/en/products?keywords=RC0402FR-0727RL) |
| R7 or R8 | 0 Ω, fit one per board | Yageo RC0402JR-070RL | [DigiKey lookup](https://www.digikey.in/en/products?keywords=RC0402JR-070RL) |
| Y1 | 12 MHz, 10 pF load | Abracon ABM8-272-T3 | [Crystal](https://www.digikey.com/en/products/detail/abracon-llc/ABM8-272-T3/22472366) |
| C22, C23 | 15 pF, C0G | Yageo CC0402JRNPO9BN150 | [MPN lookup](https://www.digikey.com/en/products?keywords=CC0402JRNPO9BN150) |

Carrier buttons momentarily short BOOTSEL_N and RUN to GND. For USB recovery, hold BOOTSEL_N low, pulse RUN low, then release BOOTSEL_N after reset sampling. Route USB_DP and USB_DM to the carrier USB connector. SWCLK and SWDIO provide independent debug access. GPIO1 through GPIO47 are carrier-facing signal names. GPIO40 through GPIO47 also provide ADC0 through ADC7. Physical LGA pad numbers remain open.

Reference circuits: [RP2350B Minimal, Appendix B](https://datasheets.raspberrypi.com/rp2350/hardware-design-with-rp2350.pdf) and [Waveshare RP2350 board recovery circuit](https://files.waveshare.com/wiki/RP2350-Touch-LCD-1.28/RP2350-Touch-LCD-1.28.pdf).
## Ten-prototype budget (INR, 1 November 2026)

Ten populated sets of the current schematic, exact fit quantities, no attrition. DigiKey India pricing except Mouser India for PSRAM. PCB fabrication, assembly and delivery are separate.

| Item | Buy quantity | INR for ten boards |
|---|---:|---:|
| [RP2350B SC1510-A4](https://www.digikey.in/en/products/detail/raspberry-pi/SC1510-A4/26241109), using the single-piece rate | 10 | 1,098.80 |
| [W25Q128JVPIQ](https://www.digikey.in/en/products/detail/winbond-electronics/W25Q128JVPIQ/6819668) | 10 | 3,504.77 |
| [APS6404L-3SQR-ZR](https://www.mouser.in/en/ProductDetail/AP-Memory/APS6404L-3SQR-ZR) | 10 | 2,255.00 |
| [AP2112K-3.3TRG1](https://www.digikey.in/en/products/detail/diodes-incorporated/AP2112K-3-3TRG1/4470746) | 10 | 181.66 |
| [AOTA-B201610S3R3-101-T](https://www.digikey.in/en/products/detail/abracon-llc/AOTA-B201610S3R3-101-T/25621527) | 10 | 165.30 |
| [ABM8-272-T3](https://www.digikey.in/en/products/detail/abracon-llc/ABM8-272-T3/22472366) | 10 | 574.26 |
| **Distributor-priced subtotal** | | **7,779.79** |
| 0402 resistor and capacitor allowance (unquoted) | 70 R, 230 C | 400–800 |
| **Estimated fitted parts** | | **8,180–8,580** |
| JLCPCB bare-board planning allowance (unquoted, 30 × 15 mm, four-layer FR-4, ENIG, standard through vias) | 10 | 1,500–3,000 |
| **Planning total, parts and bare PCBs** | | **9,680–11,580** |

Passive quantities: 160 × 100 nF, 50 × 4.7 µF, 20 × 15 pF, 10 × 10 kΩ, 10 × 33 Ω, 20 × 1 kΩ and 20 × 27 Ω and 10 × 0 Ω. Spares, tax/import charges, freight from three vendors, stencil, placement and reflow are additional. Obtain a [JLCPCB fabrication quote](https://jlcpcb.com/quote) after layout confirms the stack-up, vias, panel and finish.
