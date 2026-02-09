# Autonomous Drone Flight Project

A comprehensive autonomous drone project using ArduPilot, Raspberry Pi 5, and Python-based trajectory planning with Vicon motion capture tracking.

## 🎯 Overview

This project demonstrates autonomous drone flight capabilities through progressive exercises, from basic construction to advanced trajectory planning. The drone uses ArduPilot firmware with Python-based control via DroneKit or MAVSDK libraries, integrated with Vicon motion capture for precise indoor positioning.

**Key Features:**
- QAV250 quadcopter frame assembly
- ArduPilot flight controller integration
- Raspberry Pi 5 companion computer
- Python-based autonomous flight control
- Vicon motion capture integration
- Spiral trajectory implementation
- Safety-first design approach

## 🛠️ Hardware Requirements

### Drone Components
- **Frame:** QAV250 Mini Quadcopter Frame
- **Flight Controller:** Pixhawk 4 Mini with ArduPilot firmware
- **Companion Computer:** Raspberry Pi 5
- **ESCs:** Electronic Speed Controllers (4x)
- **Motors:** Brushless motors (4x)
- **Propellers:** Matched set (DO NOT install until tutor approval)
- **Battery:** LiPo battery with appropriate charger
- **Power Distribution Board**
- **Remote Controller:** For manual flight

### Additional Equipment
- Safety glasses
- LiPo safety bag
- Protective net for testing area
- SD Card (64-bit) for Raspberry Pi OS
- WiFi access (Zyxel recommended)

## 💻 Software Requirements

### Required Software
- **Raspberry Pi OS** (64-bit)
- **ArduPilot** - Flight control firmware
- **Python 3.x** with the following libraries:
  - DroneKit (`dronekit-python`) - Recommended
  - MAVSDK (alternative)
  - PyVicon datastream
- **VS Code** with Remote Explorer extension (for SSH)

### Documentation Links
- [ArduPilot Initial Setup Guide](https://ardupilot.org/copter/docs/initial-setup.html)
- [DroneKit Python Documentation](https://dronekit-python.readthedocs.io/en/latest/guide/index.html)

## ⚠️ Safety Protocols

### CRITICAL SAFETY RULES

**LiPo Battery Safety:**
- ✅ Only use approved chargers
- ✅ Always use fire-resistant LiPo bag during charging
- ✅ Never leave batteries charging unattended
- ✅ Store at 3.8-3.85V per cell when not in use for >24 hours
- ✅ Store in cool, dry location inside LiPo bag
- ❌ Never drop, puncture, or bend batteries
- 🚨 Immediately report puffed, swollen, or damaged batteries

**Workshop & Flight Safety:**
- ✅ Safety glasses required when working on drone
- ✅ **DO NOT install propellers until tutor approval**
- ✅ **Always put drone behind protective net when powered on**
- ✅ Keep workspace clean and organized
- ✅ Be mindful of other groups in the lab
- ❌ Never test motors/propellers without tutor inspection

> **WARNING:** Failure to follow safety protocols may result in equipment damage, personal injury, and lab access revocation.

## 📁 Project Structure

The project is organized into three progressive exercises:

### Exercise 0: Preparation
- Kit inspection and inventory verification
- Lab access setup
- Safety protocol review

### Exercise 1: Construction of the Drone
- Frame assembly (QAV250)
- Electronic component installation
- Software configuration (ArduPilot)
- First manual flight

### Exercise 2: Automation
- Raspberry Pi 5 integration
- Vicon motion capture setup
- Autonomous flight programming
- Spiral trajectory implementation

## 🚀 Installation & Setup

### Exercise 0: Preparation

#### 0.1 Kit Inspection
- Create a checklist of all components
- Verify nothing is broken or missing
- Report any issues to tutors immediately

#### 0.2 Lab Access
- Obtain lab access card
- Designate one group member to sign for card
- Store card securely

### Exercise 1: Drone Construction

#### 1.1 Frame Assembly

1. **Plan Component Placement**
   - Consider wire routing
   - Center of gravity
   - Accessibility for maintenance
   - Review plan with tutor before assembly

2. **Assemble QAV250 Frame**
   - Follow [Pixhawk 4 Mini QAV250 Kit Quick Start Guide](https://docs.px4.io/main/en/frames_multicopter/holybro_qav250_pixhawk4_mini.html)
   - Consult online build log for detailed visual guide

3. **Connect Electronic Components**
   - ESCs
   - Motors
   - Power Distribution Board
   - Ensure neat and secure wiring

4. **Verify Motor Configuration**
   - Check motor layout matches guide diagram
   - Confirm spin directions
   - **Critical for flight stability**

5. **⚠️ STOP - DO NOT ATTACH PROPELLERS**
   - Get tutor inspection and approval first
   - Only install propellers after explicit permission

#### 1.2 Software Installation

Follow the ArduPilot first setup guide for complete configuration including software setup, calibration, and radio controller configuration.

#### 1.3 First Flight

- Present complete assembly to tutor
- Get final check-up approval
- Fly manually with remote controller

### Exercise 2: Autonomous Flight Setup

#### 2.1 Raspberry Pi 5 Setup

**Steps:**
1. Flash Raspberry Pi OS (64-bit) to SD Card
2. Enable SSH and connect to WiFi (Zyxel recommended)
3. Update system packages
4. Install Python dependencies (dronekit, pymavlink)
5. Test DroneKit installation

**VS Code Remote Development:**
- Install "Remote Explorer" extension in VS Code
- Connect to RPI 5 via SSH for remote development

#### 2.2 Vicon Motion Capture Integration

Install PyVicon datastream library on Raspberry Pi.

Request tutor assistance for:
- Vicon Tracker software setup
- Streaming object data configuration
- Code example for receiving Vicon data

#### 2.3 DroneKit/MAVSDK Interface

**Recommended: DroneKit**
- [DroneKit Documentation](https://dronekit-python.readthedocs.io/en/latest/guide/index.html)
- Interfaces Raspberry Pi with Pixhawk
- Allows position commands and velocity control

## 📐 Trajectory Planning

### Spiral Trajectory Exercise (2.3)

**Objective:** Program autonomous upward spiral (helical) trajectory

**Trajectory Specifications:**
- **Radius:** 1 meter
- **Starting Height:** 0.5 meters
- **Final Height:** 1.5 meters
- **Mindful of lab ceiling constraints**

**Mathematical Implementation:**

Generate waypoints using trigonometric functions (sine and cosine) for the circular path in the xy-plane, while linearly increasing the z-component for the ascent. The number of windings is up to you to decide and implement.

**Execution Requirements:**
- Smooth waypoint transitions
- Safe takeoff to starting height
- Smooth landing after trajectory completion
- Code must include safety features (safe takeoff and landing)

## 🔧 Troubleshooting

### Common Issues

**Battery not charging:**
- Check charger settings
- Verify correct LiPo balance mode
- Inspect battery for damage

**Motors not spinning:**
- Check ESC connections
- Verify motor direction configuration
- Ensure proper PWM signals from flight controller

**DroneKit connection failed:**
- Verify serial port: `/dev/ttyAMA0` or `/dev/ttyUSB0`
- Check baud rate (typically 57600 or 115200)
- Ensure Raspberry Pi is powered properly

**Vicon data not streaming:**
- Verify network connection
- Check Vicon Tracker software configuration
- Request tutor assistance for setup

**Unstable flight:**
- Re-check motor directions
- Verify propeller installation (correct orientation)
- Recalibrate IMU and compass
- Check center of gravity

## 📚 References

- [ArduPilot Documentation](https://ardupilot.org/copter/)
- [DroneKit Python Guide](https://dronekit-python.readthedocs.io/)
- [Pixhawk 4 Mini Setup](https://docs.px4.io/main/en/frames_multicopter/holybro_qav250_pixhawk4_mini.html)
- [PyVicon Datastream](https://pypi.org/project/pyvicon-datastream/)

## 📄 License

This project is developed as part of an academic course. Please check with your institution regarding usage and distribution rights.

## ⚡ Acknowledgments

- Course instructors and tutors
- ArduPilot development community
- DroneKit developers

---

**⚠️ SAFETY REMINDER:** Always follow safety protocols. Never fly without tutor approval. Report any issues immediately.

