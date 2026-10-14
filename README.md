# Orin NX Robot Carrier

A compact carrier board for the NVIDIA Jetson Orin NX (16 GB) module, built to be the "brain" of a mobile robot or drone rather than a desk dev kit.

> **Status:** Concept / requirements. No schematic yet.

## Why

The Orin NX module is only a compute card. A carrier board turns its raw pins into power, connectors and interfaces. Existing carriers fall short for robots in a few recurring ways:

| Problem with existing carriers | What this board does instead |
| --- | --- |
| Cameras validated only on NVIDIA's dev kit; third-party carriers remap CSI lanes and I2C buses, so stock drivers break | Camera ports pin-compatible with the dev kit, plus more 4-lane ports |
| Vendor BSPs lag behind JetPack releases | Stay close to the NVIDIA reference design; publish a small, open device-tree patch |
| Expect a clean bench supply | Battery-hardened 2S–6S input: reverse polarity, transient/regen protection, brownout hold-up |
| Camera/IMU timestamps aligned in software | Hardware trigger shared by cameras and an on-board IMU |
| Desktop connectors, reflashing means opening the robot | Locking JST-GH connectors; supervisor MCU for power, watchdog and remote recovery |
| Fan coolers that don't fit sealed robot bodies | Outline and mounting designed for a conduction-cooled plate |

## Target feature set (draft)

- Jetson Orin NX / Orin Nano module (260-pin SO-DIMM)
- 2S–6S LiPo input (~6–26 V)
- 2–4 MIPI CSI-2 camera ports, dev-kit pin mapping, hardware frame sync
- CAN-FD transceiver
- IMU, rigidly referenced to camera connectors
- UARTs for flight controller / motor MCU
- M.2 Key M NVMe (boot drive)
- Gigabit Ethernet, USB 3
- Supervisor MCU: power sequencing, watchdog, recovery-mode control
- 6-layer, controlled-impedance stackup

Full requirements: [`docs/requirements.md`](docs/requirements.md)

## Repository layout

```
docs/          requirements, decision log, reference list
hardware/      Altium project, libraries, fab outputs
firmware/      supervisor MCU firmware
bsp/           pinmux, device tree, flashing configs for JetPack
validation/    bring-up checklist and test results
reference/     NVIDIA reference docs (local only, not committed — see docs/references.md)
```

## Roadmap

1. Requirements and block diagram
2. Power tree and interface selection
3. Schematic (Altium)
4. Stackup and impedance with chosen fab
5. Layout and design review
6. Rev A fabrication and bring-up
7. BSP: pinmux, device tree, JetPack flashing
8. Rev B fixes
