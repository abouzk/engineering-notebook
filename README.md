# Engineering Notebook & Knowledge Base
**Owner:** Karim Abouzeid  
**Focus:** Robotics, Embedded Systems, and Control Theory

## Overview
This repository serves as a living documentation of my technical development, experimental workflows, and problem-solving logs. Unlike my project repositories (which contain production-ready code), this notebook captures the **process:** the debugging trails, architectural decisions, and theoretical deep-dives that drive my engineering work.

## Active Learning Logs

### 📂 [Haptic Teleoperation & Digital Twins](logs/isaacsim-surgical-teleop-log.md)
*High-fidelity physics simulation for Sim-to-Real transfer.*
* **Status:** In Progress
* **Focus:** Node communication, bilateral control loops, and multi-modal hardware mapping.

### 📂 [Computer Vision Kinematics Pipeline](logs/mediapipe-hand-kinematics-log.md)
*Markerless telemetry using applied machine learning.*
* **Status:** In Progress
* **Focus:** Google MediaPipe integration and spatial coordinate extraction.
  
### 📂 [HMI Accessibility & Sensorimotor Simulator](logs/hmi-accessibility-sim-log.md)
*Testing human performance under artificial latency, input jitter, and sensory noise.*
* **Status:** In Progress
* **Focus:** Sensorimotor control loops, HCI ergonomics, and Pygame event handling.
  
### 📂 [Industrial Automation & Safety Architecture (ABB)](logs/industrial-robot-control-python-log.md)
*Documentation of standard industrial platforms and safety standards.*
* **Status:** Complete
* **Summary:** Analysis of RWS communication, latching hardware states, and Python-to-RAPID bridge architecture.
  
### 📂 [ROS 2 Architecture & Middleware](logs/ros2-fundamentals-log.md)
*Middleware configuration and node lifecycle management.*
* **Status:** In Progress
* **Focus:** Node composition and real-time DDS configuration.

### 📂 [Real-Time Embedded Motor Controller](logs/msp432-embedded-controllers-log.md)
*Bare-metal control system on TI MSP432 (ARM Cortex-M4).*
* **Status:** Complete (Retroactive Documentation)
* **Summary:** Architectural review of closed-loop feedforward + proportional velocity controllers, quadrature encoder timing, and sub-10µs interrupt latency diagnosis.

### 📂 [Autonomous Mobile Service Robot (ATmega2560)](logs/atmega-obstacle-avoidance-log.md)
*Differential drive kinematics and subsumption safety architecture.*
* **Status:** Complete (Retroactive Documentation)
* **Focus:** Hardware interrupts, proportional control loops, and embedded C++ safety overrides.

## Methodology
My engineering approach follows a cycle of **Theory → Implementation → Validation**:
1. **Theory:** Grounding work in fundamental constraints (e.g., Kinematics, ISO Safety).
2. **Implementation:** Building modular, testable drivers and systems.
3. **Validation:** Verifying performance against real-world telemetry (e.g., measuring latency and signal noise).

---
*Note: For production-ready source code and deployable assets, please visit the links provided at the top of each respective learning log.*
