# Requirements

Draft. Numbers marked TBD are to be confirmed against the Jetson Orin NX/Nano Series Product Design Guide and part datasheets.

Priority: **M** = must have for Rev A, **S** = should have, **C** = could have.

## Module

| ID | Requirement | Priority |
| --- | --- | --- |
| MOD-01 | Supports Jetson Orin NX 16 GB via 260-pin SO-DIMM connector | M |
| MOD-02 | Also compatible with Orin NX 8 GB and Orin Nano modules | S |
| MOD-03 | Boots from on-board M.2 Key M NVMe | M |

## Power

| ID | Requirement | Priority |
| --- | --- | --- |
| PWR-01 | Input range covers 2S–6S LiPo (TBD: ~6–26 V) | M |
| PWR-02 | Reverse-polarity protection on main input | M |
| PWR-03 | Transient / surge protection for motor regen and hot-plug | M |
| PWR-04 | Hold-up to ride through input sag of TBD ms without reset | S |
| PWR-05 | Power-on and reset sequencing per design guide | M |
| PWR-06 | Input voltage and current monitoring readable by Jetson and supervisor MCU | S |
| PWR-07 | Switched 5 V rail for external peripherals (TBD A) | S |

## Cameras

| ID | Requirement | Priority |
| --- | --- | --- |
| CAM-01 | CSI connector pinout and I2C/GPIO mapping identical to NVIDIA dev kit (P3768) for at least one port | M |
| CAM-02 | At least 2 camera ports, target 4 | M |
| CAM-03 | Shared hardware frame-sync line to all cameras | M |
| CAM-04 | Camera sync line also routed to IMU / timestamp input | S |

## Robot I/O

| ID | Requirement | Priority |
| --- | --- | --- |
| IO-01 | CAN-FD transceiver with locking connector and switchable termination | M |
| IO-02 | At least 2 UARTs on locking connectors (flight controller, motor MCU) | M |
| IO-03 | On-board IMU on SPI or I2C, mounted near camera connectors | M |
| IO-04 | Gigabit Ethernet | M |
| IO-05 | At least 1 USB 3 port | M |
| IO-06 | Spare I2C, SPI and GPIO on a header | S |
| IO-07 | All external connectors locking (JST-GH or equivalent) | M |

## Supervisor MCU

| ID | Requirement | Priority |
| --- | --- | --- |
| SUP-01 | Controls Jetson power enable and reset | M |
| SUP-02 | Hardware watchdog for the Jetson | S |
| SUP-03 | Can force recovery mode for remote reflashing | S |
| SUP-04 | Link to Jetson (UART or I2C) for status and commands | M |

## Mechanical / thermal

| ID | Requirement | Priority |
| --- | --- | --- |
| MECH-01 | Board outline TBD, smaller than dev kit carrier | M |
| MECH-02 | Mounting compatible with a conduction-cooled thermal plate | S |
| MECH-03 | 6-layer stackup with controlled impedance from chosen fab | M |

## Software / BSP

| ID | Requirement | Priority |
| --- | --- | --- |
| BSP-01 | Runs stock JetPack with a minimal, documented device-tree / pinmux patch | M |
| BSP-02 | BSP patch published in this repo | M |
| BSP-03 | Stock Arducam / Raspberry Pi camera drivers work on dev-kit-compatible port | M |
