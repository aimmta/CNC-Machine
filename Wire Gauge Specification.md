# Wire Gauge Specification

Power & Control System – V1

## Conventions used

* Copper conductors, 75 °C minimum insulation (THHN/MTW inside cabinet)
* Stranded wire for anything that moves or lands on terminals
* Shielded cable where noted
* All grounds bonded to a single cabinet ground bar

---

## 1. AC mains and protection

| Circuit                              | Voltage     | Current (typical) | Wire gauge | Notes                           |
| ------------------------------------ | ----------- | ----------------: | ---------: | ------------------------------- |
| Main AC feed (to cabinet disconnect) | 240 VAC     |             ≤30 A | **10 AWG** | Headroom, mechanical robustness |
| Disconnect → VFD input               | 240 VAC     |          ~10–12 A | **12 AWG** | Dedicated run                   |
| Disconnect → Stepper PSU             | 240 VAC     |           ~8–10 A | **14 AWG** | Separate branch                 |
| Disconnect → Control PSU             | 120/240 VAC |              <2 A | **16 AWG** | Light load                      |
| Safety ground (PE)                   | —           |                 — | **10 AWG** | Cabinet ground bond             |

---

## 2. VFD to spindle (noise-critical)

| Circuit             | Voltage            | Current | Wire gauge | Cable type                   |
| ------------------- | ------------------ | ------: | ---------: | ---------------------------- |
| VFD → spindle U/V/W | 0–240 VAC, 3-phase |  ~6–9 A | **14 AWG** | **Shielded VFD motor cable** |
| Spindle ground      | —                  |       — | **14 AWG** | Bond to spindle body         |

Rules:

* Shield grounded at **VFD end only**
* Route alone, no parallel signal wiring

---

## 3. Stepper DC power distribution

| Circuit                              | Voltage   |         Current |    Wire gauge | Notes                          |
| ------------------------------------ | --------- | --------------: | ------------: | ------------------------------ |
| Stepper PSU DC output → distribution | 60–72 VDC |      up to 20 A |    **10 AWG** | Short run to terminal block    |
| Distribution → each DMA860S          | 60–72 VDC | ≤6 A per driver |    **14 AWG** | Star topology, not daisy-chain |
| DC negative return                   | 60–72 VDC |               — | **10–14 AWG** | Match positive size            |

---

## 4. Stepper drivers to motors

| Circuit                 | Voltage   | Phase current | Wire gauge | Cable type                  |
| ----------------------- | --------- | ------------: | ---------: | --------------------------- |
| DMA860S → NEMA 34 motor | Pulsed DC |           6 A | **14 AWG** | **Shielded, twisted pairs** |

Notes:

* One cable per motor
* Shield grounded at cabinet end only
* Keep away from VFD output cable

---

## 5. Control power (24 VDC)

| Circuit                           | Voltage |   Current | Wire gauge | Notes              |
| --------------------------------- | ------- | --------: | ---------: | ------------------ |
| Control PSU output → distribution | 24 VDC  |      ≤5 A | **16 AWG** | Short internal run |
| Distribution → DDCSV4.1           | 24 VDC  |      <1 A | **18 AWG** | Clean logic feed   |
| Distribution → relays, MPG, fans  | 24 VDC  | <1 A each | **18 AWG** | Label circuits     |

---

## 6. Step/Dir and enable signals (DDCSV → DMA860S)

| Signal type         | Voltage      | Current | Wire gauge | Cable type              |
| ------------------- | ------------ | ------: | ---------: | ----------------------- |
| Step / Dir / Enable | 5–24 V logic |      mA | **22 AWG** | Shielded, twisted pairs |

Notes:

* Differential wiring preferred where available
* Shield grounded at controller end only

---

## 7. Limits, homes, E-stop

| Circuit                | Voltage | Current |                      Wire gauge | Cable type              |
| ---------------------- | ------- | ------: | ------------------------------: | ----------------------- |
| Limit & home switches  | 24 VDC  |      mA |                      **22 AWG** | Shielded if long runs   |
| E-stop loop (control)  | 24 VDC  |      mA |                   **18–20 AWG** | Robust insulation       |
| E-stop power interrupt | AC      |  varies | **Same as interrupted circuit** | Through contactor/relay |

---

## 8. Analog spindle speed control (DDCSV → VFD)

| Circuit       | Voltage  | Current | Wire gauge | Cable type                |
| ------------- | -------- | ------: | ---------: | ------------------------- |
| 0–10 V analog | 0–10 VDC |      mA | **22 AWG** | **Shielded twisted pair** |

Rules:

* Shield grounded at DDCSV end only
* Never share conduit with VFD output

---

## 9. Grounding and shields

| Purpose                    |                Wire gauge |
| -------------------------- | ------------------------: |
| Cabinet ground bar → earth |                **10 AWG** |
| PSU frames → ground bar    |             **12–14 AWG** |
| Driver frames → ground bar |                **14 AWG** |
| Cable shields → ground bar | **Drain wire, 18–22 AWG** |
