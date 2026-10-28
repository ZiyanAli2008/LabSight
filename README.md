# LabSight

**An ESP32-Based Smart Laboratory Monitoring and Object Tracking System**

**Status:** In Development — V1 Design Phase

## Overview

LabSight is a smart laboratory monitoring system designed to combine embedded systems, computer vision, environmental sensing, and automated object tracking into a single platform.

The system uses an adjustable articulated arm equipped with a motorized sensor head to track selected objects while collecting non-contact temperature and distance measurements. A stationary base monitors ambient environmental conditions, while a web dashboard processes, visualizes, and records data.

LabSight is designed to support both existing Wi-Fi networks and offline operation through a local wireless network.

## Planned V1 Features

- **Automatic Object Tracking:** Computer vision identifies and tracks a selected object using a camera and motorized pan/tilt mechanism.
- **Non-Contact Temperature Measurement:** An infrared sensor measures surface temperature within its field of view.
- **Distance Measurement:** A time-of-flight sensor measures distance to objects within its sensing region.
- **Environmental Monitoring:** Ambient temperature, humidity, pressure, and air-quality measurements.
- **Real-Time Dashboard:** Displays sensor readings, trends, tracking information, and experiment data.
- **Experiment Logging:** Records sensor measurements for later analysis.
- **Local Alerts:** OLED display, status LED, and audible warnings.
- **Dual Network Modes:** Operation through an existing Wi-Fi network or a locally hosted wireless network without internet access.

## System Architecture

LabSight consists of three main subsystems.

### 1. Sensor Head

**Controller:** Seeed Studio XIAO ESP32-S3 Sense (planned)

Components:
- Camera module
- MLX90614 infrared temperature sensor
- VL53L1X time-of-flight distance sensor
- Two MG90S servo motors for pan and tilt

The sensor head captures images, collects target-related measurements, and receives tracking commands.

### 2. Monitoring Base

**Controller:** ESP32-WROOM-32

Components:
- BME280 environmental sensor
- ENS160 + AHT21 air-quality and environmental sensor module
- SSD1306 OLED display
- RGB status LED
- Buzzer
- Pushbuttons

The base collects environmental measurements and provides local monitoring and controls.

### 3. Computer and Web Application

Planned technologies:
- Python
- OpenCV
- Web backend (Flask or FastAPI)
- Web dashboard
- SQLite for experiment data storage

The computer performs object tracking, processes measurements, sends servo commands, and hosts the monitoring dashboard.

## Mechanical Design

LabSight V1 uses a custom articulated desktop arm with:

- Freestanding 3D-printed electronics base
- Two manually adjustable arm segments
- Lockable friction joints
- Motorized pan/tilt sensor head
- Cable routing through or along the arm

The main arm is positioned manually, while the sensor head automatically rotates to track selected objects.

## Development Roadmap

- [x] Define V1 project concept and requirements
- [x] Inventory existing hardware
- [x] Select preliminary hardware components
- [x] Draft bill of materials
- [x] Design preliminary system architecture
- [x] Complete initial mechanical sketches
- [ ] Verify electrical compatibility and finalize purchases
- [ ] Test individual sensors and controllers
- [ ] Implement wireless communication
- [ ] Integrate camera streaming
- [ ] Develop computer vision tracking
- [ ] Implement pan/tilt servo control
- [ ] Integrate automatic object tracking
- [ ] Integrate environmental and target measurements
- [ ] Design and 3D-print mechanical components
- [ ] Develop web dashboard and experiment logging
- [ ] Complete system testing and calibration
- [ ] Document final results and demonstration

## Engineering Challenges

Key areas of development include:

- Reliable wireless camera streaming and control
- Sensor alignment and measurement accuracy
- Closed-loop pan/tilt tracking
- Power distribution and servo current management
- Mechanical stability and joint design
- Integration of embedded firmware with computer vision and a web application

## Current Progress

**October 27, 2026**

Completed the initial V1 concept, hardware inventory, preliminary component selection, system architecture, and mechanical design sketches.

Current priorities are finalizing electrical compatibility, purchasing components, and preparing for hardware prototyping.

## Project Documentation

Development documentation, wiring diagrams, CAD models, test results, and progress logs will be added as the project progresses.

## License

MIT License for repository software. Hardware design licensing may be specified separately.
