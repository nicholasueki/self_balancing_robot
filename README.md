# Self-Balancing Robot — Inverted Pendulum Control System

> **Note:** Full project documentation is being added.

A two-wheeled self-balancing robot implementing real-time PID control to maintain upright stability — the classic inverted pendulum problem applied to a physical embedded system.

---

## Objective

The inverted pendulum is inherently unstable: without active correction, it falls. The goal was to build a robot that uses onboard sensor feedback to continuously calculate and apply corrective torque fast enough to stay upright — and to tune the control gains to achieve stable, responsive balancing.

---

## What I Built

*(Full details coming — project documentation is being migrated to this repository.)*

Core components:
- **IMU (accelerometer + gyroscope)** for real-time tilt angle measurement
- **Complementary/Kalman filter** for sensor fusion (gyro drift correction)
- **PID controller** computing corrective motor output from angle error
- **DC motors with encoder feedback** for closed-loop wheel velocity control
- **Embedded firmware** running the full control loop at high frequency

---

## Challenges

**Sensor fusion** — Accelerometers are noisy; gyroscopes drift. Getting a clean tilt angle required fusing both sensors, which meant implementing and tuning a complementary filter before the PID loop could work at all.

**PID tuning** — With three independent gains to tune on a physically unstable system, finding stable operating parameters required systematic iteration — small changes to derivative gain in particular had outsized effects on oscillation.

---

## Tech Stack

- **Microcontroller:** Arduino / STM32
- **Sensors:** IMU (MPU-6050 or similar)
- **Control:** PID, complementary filter
- **Actuators:** DC motors with encoders
- **Language:** C/C++
