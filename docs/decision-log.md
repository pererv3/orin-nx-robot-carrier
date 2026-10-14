# Decision log

One entry per design decision: what was decided, why, and what was rejected. Newest at the bottom.

## D-001: Target module is Jetson Orin NX 16 GB

- **Date:** 2026-10-14
- **Decision:** Design around the Orin NX 16 GB module, keeping Orin Nano compatibility where it costs little.
- **Why:** Module already on hand; NX and Nano share the 260-pin SO-DIMM form factor and the P3768 reference carrier.

## D-002: Robot-brain board, not a general dev board

- **Date:** 2026-10-14
- **Decision:** Optimize for mobile robots: battery input, multi-camera with hardware sync, CAN-FD, IMU, locking connectors.
- **Why:** Clear gap in existing carriers; strongest fit for robotics hardware roles; uses CAN/EV background.

<!-- Template
## D-NNN: Title

- **Date:**
- **Decision:**
- **Why:**
- **Rejected:**
-->
