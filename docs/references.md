# Reference documents

Download from the [Jetson Download Center](https://developer.nvidia.com/embedded/downloads) (NVIDIA account required). These are NVIDIA-licensed, so keep them in `reference/` locally; that folder is git-ignored.

| Document | Use |
| --- | --- |
| Jetson Orin NX Series and Orin Nano Series Product Design Guide | Main spec: power sequencing, interface routing rules, impedance targets |
| Jetson Orin NX module datasheet | Electrical limits, pin functions |
| Jetson Orin NX/Nano pinmux spreadsheet | Pin assignments; generates device-tree files |
| P3768 dev kit carrier reference design files (A04) | Reference schematic and layout |
| Jetson Orin NX/Nano thermal design guide | Thermal plate design |
| Module 3D STEP model | Mechanical fit in Altium |

## Notes

- The P3768 files are OrCAD/Concept schematics and an Allegro layout, not Altium. Use the free Cadence PCB viewer to inspect stackup and routing.
- NVIDIA recommends following the **Concept** schematic PDF, which shows the actual stuffing options; the OrCAD "base version" has none. Apply `P3768_A04_BOM.xls` on top of it.
