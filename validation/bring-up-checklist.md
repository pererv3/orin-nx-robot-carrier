# Rev A bring-up checklist

Work top to bottom. Do not insert the Jetson module until the power section passes.

## 1. Bare board (no module)

- [ ] Visual inspection: solder bridges, polarity, missing parts
- [ ] Input to GND resistance (no short)
- [ ] Each rail to GND resistance (no short)
- [ ] Reverse-polarity test at low current limit
- [ ] Power up from current-limited bench supply at minimum input voltage
- [ ] Measure every rail: voltage, ripple
- [ ] Check power-on sequencing on scope against design guide
- [ ] Sweep input from 2S to 6S range; rails stay in regulation
- [ ] Supervisor MCU programs and toggles power enable

## 2. With module

- [ ] Module powers on, debug UART shows boot log
- [ ] Enter recovery mode, flash JetPack from host
- [ ] Boots from NVMe
- [ ] Ethernet link and throughput
- [ ] USB 3 enumeration at SuperSpeed
- [ ] CAN-FD loopback and external node
- [ ] UARTs loopback
- [ ] IMU responds, data sane
- [ ] Camera on dev-kit-compatible port with stock driver
- [ ] All camera ports streaming simultaneously
- [ ] Hardware frame sync verified on scope
- [ ] Supervisor watchdog resets a hung Jetson
- [ ] Supervisor-triggered recovery mode

## 3. Stress

- [ ] Full GPU load, thermal throttling behavior with target thermal solution
- [ ] Simulated battery sag and motor regen transients
- [ ] Vibration / connector retention
