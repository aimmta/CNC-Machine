# DDCSV4.1 Axis and Dual-X Homing Configuration

Power & Control System – V1

---

## 1. Axis role definition

You have four motors and four driver channels.

### Axis mapping (locked)

| Physical axis        | DDCSV axis | Notes       |
| -------------------- | ---------- | ----------- |
| X-Left gantry motor  | X          | Master      |
| X-Right gantry motor | A          | Slaved to X |
| Y axis motor         | Y          | Independent |
| Z axis motor         | Z          | Independent |

Do not attempt to electrically tie the two X motors together. Slaving is done in software.

---

## 2. Entering axis configuration mode

1. Power on the DDCSV4.1
2. From the main screen, enter:

   * **System Settings**
   * **Axis Settings**

All configuration below happens in this area.

---

## 3. Enable and assign axes

For each axis (X, A, Y, Z):

* Axis enabled: **Yes**
* Axis type: **Linear**
* Units: **mm** (recommended, even if you think in inches)

Confirm that **all four axes are enabled**.

---

## 4. Axis direction check (before homing)

This step prevents crashes.

For each axis:

1. Exit settings
2. Use jog mode at **very low speed**
3. Jog positive direction

If motion is reversed:

* Return to Axis Settings
* Invert direction for that axis
* Do not swap motor wires unless absolutely necessary

Repeat until:

* X jogs in expected machine +X
* A jogs in the same physical direction as X
* Y and Z jog correctly

---

## 5. Steps per unit configuration

This connects driver tuning to motion.

### Electrical constant (from DMA860S tuning)

* Steps per motor revolution: **2000**

### Enter preliminary values

In Axis Settings for X, A, Y, Z:

* Steps per unit: **TEMPORARY VALUE**

  * Use a safe placeholder such as **200 steps/mm**
  * Final calibration comes later

The critical rule here:

* **X and A must have identical steps-per-unit values**

---

## 6. Axis slaving configuration (dual-X)

Navigate to:

* **System Settings**
* **Axis Relation / Slave Settings**

Configure:

| Master axis | Slave axis |
| ----------- | ---------- |
| X           | A          |

Rules:

* Only A is slaved
* X remains the master
* Do not slave in reverse

Save settings.

---

## 7. Homing switch assignment

This is the heart of gantry squaring.

### Required switches (already wired)

* X-Left home switch
* X-Right home switch
* Y home switch
* Z home switch

### DDCSV home input mapping

In **I/O Settings**:

| Axis | Home input |
| ---- | ---------- |
| X    | X-HOME     |
| A    | A-HOME     |
| Y    | Y-HOME     |
| Z    | Z-HOME     |

Each switch must be independent.

---

## 8. Homing direction and order

Navigate to:

* **Homing Settings**

### Homing direction

Set per your machine geometry. Typical example:

| Axis | Direction |
| ---- | --------- |
| Z    | Positive  |
| X    | Negative  |
| A    | Negative  |
| Y    | Negative  |

Direction must move the axis **toward its home switch**.

---

### Homing order (recommended)

| Order | Axis    | Reason                  |
| ----- | ------- | ----------------------- |
| 1     | Z       | Get tool out of the way |
| 2     | X and A | Gantry squaring         |
| 3     | Y       | Table reference         |

If the DDCSV allows grouping:

* Home X and A together
* Ensure they stop independently on their own switches

---

## 9. Dual-X squaring behavior

During homing:

1. X and A move toward home
2. One side hits its switch first and stops
3. The other side continues until its switch triggers
4. Gantry is squared mechanically
5. X and A zeroed together

This only works if:

* Switches are wired independently
* X and A are not electrically tied
* Slaving is configured correctly

---

## 10. Homing speed and backoff

Recommended initial values:

* Homing speed: **Slow**
* Backoff distance: **2 to 5 mm**
* Second approach (if available): **Enabled, slow**

This improves repeatability and reduces switch stress.

---

## 11. Soft limits (enable later)

For initial testing:

* Soft limits: **Disabled**

After calibration:

* Enable soft limits
* Set travel ranges per axis
* X and A must match exactly

---

## 12. First homing test procedure

Perform this sequence exactly:

1. Power on control PSU only
2. Enable DDCSV
3. Enable stepper PSU
4. Jog each axis slightly away from home
5. Press **Home All**

Observe:

* Z homes first
* X and A home together and square
* Y homes last
* No axis stalls or overshoots

If any axis moves the wrong way:

* Abort immediately
* Fix direction setting
* Retry
