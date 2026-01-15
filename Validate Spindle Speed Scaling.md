# Validate Spindle Speed Scaling

Power & Control System – V1

## Purpose

Ensure commanded RPM matches actual spindle speed.
This validates 0–10 V scaling between DDCSV and Huanyang VFD.

---

## Preconditions

- VFD parameters set
- Spindle cooling operational
- Analog control enabled
- No cutting load applied

---

## Test Setup

Tools:

- Optical tachometer or RPM probe
- Eye protection
- Clear spindle area

---

## Validation Procedure

1. Power on VFD and controller
2. Command spindle on at low RPM
   - Example: S6000
3. Measure actual spindle speed
4. Record commanded vs actual RPM

Repeat at:

- 25 percent
- 50 percent
- 75 percent
- 100 percent of max RPM

---

## Adjustment

If error exists:

- Adjust DDCSV spindle scaling
- Or adjust VFD analog gain
- Never adjust both simultaneously

Repeat measurement until error is acceptable.

---

## Acceptance Criteria

- Linear response across range
- Error less than 2 percent preferred
- Smooth ramping without surging

---

## Status

Spindle speed scaling validated for V1.
