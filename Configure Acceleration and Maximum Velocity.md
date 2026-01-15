# Configure Acceleration and Maximum Velocity

Power & Control System – V1

## Purpose

Acceleration and velocity settings define machine performance and reliability.
Overly aggressive values cause missed steps and mechanical stress.

## Preconditions

- Steps-per-unit calibration complete
- Motors and drivers tuned
- No axis binding
- Machine fully assembled

## Initial Conservative Settings

Use these as safe starting points.

### Velocity

- X axis: Low to moderate
- A axis: Same as X
- Y axis: Same as X
- Z axis: Significantly lower

Example approach:

- Start at 25 percent of expected maximum
- Increase incrementally

### Acceleration

Acceleration has greater impact than top speed.

- X and A: Moderate
- Y: Moderate
- Z: Low

Start low.
Increase only after stable testing.

## Configuration Steps

1. Enter System Settings
2. Open Axis Settings
3. For each axis:
   - Set maximum velocity
   - Set acceleration
4. Save settings

## Testing Procedure

1. Jog each axis at increasing speeds
2. Listen for harsh noise or stalling
3. Perform rapid direction reversals
4. Observe for missed steps

If any issue occurs:

- Reduce acceleration first
- Reduce velocity second

## Locking Values

Once stable:

- Record final values
- Apply identical values to X and A
- Do not exceed tested limits

## Status

Acceleration and velocity configured for V1.
