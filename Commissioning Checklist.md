# Commissioning Checklist

Power & Control System – V1

This checklist defines when **V1 is complete and safe to operate**.
All items should be verified in order. Do not skip steps.

## Phase 0: Administrative and Baseline

* [ ] Power & Control System labeled as **V1**
* [ ] Wiring diagrams match actual build
* [ ] All PSU voltages labeled
* [ ] Cabinet ground bonded to earth
* [ ] Emergency stop physically accessible

## Phase 1: Electrical Integrity

### Grounding and bonding

* [ ] Single ground bar installed
* [ ] VFD chassis bonded
* [ ] PSU frames bonded
* [ ] Stepper driver frames bonded
* [ ] Spindle body bonded
* [ ] Cable shields terminated at cabinet end only
* [ ] Stepper DC power supply installed per specification
* [ ] Control / logic DC power supply installed per specification

### Power integrity

* [ ] Main disconnect interrupts all AC
* [ ] AC branch protection verified against AC Power Supply Specification
* [ ] Stepper PSU AC feed fused
* [ ] Control PSU AC feed fused
* [ ] VFD on dedicated branch
* [ ] Control PSU stable at 24 VDC
* [ ] No unexpected heating under idle power

## Phase 2: Controller and Logic

### DDCSV4.1 basic operation

* [ ] Controller boots normally
* [ ] MPG recognized and functional
* [ ] Axis enable toggles correctly
* [ ] E-stop input recognized by controller

### Axis mapping

* [ ] X motor responds to X jog
* [ ] A motor responds to A jog
* [ ] X and A jog in same physical direction
* [ ] Y jog correct direction
* [ ] Z jog correct direction

## Phase 3: Homing and Squaring

* [ ] All home switches trigger reliably
* [ ] Z homes first
* [ ] X and A home independently
* [ ] Gantry squares during homing
* [ ] Y homes after gantry
* [ ] No switch overtravel or chatter

## Phase 4: Motion Calibration

### Driver configuration

* [ ] DMA860S current set correctly
* [ ] Microstep settings consistent across axes
* [ ] Idle current reduction enabled
* [ ] Drivers remain thermally stable

### Steps-per-unit

* [ ] Initial calculated values entered
* [ ] X calibrated and copied to A
* [ ] Y calibrated
* [ ] Z calibrated under load
* [ ] Error less than target tolerance

## Phase 5: Limits and Safety

* [ ] Soft limits enabled
* [ ] X and A soft limits identical
* [ ] Soft limits stop motion before mechanical ends
* [ ] Hard limits still functional
* [ ] E-stop cuts motion power
* [ ] E-stop stops spindle
* [ ] Stepper DC bus voltage verified under simultaneous axis motion

## Phase 6: Spindle Validation

* [ ] Cooling system operational
* [ ] VFD parameters verified
* [ ] Spindle runs from controller command
* [ ] 0–10 V scaling linear
* [ ] Commanded RPM matches measured RPM
* [ ] No abnormal noise or vibration

## Phase 7: Dry-Run Validation

* [ ] Dry-run G-code loads correctly
* [ ] No limit alarms during run
* [ ] Axis coordination correct
* [ ] Z clearance maintained
* [ ] No lost steps
* [ ] No unexpected pauses or resets

## Phase 8: V1 Acceptance

* [ ] DC power capacity validated for continuous multi-axis operation
* [ ] Cabinet closed and ventilated
* [ ] All wiring labeled
* [ ] Configuration values recorded
* [ ] V1 declared complete

## Status

Power & Control System – V1 commissioned.
