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
