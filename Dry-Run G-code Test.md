# Dry-Run G-code Test

Power & Control System – V1

## Purpose

Validate coordinated motion without cutting.
This is the final logic and motion verification step.

## Preconditions

- All axes calibrated
- Soft limits enabled
- Spindle control verified
- No tool installed

## Test File Characteristics

The dry-run program should include:

- X, Y, and Z motion
- Direction reversals
- Rapid and feed moves
- Safe Z clearance

No spindle cutting load.

## Execution Steps

1. Home the machine
2. Load dry-run G-code
3. Enable single-block mode if available
4. Run program at reduced feed override
5. Observe full execution

## Observations to Make

- Axis coordination
- No unexpected pauses
- No limit alarms
- No loss of position
- Correct Z clearances

## Failure Handling

If an issue occurs:

- Stop immediately
- Identify root cause
- Correct configuration
- Restart from homing

## Status

Dry-run G-code test complete for V1.
