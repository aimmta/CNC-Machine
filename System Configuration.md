# Power & Control System Configuration

Power & Control System – V1

* **Controller:** CNCTOPBAOS DDCSV4.1 (stand-alone, PLC-capable, MPG)
* **Axes:** 4 total

  * X axis: dual NEMA 34 (slaved, auto-squaring)
  * Y axis: single NEMA 34
  * Z axis: single NEMA 34
* **Motors:** HobbyUnlimited NEMA 34, 6 A, 12 Nm, 156 mm
* **Drivers:** 4 × DMA860S digital stepper drivers
* **Stepper power:** Single high-voltage DC bus (60–72 VDC class)
* **Control power:** 24 VDC logic and I/O supply
* **Spindle system:** Huanyang 2.2 kW VFD + 80 mm water-cooled spindle, 0–10 V speed, relay run control
* **Safety model:** Hardware E-stop cutting stepper power and spindle run, plus controller awareness
* **Architecture:** Fully stand-alone, no PC dependency during runtime
