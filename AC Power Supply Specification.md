# AC Power Supply Specification

Power & Control System – V1

This document defines the AC power requirements, protection strategy, and internal
distribution architecture for Power & Control System – V1.

All downstream DC power specifications and wiring decisions depend on the
requirements defined here.

## Overview

Power & Control System – V1 operates from a single-phase 240 VAC supply and
contains three primary AC loads:

- VFD and spindle system
- Stepper motor DC power supply
- Control and logic power supply

All AC power enters the cabinet through a single main disconnect and is distributed
to individual loads through branch protection devices mounted on DIN rail.

## Incoming Service

- Nominal voltage: 240 VAC
- Acceptable range: 200–240 VAC
- Phase: single-phase
- Frequency: 50/60 Hz
- Recommended service rating: 30 A
- Neutral conductor: not required unless future 120 VAC loads are added

A 30 A service provides sufficient capacity for continuous simultaneous axis
loading, spindle operation, and future expansion while maintaining acceptable
thermal and inrush margins.

## Main Disconnect

A single main disconnect shall be installed at the cabinet power entry.

Requirements:

- Two-pole disconnect switching both hot conductors
- Minimum rating: 30 A
- Lockable in the OFF position
- Clearly labeled and readily accessible

The main disconnect provides the primary safety boundary for the cabinet and shall
interrupt all AC power entering the system.

## Branch Protection

Downstream of the main disconnect, AC power shall be divided into three protected
branches using DIN-rail mounted circuit breakers or fused disconnect devices.

Residential breaker panels are not appropriate for use inside a control cabinet.

### Branch assignments and ratings

VFD branch:

- Two-pole breaker
- 15 A rating
- C or D trip curve to tolerate inrush current
- Dedicated branch

Stepper DC power supply branch:

- Two-pole breaker
- 15 A rating
- C trip curve

Control and logic power supply branch:

- Two-pole breaker
- 5 A rating
- B or C trip curve

Each branch breaker provides both overcurrent protection and a means of isolating
individual subsystems for service and troubleshooting.

## AC Wiring

Recommended conductor sizes:

- Incoming service to main disconnect: 10 AWG copper
- Branch wiring to VFD: 12 AWG copper
- Branch wiring to stepper DC power supply: 12 AWG copper
- Branch wiring to control PSU: 16 AWG copper (14 AWG acceptable)

All protective earth conductors shall terminate at a single cabinet ground bar.
Ground conductors shall not be daisy-chained.

## Noise Considerations

The VFD and its associated branch wiring are the primary sources of electrical
noise in the system.

AC routing and cabinet layout shall ensure:

- Physical separation between VFD power wiring and control wiring
- Short, direct AC runs to the VFD
- Dedicated branch protection for the VFD

Noise mitigation is addressed further in the Control Cabinet Physical Plan.
