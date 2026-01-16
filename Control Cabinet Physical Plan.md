# Control Cabinet Physical Plan

Power & Control System – V1

## Purpose

Define a clean, low-noise, serviceable cabinet layout.
This plan prioritizes EMI control, airflow, and maintenance access.

## Cabinet Zoning

Divide the cabinet into vertical zones.

### Zone 1: High Voltage AC

- Main disconnect
- Circuit breakers
- EMI filter (if used)

Keep wiring short and isolated.

### Zone 2: VFD Zone

- Huanyang VFD
- VFD line filter (optional)
- Spindle output exit point

Rules:

- Physical separation from logic
- Dedicated wire routing
- Shielded spindle cable exit

### Zone 3: Power Conversion

- Stepper PSU
- Control PSU
- DC distribution terminals

Mount centrally for short DC runs.

### Zone 4: Motion and Logic

- DDCSV4.1 controller
- DMA860S drivers
- Signal terminal blocks

Rules:

- DIN rail mounting
- Clear airflow
- Easy access for tuning

### Zone 5: Grounding and I/O

- Ground bar
- Shield termination points
- Limit and sensor terminals

Single-point grounding only.

## Electrical Separation and Grounding

The stepper DC supply and the control DC supply must remain electrically isolated.
DC negative rails must not be tied together.

Both power supply chassis must be bonded to the cabinet ground bar, and all
protective earth connections must converge at a single grounding point. This
approach minimizes noise coupling and limits fault propagation.

## AC Power Entry and Distribution

### Main Disconnect Placement

AC power entry, disconnects, and branch protection shall be implemented in
accordance with [AC Power Supply Specification](<AAC Power Supply Specification.md>).

This device establishes the primary safety boundary for the cabinet.

### Branch Breaker Layout

Branch protection devices shall be DIN-rail mounted and located downstream of the
main disconnect. Branch breakers should be arranged in a logical top-to-bottom or
left-to-right order corresponding to load type:

1. VFD branch
2. Stepper DC power supply branch
3. Control and logic power supply branch

Each breaker shall be clearly labeled to indicate the load it serves.

### Separation of Noisy and Quiet Loads

The cabinet layout shall physically separate high-noise and low-noise components.

- Noisy components:
  - VFD
  - VFD branch breaker
  - Spindle power wiring

- Quiet components:
  - Control PSU
  - DDCSV4.1 controller
  - Signal terminal blocks

Noisy and quiet wiring shall be routed in separate wire ducts where practicable.
Crossings, if unavoidable, shall be made at right angles to minimize coupling.

This separation reduces EMI, improves signal integrity, and increases overall
system reliability.

## Airflow Plan

- Bottom or side intake
- Top or opposite-side exhaust
- Airflow across drivers and PSUs
- VFD heatsink unobstructed

Use filtered intake.

## Serviceability Rules

- No wire crossing zones unnecessarily
- Label both ends of every cable
- Leave service loops
- Keep DIP switches accessible

## Status

Cabinet physical plan drafted for V1.
