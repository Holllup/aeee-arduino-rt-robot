# aeee-arduino-rt-robot
4-week Arduino robotics project: focusing on **electronics bring-up**, **real-time embedded control**, **HMI design**, and **system integration** on an Arduino-based 4WD robot platform.

> **Highlights:** UART validation with oscilloscope captures, timer-interrupt real-time control (≥200 Hz), custom soldered HMI, and an individual low-battery indicator board.

---

## Demo
- **Final demo video:** [link or placeholder]
- **Photos:** see `/media/photos/`
- **Key waveforms (UART / RT control):** see `/experiments/scope_captures/`

> GIF placeholder:  
![demo-gif](media/gifs/demo.gif)

---

## System Overview
**Hardware (typical):**
- Arduino Nano (controller)
- 4WD chassis + DC motors with encoders
- H-bridge motor driver / baseboard
- HMI: buttons, slide switch, rotary encoder, LCD1602, LEDs, buzzers, microphone
- Individual battery voltage indicator (divider + RC filter + LEDs)

**Software:**
- Modular firmware for HMI, UART tests, and real-time control loops
- Timer ISR for deterministic control period (real-time)
- State machine for challenge tasks

---

## What We Built (4 Weeks)
### Week 1 — Foundations
- Basic circuit verification: divider / LED current limiting / RC / manual H-bridge
- Arduino bring-up and basic IO/PWM/ADC
- Vehicle assembly and basic motion testing + path challenge

### Week 2 — UART + Real-Time + HMI (Core)
- UART communication between two Arduino boards with waveform verification
- Real-time control via timer interrupts (≥200 Hz)
- RT sine generator: ISR-based duty cycle control + amplification + filtering
- Custom HMI integration (LCD + encoder + buttons + buzzer/LED + mic option)
- Individual low-battery voltage indicator board

### Week 3 — Sensors & Wireless (fill based on actual work)
- [sensor list]
- [wireless module / protocol]
- [demo]

### Week 4 — System Integration & Control
- [line following / PID / final integration]
- [robustness improvements]
- [final challenge]

---

## Repository Structure
- `firmware/` Arduino code (modular by function)
- `hardware/` schematics, PCB notes, BOM, wiring
- `experiments/` measurements, oscilloscope captures, calibration records
- `docs/` project website (GitHub Pages)
- `media/` photos / videos / gifs for quick viewing

---

## How to Run
1. Open Arduino IDE
2. Flash firmware in `firmware/...`
3. Wire according to `hardware/schematics/...`
4. Verify using Serial Monitor and scope captures

> Note: Some pins and wiring are board-dependent; see `hardware/` documentation.

---

## Evidence Pack (for reproducibility)
- UART Tx/Rx waveforms (scope)
- Real-time control timing evidence
- Battery indicator measured thresholds
- Photos of soldered boards and integration

---

## License
MIT (or your preferred open-source license).
