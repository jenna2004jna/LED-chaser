## Project Overview
Design an LED Chaser circuit (555 Timer + 4017 Decade Counter) and document the process for PCB fabrication using KiCad.

---

### 1. README (Project Introduction)

- **What is this?**
  An LED Chaser (aka LED Sequencer) using an NE555 Timer and CD4017 Decade Counter IC. This project demonstrates classic digital IC sequencing without microcontrollers.
- **Features:**
  - Chaser effect using 10 LEDs
  - Simple circuit, good for learning PCB design
  - Step-by-step development in KiCad
- **Repository Structure:**
  - `schematic/`   – KiCad schematic files
  - `pcb/`        – PCB layout files (KiCad)
  - `gerbers/`    – Generated manufacturing files
  - `docs/`       – Project documentation / images

---

### 2. Design Notes

- **Circuit Choice:**
  - 555 Timer (Astable mode) generates clock pulses
  - 4017 Decade Counter increments output, driving LEDs
- **Key Components:**
  - NE555 Timer IC
  - CD4017 Decade Counter IC
  - 10 LEDs (5mm, THT)
  - 10 Current limiting resistors (220Ω–330Ω)
  - Power: 5V or 9V
  - Decoupling capacitors (0.1µF at each IC's VCC/GND)
- **PCB Best Practices:**
  - Place ICs centrally
  - LED row for clear chaser effect
  - Power input near edge
  - Capacitors close to ICs
  - Use ground plane (GND zone) for noise immunity
  - Short 555-to-4017 clock trace
- **Fabrication:**
  - Run DRC in KiCad before generating Gerbers
  - Export Gerber and drill files for manufacturing (JLCPCB/PCBWay)

---

### 3. Bill of Materials (BOM)

| Qty | Reference           | Value         | Part Type   | Note                  |
|-----|---------------------|--------------|-------------|-----------------------|
| 1   | U1                  | NE555        | DIP-8       | Timer IC              |
| 1   | U2                  | CD4017       | DIP-16      | Decade Counter IC     |
| 10  | LED1–LED10          | 5mm          | THT         | Indicator LEDs        |
| 10  | R1–R10              | 220Ω–330Ω    | Axial       | LED current limiting  |
| 1   | R11                 | 10kΩ (ex)    | Axial       | 555 timing resistor   |
| 1   | C1                  | 10µF         | Radial      | 555 timing capacitor  |
| 2   | C2, C3              | 0.1µF        | Ceramic     | Decoupling capacitors |
| 1   | Conn1               | Power Input  | Header 2-pin| 5V or 9V supply       |

> Update ref/value as per your specific schematic.

---

### 4. Assembly & Testing Notes

- Solder components in order: resistors → IC sockets → LEDs → capacitors → power connector
- Double-check orientation of ICs and LEDs
- After assembly, power up and confirm LED chaser sequence
- If sequence fails, check clock trace length, decoupling cap placement, and solder joints
<img width="337" height="587" alt="Screenshot 2026-03-03 221244" src="https://github.com/user-attachments/assets/5cee533a-1855-431d-981a-e37e39b73215" />
<img width="244" height="398" alt="Screenshot 2026-03-03 221307" src="https://github.com/user-attachments/assets/2e9b393b-8a08-44c2-b13d-020acc71e8f8" />


<img width="730" height="352" alt="Screenshot 2026-03-03 221339" src="https://github.com/user-attachments/assets/cf421754-83b7-4c72-9e28-6137773d29ef" />


### 5. References & Further Reading

- [KiCad Official Documentation](https://docs.kicad.org/)
- [555 Timer & CD4017 datasheets](https://www.ti.com)
- [Example LED Chaser Circuits](https://www.electronics-tutorials.ws/sequential/seq_2.html)

---

**Maintainer:** jenna2004jna
