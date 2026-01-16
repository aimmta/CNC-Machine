# DIN-Rail Placement Plan

Power & Control System – V1

This is a **textual placement plan**, suitable for a sketch or CAD later.

## Rail 1: High-Voltage AC (Top or Left)

Order from incoming power:

1. Main disconnect
2. EMI line filter (optional)
3. Branch breakers or fuses
4. VFD input terminals

Rules:

* Short runs
* No signal wiring on this rail
* Clear finger-safe spacing

## Rail 2: Power Conversion (Center)

Left to right:

1. Stepper PSU
2. Control PSU
3. DC distribution terminals

Rules:

* Keep DC runs short
* Label voltage clearly
* Leave airflow clearance

## Rail 3: Motion and Control (Opposite Side)

Left to right:

1. DDCSV4.1 controller
2. DMA860S drivers (even spacing)
3. Signal terminal blocks

Rules:

* Signal wiring only
* No AC crossings
* DIP switches accessible

## Rail 4: Ground and I/O (Bottom)

1. Ground bar
2. Shield termination points
3. Limit and sensor terminals

Rules:

* Single-point ground
* Shields land here
* Easy inspection
