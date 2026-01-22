# Steps-Per-Unit Calibration

Power & Control System – V1

## Preconditions

Before calibrating, confirm:

* DDCSV4.1 axis and dual-X homing are working
* X and A home independently and square the gantry
* DMA860S drivers are set identically on X and A
* All axes jog smoothly at low speed
* No binding across full travel

Do not calibrate until the machine can home reliably.

## What steps-per-unit actually is

Steps-per-unit expresses the relationship between:

* Electrical pulses from the controller
* Mechanical motion of the axis

The formula is:

```sql
Steps per unit =
( Motor steps per revolution × Microsteps × Gear ratio )
/ Linear travel per revolution
```

## Electrical constants (locked)

* Motor full steps per revolution: 200
* Microsteps: 10
* Steps per motor revolution: 2000

These values apply to **all axes**, including X and A.

## Mechanical inputs you must supply

You need one of the following per axis:

### Ballscrew-driven axis

* Ballscrew pitch in mm per revolution
  Example: 10 mm per revolution

### Rack-and-pinion axis

* Pinion circumference in mm
  Example: 20-tooth, module 1.5 gear

If an axis uses reduction:

* Include gear or belt ratio

Each axis can differ mechanically.

## Initial calculation (example)

### Example: 10 mm ballscrew

```java
Steps per mm = 2000 / 10
Steps per mm = 200
```

Enter **200** as the initial value.

### Example: rack-and-pinion

```java
Pinion circumference = π × pitch diameter
Steps per mm = 2000 / circumference
```

Use this value only as a starting point.

## Enter initial values in DDCSV4.1

1. Go to **System Settings**
2. Open **Axis Settings**
3. For each axis:

   * Enter the calculated steps-per-unit
   * Ensure X and A are identical
4. Save settings

Do not attempt fine tuning yet.

## Measurement setup

You need a reliable reference.

Recommended tools:

* Dial indicator with magnetic base
  or
* Steel rule with fine graduations

Measurement rules:

* Measure along the axis line of travel
* Do not measure diagonally
* Use at least **100 mm of travel** if possible

Longer moves reduce error.

## Calibration move procedure

For each axis independently:

1. Home the machine
2. Zero the axis DRO
3. Command a move of a known distance
   Example: 100.000 mm
4. Measure actual movement

Record:

* Commanded distance
* Actual distance

## Correction calculation

Use this exact formula:

```java
New steps per unit =
( Current steps per unit × Commanded distance )
/ Actual distance
```

### Example

* Current value: 200
* Commanded: 100.000 mm
* Actual: 99.600 mm

```java
New value = (200 × 100.000) / 99.600
New value ≈ 200.80
```

Enter the new value.

## Apply and repeat

1. Enter corrected value
2. Save settings
3. Re-home
4. Repeat the same move
5. Re-measure

Stop when:

* Error is less than 0.05 mm over 100 mm
* Or better, depending on your goals

## Dual-X axis rule

* Calibrate **X only**
* Copy the final X value to **A**
* Never calibrate A independently

If the gantry does not square:

* Fix homing switch alignment
* Do not alter steps-per-unit to compensate

## Z-axis special notes

Z axes often have:

* Higher friction
* Gravity load

Calibrate Z with:

* Tool holder installed
* Normal operating load

If Z error differs up vs down:

* That is mechanical, not steps-per-unit
* Do not compensate electrically

## Verify full-travel accuracy

After fine calibration:

1. Move the axis close to maximum travel
2. Measure cumulative error
3. Confirm no binding or missed steps

If error grows with distance:

* Check mechanical alignment
* Check couplings
* Check rack mounting

## Lock the values

Once satisfied:

* Record final steps-per-unit values
* Store them as **Power & Control System – V1 calibration**
* Photograph or document DDCSV screens

These values should not change unless mechanics change.

## What this completes

At this point, V1 has:

* Electrically correct motion
* Mechanically squared gantry
* Dimensionally accurate axes
* A known-good calibration baseline
