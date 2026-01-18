# DC Power Supply Specification

Power & Control System – V1

This document specifies the DC power supplies required for reliable operation of
Power & Control System – V1 under continuous, simultaneous multi-axis loading.

## Overview

The system uses two electrically separate DC power domains:

- High-voltage DC for stepper motor power
- Low-voltage DC for control, logic, and I/O

These supplies must remain electrically isolated from each other while sharing a
common protective earth reference.

## Stepper Motor DC Power Supply

### Purpose

The stepper motor DC power supply provides the DC bus power for all DMA860S stepper
motor drivers. It must support continuous simultaneous axis loading without
excessive voltage sag or thermal stress.

### Electrical Requirements

- Nominal voltage: 68 VDC
- Acceptable operating range: 60–72 VDC
- Topology: single shared DC bus
- Output type: regulated switching DC supply
- Ripple tolerance: minimal ripple preferred; transient sag must be avoided

### Load Characteristics

The system uses four stepper motors:

- Quantity: 4
- Type: NEMA 34
- Rated phase current: 6.0 A
- Drive method: bipolar, microstepped
- Expected duty cycle: continuous multi-axis motion

Stepper motor drivers do not draw phase current directly from the DC supply.
Instead, they draw average electrical power based on motor load, acceleration,
and driver efficiency.

### Numerical Sizing

A conservative per-motor electrical power estimate under sustained load is
approximately 200–250 W. This accounts for copper losses, driver inefficiency,
and continuous torque demand.

For four motors:

- Base electrical demand: approximately 1000 W

Additional margin is required to accommodate:

- Simultaneous acceleration events
- DC bus capacitance recharge
- Thermal headroom and long-term reliability

Recommended margin: 30–50 percent.

### Final Recommended Rating

- Minimum acceptable continuous rating: 1200 W
- Recommended continuous rating: 1500 W
- Voltage rating: 60–72 VDC, with 68 VDC nominal preferred

### Quantity

A single shared high-voltage DC power supply is recommended. Multiple supplies
provide no functional advantage and introduce unnecessary grounding and fault
complexity.

## Control and Logic DC Power Supply

### Purpose

The control and logic DC power supply provides power for:

- DDCSV4.1 motion controller
- Limit and home switches (if powered)
- Relays or contactors with 24 VDC coils
- Indicator lights and auxiliary logic

### Electrical Requirements

- Output voltage: 24 VDC regulated
- Output type: industrial-grade switching power supply
- Electrical noise: low ripple preferred
- Isolation: galvanically isolated from the stepper DC power supply

### Load Estimate

Typical control system loads are modest and include controller logic, I/O
circuits, and auxiliary devices. Estimated continuous current draw is less than
3 A.

Recommended supply rating:

- Minimum: 24 VDC at 5 A
- Preferred: 24 VDC at 10 A for headroom and future expansion
- Control and logic power supply: Mean Well NDR-240-24, 24 VDC, 10 A, DIN-rail mounted.

## Acceptance Criteria

The DC power system is considered valid when:

- The stepper DC bus remains within the specified voltage range during sustained
  simultaneous axis motion
- No stepper driver faults occur during heavy multi-axis operation
- Power supplies remain within thermal limits
- Control logic remains stable during aggressive motion events

## Status

DC power supply requirements are defined and approved for Power & Control System – V1.
