# Build-Order Dependency Chart

Power & Control System – V1

Each section **depends on all sections above it**.
If work stops and resumes later, restart at the highest unchecked section.

---

## Administrative Baseline

* System named and labeled as Power & Control System – V1
* Component selection frozen
* Wiring, configuration, and commissioning documents created

---

## Mechanical Foundation

* CNC table assembled
* Frame leveled relative to gravity
* X, Y, and Z axes mechanically square
* Linear motion smooth across full travel
* Mechanical alignment declared valid

This section is a hard gate for electrical motion testing.

---

## Electrical Infrastructure

* Cabinet installed
* Ground bar installed and bonded to earth
* Main disconnect installed
* Branch protection installed
* AC integrity verified with no loads

---

## Power Conversion and Distribution

* Control PSU installed and verified
* Stepper PSU installed and verified
* DC distribution terminals installed
* Voltage domains labeled

---

## Motion and Logic Hardware

* DDCSV4.1 installed
* DMA860S drivers installed
* DIN-rail terminals installed
* Device frames bonded to ground
* Controller boots normally

---

## Signal Wiring

* Step, direction, and enable signals wired
* Driver-to-motor wiring complete
* Limit and home switches wired
* E-stop logic wired
* Spindle control signals wired

---

## Static Electrical Verification

* Continuity checks complete
* Ground isolation verified
* Shield termination verified
* Power-up with motors disabled
* No faults or overheating

---

## Motion Enablement

* Drivers enabled
* Individual axis jogging verified
* Axis directions verified
* Dual-X coherence verified
* Motion disabled and inspected

---

## Homing and Squaring

* Homing directions configured
* Home switches verified
* Dual-X homing enabled
* Gantry squaring verified
* Homing repeatability confirmed

---

## Motion Calibration

* Driver current and microsteps set
* Initial steps-per-unit entered
* X axis calibrated
* X calibration copied to A
* Y axis calibrated
* Z axis calibrated under load

---

## Safety Envelope

* Soft limits enabled
* Soft limits verified
* Hard limits verified
* E-stop removes motion power
* E-stop stops spindle

---

## Spindle Validation

* Cooling system verified
* VFD terminal control verified
* 0–10 V scaling validated
* Commanded RPM matches actual RPM
* Thermal behavior observed

---

## Integrated Testing

* Dry-run G-code loaded
* Full dry-run executed
* Axis coordination verified
* No lost steps
* No limit faults

---

## Commissioning Complete

* Configuration values recorded
* Cabinet closed and ventilated
* Wiring labeled
* V1 declared commissioned

---
