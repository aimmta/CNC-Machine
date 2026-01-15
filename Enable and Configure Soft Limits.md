# Enable and Configure Soft Limits

Power & Control System – V1

## Purpose

Soft limits prevent axis motion beyond the usable travel range.
They are a software safety layer and must never replace hard limits or E-stop behavior.

## Preconditions

- Machine homes reliably on all axes
- Steps-per-unit calibration is complete
- Dual-X homing and squaring are correct
- No binding across full axis travel

## Procedure

1. Power on the system
2. Home all axes
3. Navigate to:
   - System Settings
   - Axis Settings
   - Soft Limits

## Configure Travel Limits

For each axis, enter the usable travel range.

Example values only:

- X axis
  - Minimum: 0.0
  - Maximum: measured usable X travel
- Y axis
  - Minimum: 0.0
  - Maximum: measured usable Y travel
- Z axis
  - Minimum: safe lower limit
  - Maximum: safe upper limit

Rules:

- X and A must have identical limits
- Do not include crash margin in usable travel
- Leave mechanical margin at both ends

## Enable Soft Limits

- Soft limits: Enabled
- Overtravel action: Stop motion
- Alarm or warning: Enabled if supported

Save settings.

## Verification

1. Home the machine
2. Jog toward each soft limit at low speed
3. Confirm motion stops before mechanical end
4. Confirm no false triggering during normal motion

## Notes

- Soft limits only function after homing
- Loss of position invalidates soft limits
- Mechanical changes require revalidation

## Status

Soft limits enabled and validated for V1.
