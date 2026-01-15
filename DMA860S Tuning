# DMA860S Tuning

Power & Control System – V1

## Scope

This section covers:

* Output current settings for your 6 A NEMA 34 motors
* Microstep selection appropriate for machine mass and controller pulse rate
* Idle current reduction
* Direction, enable, and signal integrity notes
* A safe initial steps-per-unit baseline

---

## Motor facts (locked)

* Motor type: NEMA 34
* Rated current: 6.0 A per phase
* Rated torque: 12 Nm
* Application: Large CNC router, dual-X gantry
* Controller: DDCSV4.1 (500 kHz capable)

---

## 1. Output current setting

Set the DMA860S **peak current to 6.0 A**.

Do not overshoot the motor rating. These motors already have ample torque, and excess current only adds heat.

### Typical DMA860S current table mapping

DMA860S labels vary slightly, but most follow this pattern.

| Peak current (A) | Switch setting       |
| ---------------- | -------------------- |
| 5.6 A            | Near but under rated |
| **6.0 A**        | **Recommended**      |
| 6.8 A            | Not recommended      |
| 7.2 A            | Do not use           |

If the driver only offers 5.6 A and 6.8 A options, choose **5.6 A** for initial testing. You can increase later after thermal checks.

### Thermal check rule

After 20 to 30 minutes of holding torque:

* Driver case should be warm, not hot
* Motor case should be touchable for several seconds

If either is too hot to touch, reduce current one step.

---

## 2. Idle current reduction

Enable idle current reduction at **50 percent**.

This reduces heat when the axis is stationary without sacrificing holding accuracy during motion.

If the DMA860S offers multiple idle options:

* Choose 50 percent or equivalent
* Avoid aggressive reductions below 30 percent on Z

---

## 3. Microstep selection

### Design goals

* Smooth motion
* Reasonable top speed
* No unnecessary pulse load on the controller
* Identical behavior on X and A axes

### Recommended starting microstep

10 microsteps per full step

This is a very common and well-balanced choice for large NEMA 34 systems.

### Why not higher

* Above 10 to 16 microsteps, torque per microstep drops
* Mechanical stiffness dominates accuracy, not microstep count
* Higher microsteps increase pulse rate with no real gain

---

## 4. Steps per revolution and steps per unit

### Motor basics

* Full steps per revolution: 200
* Microsteps: 10

```java
Steps per motor revolution = 200 × 10 = 2000
```

### Leadscrew or rack conversion

You will calculate steps per unit later based on:

* Ballscrew pitch or rack travel per revolution
* Gear reduction, if any

For now, lock **2000 steps per motor revolution** as the electrical constant.

---

## 5. Signal polarity and enable behavior

### Direction signal

* Default direction polarity is acceptable
* Reverse direction in DDCSV if needed
* Do not swap motor phase wiring to fix direction unless necessary

### Enable signal

* Use ENA on all axes
* Active-low enable is typical
* Confirm behavior by disabling the axis in DDCSV and verifying free rotation

---

## 6. Pulse timing considerations

The DMA860S is tolerant, but best practice is:

* Step pulse width: ≥ 5 microseconds
* Direction setup time: ≥ 5 microseconds before step

The DDCSV4.1 defaults are usually safe here. No special tuning required initially.

---

## 7. Axis-specific notes

### X and A axes (dual gantry)

* Identical driver settings
* Identical microstep and current
* Mechanical squaring handled in homing, not in driver tuning

### Y axis

* Same settings as X and A
* No special handling required

### Z axis

* Same current and microstep initially
* If Z runs warmer, reduce idle current only, not peak

---

## 8. Initial verification checklist

Before commanding motion:

* All four drivers set identically
* DIP switches documented or photographed
* Motors rotate smoothly by hand when disabled
* No driver fault LEDs active

During first motion:

* Jog at low speed only
* Listen for harsh resonance or growling
* Confirm correct direction per axis
* Confirm X and A move together
