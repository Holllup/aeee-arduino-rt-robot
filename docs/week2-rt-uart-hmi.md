# Week 2 — Real-Time Control + UART Validation + HMI Integration

This week upgraded the system from “a working robot platform” to an **integrated embedded system** featuring:
- **UART communication** validated by oscilloscope timing
- **Real-time (interrupt-driven) control** for deterministic updates (≥200 Hz)
- **Custom HMI** for parameter input and status output
- **Individual low-battery indicator board** (analog front-end + ADC + LED state machine)

---

## What I Built

## 1) UART Communication Between Two Arduino Boards (with Waveform Validation)
- Established UART TX/RX wiring with common ground.
- Verified data exchange using Serial Monitor.
- Measured UART bit timing on the oscilloscope and compared against the configured baud rate.
- Documented why programming becomes problematic when RX/TX lines are connected (shared serial lines with bootloader/programmer).

**Portfolio point:** I validated not only functionality, but also *physical-layer timing*.

---

## 2) Individual Task: Low Battery Voltage Indicator (Divider + RC + ADC + LED Logic)
- Designed a voltage divider + RC filter to safely scale battery voltage for Arduino ADC input.
- Selected threshold levels based on a 2-cell battery discharge profile.
- Implemented a simple state machine:
  - high → 2 LEDs on
  - mid → 1 LED on
  - low → blinking warning

**Portfolio point:** This is a real embedded feature: analog protection + sampling + threshold logic + user feedback.

---

## 3) Real-Time (RT) Stability Demo: noIRQ vs withIRQ
- Compared two strategies under artificial delays:
  - loop-based update (non-deterministic timing)
  - timer interrupt update (deterministic timing)
- Observed the difference in output stability via oscilloscope measurements.
- Concluded: interrupt scheduling is essential for stable control loops in embedded systems.

---

## 4) RT Sine-Wave Generator (PWM + Amplification + Filtering)
- Implemented an interrupt-driven signal generation approach:
  - compute target waveform samples
  - update PWM duty cycle at a fixed rate
- Designed an amplification + reconstruction filtering stage to achieve a clean sine waveform from PWM.
- Verified frequency and ripple performance using oscilloscope captures.

**Portfolio point:** This is a complete digital-to-analog engineering path: timing → PWM → analog reconstruction → validation.

---

## 5) HMI Design and System Integration (Buttons + Switch + Encoder + LCD + Buzzers/LED)
- Integrated multi-input and multi-output HMI components to control system behaviour:
  - start/stop input
  - direction setting
  - speed/target setting (encoder)
  - status display (LCD)
  - status indication (LED / buzzer)
- Built the interaction logic as a clear state machine (running/stopped + mode selection).

**Portfolio point:** This is system engineering: user interface + embedded timing + motor control integration.

---

## Key Results (Evidence-Friendly)
- UART validated by oscilloscope timing (bit-level evidence)
- Interrupt-driven loop delivered stable deterministic behaviour (vs loop jitter)
- PWM-based sine output achieved clean waveform after filtering
- HMI successfully controlled and displayed system parameters
- Battery indicator implemented as an individual hardware+firmware feature

---

## Evidence Pack
- Full report (Session II): `report-assets/` (PDF)
- Recommended screenshots to include later:
  - UART TX/RX waveform capture + timing marker
  - noIRQ vs withIRQ stability comparison waveforms
  - PWM and reconstructed sine wave output captures
  - battery indicator schematic + threshold test notes
  - HMI board photo and LCD status screen photo

---

## Lessons Learned (Engineering Reflection)
- RT control is not optional for control systems: timing determinism changes stability.
- Waveform-level verification (scope) is a powerful skill—much stronger than “it works on Serial Monitor”.
- Analog front-end design (divider + RC) and firmware thresholds must be calibrated together.
- HMI integration forces clean software structure (state machines, debouncing, UI updates).
