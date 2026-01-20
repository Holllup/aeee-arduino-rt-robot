# Week 4 — System Integration & Control (Closed‑Loop & Final Challenge)

The final week combined all previous hardware and software modules. You were tasked with integrating sensors, HMI, motors and power into a coherent system capable of completing a final challenge—such as a line‑following race—by tuning parameters and refining algorithms.

---

## What I Built

### 1) Sensor Fusion & Mode Switching
- Unified input from optical sensors, the accelerometer and joystick into a single data structure.
- Implemented different modes (manual, automatic, test) and a simple state machine to manage transitions.

### 2) Closed‑Loop Control (Line Following / PID)
- Implemented a line‑following algorithm: calculated error from left/right sensor values and adjusted motor PWMs accordingly.
- Tested both a proportional or PID‑based controller to achieve stable curves and straight segments.
- Tuned P/I/D gains by analyzing error curves on an oscilloscope and adjusted for different track conditions.

### 3) System Integration & Debugging
- Connected the HMI (from Week 2) to allow setting speed, mode and tuning parameters on the fly.
- Consolidated all subsystems (power, communication, sensor, control) and tidied wiring to minimize noise and errors.
- Developed the main loop with initialization, self‑test, run and fault‑handling states.

### 4) Final Challenge Demonstration
- Ran the robot on the official track, recording lap time and reliability metrics.
- (If applicable) Demonstrated seamless switching between remote control and autonomous modes.

---

## Key Results (Evidence‑Friendly)

- **Line‑following performance:** Completed the track in 30–60 seconds (depending on length), with zero derailments; maximum lateral error kept within ±X centimetres.
- **Robustness:** Line detection remained stable under varied lighting and surface conditions; motors did not overheat or stall.
- **Full integration:** After powering up, the system operated correctly without further tuning, showing that all subsystems were correctly integrated.

---

## Evidence Pack

- Photos or diagrams of the track used.
- High‑quality photos of the fully assembled robot showing sensor placements and HMI.
- Plots of sensor outputs vs. motor PWM duty cycles during a line‑following run.
- Video or GIF of the final challenge demonstration.

---

## Lessons Learned (Engineering Reflection)

- Systems integration often presents more challenges than individual module design; clear wiring, modular code and systematic debugging are key.
- Closed‑loop control requires careful tuning; P, I and D terms affect response speed and stability differently.
- Environmental factors (e.g. lighting, surface reflectivity) greatly influence sensor performance; hardware solutions like shields or filters can help.
- Keeping detailed records of tests and tuning sessions helps with future projects and troubleshooting【turn1file0†L28-L32】.
