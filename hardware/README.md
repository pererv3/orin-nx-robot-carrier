# Hardware

Altium Designer project for the carrier board.

- `libraries/` — schematic symbols, footprints and 3D models used by this project
- `outputs/` — fabrication and assembly outputs per revision (`rev-a/`, `rev-b/`, …). Tag each release in git.

Altium files are binary, so git cannot diff or merge them. Commit often with clear messages, and avoid two people editing the same sheet at once.
