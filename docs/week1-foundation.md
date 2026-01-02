# Week 1 — Foundations (Electronics + Arduino Bring-up + Vehicle Platform)

This week focused on establishing **core electronics fundamentals**, validating measurements with lab instruments, and bringing up an **Arduino-based 4WD vehicle platform**. The emphasis was on building a reliable evidence chain: **theory → design → measurement → interpretation**.

---

## What I Built

### 1) Voltage Divider + Loading Effect (Analog Interface)
- Designed and tested a resistor divider driven by a DC supply.
- Verified *real-world loading effect* by adding a 10 kΩ load and comparing output to the unloaded case.
- Key takeaway: output voltage deviation under load matched circuit theory (effective parallel resistance).

**Portfolio point:** I didn’t only “wire a divider”—I validated how measurement conditions and load change outputs.

---

### 2) LED Current Limiting (Safe Digital Output Practice)
- Built LED circuits with current-limiting resistors.
- Compared LED brightness/current under different resistor values.
- Reinforced safe design practice for MCU IO pins (avoid overcurrent).

---

### 3) RC Circuit and Time Constant Measurement (First-Order Dynamics)
- Built an RC circuit and measured the transient response using the oscilloscope.
- Extracted the time constant τ from the waveform (63.2% point).
- Discussed why charge/discharge timing differs based on the discharge path (equivalent resistance).

**Portfolio point:** Introduced dynamic system thinking (τ, filtering), which becomes essential in Week 2 real-time control.

---

### 4) Manual H-Bridge + DC Motor Test (Motor Drive Fundamentals)
- Implemented a manual H-bridge experiment for motor direction control.
- Observed how load affects motor behaviour:
  - load ↑ → current ↑
  - speed (RPM) ↓
- Interpreted the results using basic motor torque–speed relationships.

---

### 5) Arduino Nano Bring-up (Embedded Basics)
- Completed foundational Arduino exercises:
  - GPIO output (blink)
  - PWM / analogWrite behaviours
  - analogRead measurement logic
  - serial output for debugging
- Ensured a stable development workflow and reproducible tests.

---

### 6) Vehicle Platform Bring-up
- Completed mechanical assembly and electrical integration of the 4WD platform.
- Validated basic motion sequences and baseline driving behaviour.
- Identified real-world issues (e.g., drift) and noted the need for calibration and feedback control later.

---

## Key Results (Evidence-Friendly)
- Voltage divider output: **unloaded vs loaded** behaviour consistent with theory.
- RC response: **time constant extracted from scope transient** and explained with equivalent resistance paths.
- Motor test: **load-dependent current and speed changes** observed and discussed.
- Vehicle platform: **successful bring-up** and controlled baseline motion.

---

## Evidence Pack
- Full report (Session I): `report-assets/` (PDF)
- Recommended screenshots to include later:
  - Divider measurement table / calculation screenshot
  - RC transient scope capture (τ marked)
  - H-bridge wiring photo + motor test notes
  - Vehicle assembly photos

---

## Lessons Learned (Engineering Reflection)
- Measurements are only meaningful when the test condition is controlled (loading effect matters).
- RC circuits are not just “lab theory”—they directly relate to signal filtering and timing stability.
- Motor drive experiments are best understood via relationships between voltage, speed, current, and load—this informs later control design.
