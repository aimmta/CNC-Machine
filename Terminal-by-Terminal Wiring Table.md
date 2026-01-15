# Terminal-by-Terminal Wiring Table

Power & Control System – V1

---

## 1. Power distribution (AC side)

### 1.1 Main AC → devices

| From        | Terminal | To              | Terminal | Notes   |
| ----------- | -------- | --------------- | -------- | ------- |
| AC mains L1 | —        | Main disconnect | L1       | 240 VAC |
| AC mains L2 | —        | Main disconnect | L2       | 240 VAC |
| Earth       | —        | Ground bar      | GND      | 10 AWG  |

---

### 1.2 Main disconnect → VFD

| From          | Terminal | To  | Terminal | Notes          |
| ------------- | -------- | --- | -------- | -------------- |
| Disconnect L1 | —        | VFD | R        | 12 AWG         |
| Disconnect L2 | —        | VFD | T        | 12 AWG         |
| Ground bar    | GND        | VFD | GND        | Chassis ground |

(Do not connect S for single-phase unless your VFD manual explicitly instructs it.)

---

### 1.3 Main disconnect → power supplies

| From          | Terminal | To          | Terminal | Notes       |
| ------------- | -------- | ----------- | -------- | ----------- |
| Disconnect L1 | —        | Stepper PSU | L        | 14 AWG      |
| Disconnect L2 | —        | Stepper PSU | N        | 14 AWG      |
| Disconnect L1 | —        | Control PSU | L        | 16 AWG      |
| Disconnect L2 | —        | Control PSU | N        | 16 AWG      |
| Ground bar    | GND        | All PSUs    | GND        | Bond frames |

---

## 2. Stepper DC power

### 2.1 Stepper PSU → DC distribution

| From        | Terminal | To                | Terminal | Notes  |
| ----------- | -------- | ----------------- | -------- | ------ |
| Stepper PSU | V+       | DC terminal block | +        | 10 AWG |
| Stepper PSU | V−       | DC terminal block | −        | 10 AWG |

---

### 2.2 DC distribution → DMA860S (repeat for each driver)

| From       | Terminal | To      | Terminal | Notes        |
| ---------- | -------- | ------- | -------- | ------------ |
| DC block + | +        | DMA860S | V+       | 14 AWG       |
| DC block − | −        | DMA860S | V−       | 14 AWG       |
| Ground bar | GND        | DMA860S | GND        | Frame ground |

---

## 3. DMA860S → stepper motors

(Repeat per motor)

| Driver terminal | Motor lead | Notes              |
| --------------- | ---------- | ------------------ |
| A+              | Phase A+   | Twisted pair       |
| A−              | Phase A−   |                    |
| B+              | Phase B+   | Twisted pair       |
| B−              | Phase B−   |                    |
| Shield drain    | —          | To ground bar only |

---

## 4. DDCSV4.1 → DMA860S (motion signals)

### Axis assignment

* X → X-Left motor
* A → X-Right motor
* Y → Y motor
* Z → Z motor

### 4.1 Step / Direction / Enable (per axis)

| DDCSV terminal | To driver | Driver terminal | Notes                    |
| -------------- | --------- | --------------- | ------------------------ |
| XPUL+          | X driver  | PUL+            | Shielded                 |
| XPUL−          | X driver  | PUL−            |                          |
| XDIR+          | X driver  | DIR+            |                          |
| XDIR−          | X driver  | DIR−            |                          |
| XENA+          | X driver  | ENA+            | Optional but recommended |
| XENA−          | X driver  | ENA−            |                          |

(Repeat the same mapping for A, Y, Z using APUL, YPUL, ZPUL, etc.)

---

## 5. DDCSV4.1 power (logic)

| From              | Terminal | To    | Terminal | Notes            |
| ----------------- | -------- | ----- | -------- | ---------------- |
| Control PSU +24 V | +        | DDCSV | +24 V    | 18 AWG           |
| Control PSU 0 V   | −        | DDCSV | GND      | Common reference |

---

## 6. Limit and home switches

(Recommended: normally closed switches)

### 6.1 Home switches

| Switch       | From         | To           | Notes            |
| ------------ | ------------ | ------------ | ---------------- |
| X-Left home  | DDCSV X-HOME | Switch → GND | Independent      |
| X-Right home | DDCSV A-HOME | Switch → GND | Enables squaring |
| Y home       | DDCSV Y-HOME | Switch → GND |                  |
| Z home       | DDCSV Z-HOME | Switch → GND |                  |

---

### 6.2 Limit switches (if separate)

| Axis     | From          | To                 | Notes     |
| -------- | ------------- | ------------------ | --------- |
| X limits | DDCSV X-LIMIT | Switch chain → GND | Series NC |
| Y limits | DDCSV Y-LIMIT | Switch chain → GND |           |
| Z limits | DDCSV Z-LIMIT | Switch chain → GND |           |

---

## 7. E-stop wiring

### 7.1 E-stop logic input

| From   | Terminal  | To                | Terminal | Notes                |
| ------ | --------- | ----------------- | -------- | -------------------- |
| DDCSV  | E-STOP IN | E-stop NC contact | —        | 24 V logic           |
| E-stop | —         | DDCSV GND         | —        | Controller awareness |

---

### 7.2 E-stop power interruption

| Circuit interrupted | Method             | Notes         |
| ------------------- | ------------------ | ------------- |
| Stepper PSU AC      | Contactor or relay | Motion stops  |
| VFD Run             | Relay opens FOR    | Spindle stops |

(Do not rely on software stop alone.)

---

## 8. DDCSV4.1 → Huanyang VFD (control)

### 8.1 Run / Stop

| From            | Terminal | To  | Terminal | Notes          |
| --------------- | -------- | --- | -------- | -------------- |
| DDCSV relay COM | —        | VFD | DCM      | Digital common |
| DDCSV relay NO  | —        | VFD | FOR      | Run forward    |

---

### 8.2 Speed control (0–10 V)

| From             | Terminal | To  | Terminal | Notes             |
| ---------------- | -------- | --- | -------- | ----------------- |
| DDCSV analog out | 0–10 V   | VFD | AVI      | Shielded pair     |
| DDCSV analog GND | GND      | VFD | ACM      | Shared analog ref |

---

## 9. VFD → spindle

| From       | Terminal | To      | Terminal | Notes     |
| ---------- | -------- | ------- | -------- | --------- |
| VFD        | U        | Spindle | Phase 1  | 14 AWG    |
| VFD        | V        | Spindle | Phase 2  |           |
| VFD        | W        | Spindle | Phase 3  |           |
| Ground bar | GND        | Spindle | GND        | Bond body |

---

## 10. Grounding summary

| Item          | To                            |
| ------------- | ----------------------------- |
| Cabinet       | Earth                         |
| VFD frame     | Ground bar                    |
| PSU frames    | Ground bar                    |
| Driver frames | Ground bar                    |
| Cable shields | Ground bar (cabinet end only) |
