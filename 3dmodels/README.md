# Project 3D models

These STEP models were extracted without geometry changes from the embedded
models in Raspberry Pi's RP2350B Minimal reference board, revision R4-S1,
archive RP-010329-CA-1, retrieved 2026-11-10.

| File | Component |
| --- | --- |
| `rpi_rp2350b.step` | U1, Raspberry Pi RP2350B |
| `abracon_aota-b201610s3r3-101-t.step` | L1, Abracon AOTA-B201610S3R3-101-T |

Source: [Raspberry Pi RP2350 reference downloads](https://pip.raspberrypi.com/categories/1214-rp2350).
The archive's MIT licence and disclaimer are preserved in
[LICENSE-Raspberry-Pi.txt](LICENSE-Raspberry-Pi.txt).

Both models use millimetres, unit scale and zero offset. U1 uses zero additional
rotation. L1 uses 180 degrees around Z because Dolivo's pad 1 is VREG_LX and
pad 2 is VCORE, opposite the terminal numbering in Raspberry Pi's reference
footprint. The model and silkscreen dot indicate the VCORE end, matching the
reference's electrical orientation. The model geometry itself is unchanged.
The PCB links to them through `${KIPRJMOD}/3dmodels/`, so keep this directory
alongside the project. The L1 library footprint includes the same model link.
Other component models use the standard KiCad 10 3D library. J1 is the module's
underside copper land pattern and does not require a separate component body.

These models support visualization; use manufacturer drawings and physical
measurements for final mechanical fit verification.
