# Power & Control System Configuration

Power & Control System – V1

* **Controller:** CNCTOPBAOS DDCSV4.1 (stand-alone, PLC-capable, MPG)
* **Axes:** 4 total

  * X axis: dual NEMA 34 (slaved, auto-squaring)
  * Y axis: single NEMA 34
  * Z axis: single NEMA 34
* **Motors:** HobbyUnlimited NEMA 34, 6 A, 12 Nm, 156 mm
* **Drivers:** 4 × DMA860S digital stepper drivers
* **Stepper power:** SE-1500-68 68V adjustable switching power supply 68V 1500W DC 0-68V 68V 22A
* **Control and logic power supply:** Mean Well NDR-240-24, 24 VDC, 10 A, DIN-rail mounted.
* **Spindle system:** Huanyang 2.2 kW VFD + 80 mm water-cooled spindle, 0–10 V speed, relay run control
* **Safety model:** Hardware E-stop cutting stepper power and spindle run, plus controller awareness
* **Architecture:** Fully stand-alone, no PC dependency during runtime
