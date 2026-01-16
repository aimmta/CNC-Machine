# Glossary of Terms
CNC Machine Documentation

This glossary defines terms as they are used throughout this documentation set.
Where a term has multiple meanings in other contexts, the definition here is
authoritative for this project.

## AC Power Supply

The incoming alternating-current electrical service supplying the control cabinet.
In Power & Control System – V1, this is a single-phase 240 VAC supply.

## Branch Protection

Overcurrent protection devices installed downstream of the main disconnect.
Implemented using DIN-rail mounted circuit breakers or fused disconnects.
Each branch protects a single major load.

## Control Cabinet

The enclosure housing all electrical components, including power supplies,
controllers, drivers, breakers, grounding, and wiring.

## Control / Logic Power Supply

A regulated 24 VDC power supply providing power to the DDCSV4.1 controller,
I/O circuits, relays, and auxiliary logic. Electrically isolated from the stepper
DC power supply.

## DC Bus

The high-voltage DC rail supplying power to the stepper motor drivers.
Nominally 68 VDC in Power & Control System – V1.

## Dual-X (Gantry Drive)

A configuration in which two motors independently drive opposite sides of the
gantry along the X axis. Squaring is achieved through independent homing rather
than mechanical coupling.

## Electrical Homing

The process by which axes move to reference switches to establish a repeatable
machine coordinate system. Homing establishes repeatability, not geometric
squareness.

## Ground (Protective Earth)

The safety earth connection bonding all conductive enclosures, power supply
chassis, and cable shields to a single grounding point. Not the same as DC return.

## Main Disconnect

A lockable, two-pole disconnect switch that removes all AC power from the cabinet.
Serves as the primary safety isolation device.

## Mechanical Alignment

The process of physically establishing rail coplanarity, gantry squareness, and
Z-axis orthogonality. Mechanical alignment defines machine geometry and must be
completed before electrical motion calibration.

## Motion Controller

The DDCSV4.1 standalone CNC controller responsible for generating step and
direction signals, managing homing, limits, and motion coordination.

## Soft Limits

Software-defined travel limits enforced by the controller after homing.
Soft limits prevent motion beyond defined axis ranges but do not replace
hard limits or E-stop behavior.

## Stepper DC Power Supply

The high-voltage DC power supply feeding the stepper motor drivers.
Sized based on average electrical power demand, not motor phase current.

## Stepper Motor Driver

The DMA860S digital stepper driver, which converts DC bus power into controlled
phase currents for the stepper motors.

## VFD (Variable Frequency Drive)

The drive that converts AC power into variable-frequency, variable-voltage output
to control spindle speed and torque.

## X Axis

The long-table travel axis, running along the length of the machine.
Follows industry-standard CNC axis convention.

## Y Axis

The gantry crossbeam travel axis, running perpendicular to the X axis.
Follows industry-standard CNC axis convention.

## Z Axis

The vertical axis controlling spindle up-and-down motion.
