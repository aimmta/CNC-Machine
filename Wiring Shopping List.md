# Wiring Shopping List

Power & Control System – V1

## 1. AC Mains and Power Distribution Wire

### High-current AC (cabinet internal)

* **10 AWG stranded copper wire (green)**

  * Purpose: main cabinet ground bond
  * Buy: 10–15 ft

* **10 AWG stranded copper wire (black/red)**

  * Purpose: main AC feed inside cabinet
  * Buy: 10–15 ft

* **12 AWG stranded copper wire (black/red)**

  * Purpose: VFD input power
  * Buy: 10–15 ft

* **14 AWG stranded copper wire (black/red)**

  * Purpose: stepper PSU AC feed
  * Buy: 10–15 ft

* **16 AWG stranded copper wire**

  * Purpose: control PSU AC feed
  * Buy: 10 ft

Insulation type:

* MTW or THHN, 600 V rated, 75 °C or higher

## 2. VFD to Spindle Cable (critical item)

* **Shielded VFD motor cable, 4-conductor**

  * Conductors: **14 AWG**
  * Configuration: 3 phases + ground
  * Shield: braided or foil + drain
  * Length: machine dependent

    * Typical router: **15–25 ft**

Do not substitute generic SOOW here. This cable matters.

## 3. Stepper DC Power Wiring

### DC bus (PSU to distribution)

* **10 AWG stranded copper wire (red and black)**

  * Purpose: stepper PSU DC output to terminal block
  * Buy: 10 ft each color

### DC distribution to drivers

* **14 AWG stranded copper wire (red and black)**

  * Purpose: terminal block to each DMA860S
  * Buy: 25–30 ft total (covers all four drivers)

## 4. Stepper Motor Cables

You have **4 NEMA 34 motors**.

* **Shielded motor cable, 4-conductor**

  * Conductors: **14 AWG**
  * Twisted pairs preferred
  * Shield with drain wire
  * Length per motor:

    * X motors: gantry travel + service loop
    * Y motor: full axis travel
    * Z motor: shorter run
  * Typical total buy: **60–80 ft**

Label both ends before installing.

## 5. Control Power (24 VDC)

* **16 AWG stranded copper wire**

  * Purpose: 24 VDC PSU to distribution
  * Buy: 10 ft

* **18 AWG stranded copper wire**

  * Purpose: distribution to DDCSV, relays, fans
  * Buy: 30–40 ft

Color suggestion:

* Red = +24 V
* Black or blue = 0 V

## 6. Step / Direction / Enable Signal Wiring

* **Shielded, twisted-pair control cable**

  * Conductors: **22 AWG**
  * Pairs: at least 2 pairs per axis
  * Shield with drain wire

Usage:

* DDCSV → DMA860S (Step, Dir, Enable)

Buy:

* **30–40 ft total**

You can run one multi-pair cable per driver or bundle pairs neatly.

## 7. Limits, Homes, and E-stop Wiring

### Limit and home switches

* **Shielded control cable**

  * Conductors: **22 AWG**
  * 2–3 conductors per switch
  * Buy: **40–60 ft** (depends on machine size)

### E-stop control loop

* **18 or 20 AWG stranded copper**

  * Purpose: E-stop logic loop
  * Buy: 15–20 ft

## 8. Analog Spindle Speed Control (0–10 V)

* **Shielded twisted-pair cable**

  * Conductors: **22 AWG**
  * Buy: 10–15 ft

This must be its own cable. Do not bundle with step/dir.

## 9. Grounding and Shield Termination

* **14 AWG green stranded copper wire**

  * Purpose: bonding PSUs, drivers, VFD chassis
  * Buy: 15–20 ft

* **Drain wire (18–22 AWG)**

  * Purpose: shield termination to ground bar
  * Usually included in shielded cable, but have extra on hand

## 10. Optional but strongly recommended

* Ferrules for:

  * 10 AWG
  * 12 AWG
  * 14 AWG
  * 16 AWG
  * 18–22 AWG
* Heat-shrink labels
* Cable clamps and strain reliefs
* Wire duct (slotted)
