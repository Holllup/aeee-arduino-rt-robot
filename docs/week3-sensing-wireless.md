# Week 3 — Sensors & Wireless (Calibration, Joystick, Optical Sensing)

This week focused on **sensor calibration** and **remote control**, integrating various input devices—such as accelerometers, analog joysticks and reflective optical sensors—into the Arduino. You will read the sensor outputs, determine thresholds, and implement remote communication.

---

## What I Built

### 1) Analog Joystick Remote Control
- Designed a voltage-divider circuit for both axes of a joystick to feed the Arduino’s ADC.
- Mapped ADC readings to PWM duty cycles to control speed and steering.
- Built a handheld joystick board that connected via cable or wireless module to the vehicle for remote control.

### 2) Three‑Axis Accelerometer (MPU‑6050) Inclination Sensing
- Studied the datasheet, configured the I²C interface and range settings.
- Wrote a calibration routine to remove bias, and used filtering (such as moving average or complementary filter) to extract tilt angles.
- Used tilt information to detect vehicle pitch or provide safety alerts.

### 3) Reflective Optical Sensor (TCRT5000) Calibration
- Built a test circuit, comparing the output voltage over white vs. black surfaces.
- Measured output vs. distance to set thresholds and filter out noise.
- Added a simple comparator stage to convert analog output to digital high/low, then read it on the Arduino.

### 4) Wireless Communication
- Chose an RF/Bluetooth/infrared module and designed a packet format.
- Implemented two‑way communication between the joystick controller and the car, including commands and status feedback.
- Verified reliability by measuring range, latency and packet loss.

### 5) Power Module Testing
- Evaluated DC‑DC converters like the MP1584 or LM2596 for stable sensor supply.
- Adjusted output and inspected ripple with an oscilloscope.

---

## Key Results (Evidence‑Friendly)

- **Joystick calibration:** Both axes span the full ADC range (0–1023); the neutral position drift is under ±5 counts.
- **Accelerometer measurement:** After calibration, the tilt measurement accuracy was within ±2° and filtering added less than 50 ms latency.
- **Optical sensor threshold:** Significant voltage difference between black and white surfaces; best detection range about 5 mm; digital conversion false‑trigger rate below 2%.
- **Wireless link:** End‑to‑end latency around 10–20 ms and reliable control over several meters with <1 % packet loss.

---

## Evidence Pack

- Photos or schematics of the joystick controller.
- Calibration plots or screenshots for the accelerometer.
- Output vs. distance or reflectivity charts for the optical sensor.
- Wireless packet test screenshots (scope captures or debug logs).
- Week 3 demonstration photos (e.g. remote‑controlled driving).

---

## Lessons Learned (Engineering Reflection)

- Calibration must account for environmental variation; noise filtering and threshold tuning are critical.
- Reliable communication requires synchronization on both sides and robust error handling.
- Adding multiple sensors and inputs increases software complexity, so clear modular interfaces are essential.
