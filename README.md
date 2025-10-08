# RBN-Assistive-Robot-Project-4-PD
This project is about designing and building an autonomous navigation robot that integrates mechanical, electrical, and software systems into a single working prototype. The robot is equipped with ultrasonic sensors to detect and avoid obstacles, LED indicators to provide status feedback, and a mobile app for manual control when needed. It is powered by Li-ion batteries, driven by DC geared motors with encoders, and managed through an ESP32 microcontroller with a motor driver.

The main goal of this project is to demonstrate how autonomy and remote control can be combined in a low-cost robotic platform. It provides a learning opportunity for students, hobbyists, and researchers interested in robotics and embedded systems, while also serving as a foundation for more advanced applications such as delivery robots, assistive devices, or surveillance systems.

## Features of the robot
- Move forward, backward, turn.
-	Avoid obstacles using 2 ultrasonic sensors.
-	Indicate states (deployment, movement, obstacle detection) with LEDs.
-	Controlled via app (manual + autonomous mode).
-	User Manual

---

## Repository Contents
| File / Folder                 | Description                                       |
| ----------------------------- | ------------------------------------------------- |
| `Picture`                     |Folder of the project building images             |
| `BOM - PulseWave .xlsx`       | Bill of materials                                 |
| `README.md`                   |Update README.md                                   |
| `Schematic.png`               | Circuit schematic (image version)                 |
| `RP-Diale-PulseWave.ino`      | Arduino source code for running the soil detector |
|`PULSEWAVE PERFOMANCE FLOW`    | Perfomance workflow of the project                |

---

## Bill Of Materials

| Component Name                                    | Purpose in Project                                                               | Quantity  | 
| ------------------------------------------------- | -------------------------------------------------------------------------------- | --------- | 
| **ESP32 Development Board**                       | Main controller for Wi-Fi/app communication, sensor reading, motor control logic | 1         | 
| **Arduino Nano BLE 33 Sense**                     | Optional secondary controller (BLE features / sensor fusion)                     | 1         | 
| **L298N Motor Driver**                            | Drives 2 DC motors (direction + PWM speed control)                               | 1         |
| **12V DC Geared Motors with Encoders**            | Propulsion with encoder feedback for odometry                                    | 2         | 
| **Li-ion 18650 Battery Cells**                    | Main power source                                                                | 4         | 
| **18650 Battery Holder (4-slot)**                 | Secure batteries & provide connections                                           | 1         | 
| **5V DC-DC Step-Down Regulator (Buck Converter)** | Regulates battery voltage down to 5V for MCU & sensors                           | 1         | 
| **On/Off Rocker Switch**                          | Master power switch for safety                                                   | 1         | 
| **USB Cable**                                     | Programming and debugging                                                        | 1         | 
| **Breadboard**                                    | Prototyping connections                                                          | 1         | 
| **0.1 μF Ceramic Capacitors**                     | Noise decoupling on power lines                                                  | 2         | 
| **220 μF Electrolytic Capacitor**                 | Bulk decoupling on logic rail                                                    | 1         | 
| **10 μF Electrolytic/Tantalum Capacitor**         | Extra smoothing for buck converter output                                        | 1         | 
| **Ultrasonic Distance Sensors (HC-SR04)**         | Obstacle detection (front-left & front-right)                                    | 2         |
| **Caster Wheel**                                  | Stability for 2WD chassis                                                        | 1         | 
| **T-Slot Aluminium Extrusion**                    | Chassis/frame construction                                                       | 3         |
| LEDs (Red, Yellow, Green)	                        | Indicators for deployment, movement, obstacle detection	                         | 3	       |
| Resistors (220Ω / 330Ω)	                          | Current limiting for LEDs                                                        | 3–5      |
| **Misc. Hardware**                                | Screws, standoffs, zip ties, wires                                               | As needed | 

---

##  User Manual

### Introduction
The Assistive Robot is a smart, Wi-Fi-controlled robot designed to help users with basic assistive tasks such as navigation, movement, and obstacle detection. It combines functionality, safety, and ease of use, making it suitable for educational, personal, and assistive applications.

This manual provides step-by-step instructions on how to set up, operate, and maintain the robot. It also explains the meaning of LED indicators, app functions, and safety guidelines. Whether you are a beginner or an experienced user, this guide will help you use the robot confidently and effectively.

**Purpose of the User Manual:**
- To guide users through safe and correct operation of the assistive robot.  
- To explain the robot’s main features, functions, and controls.  
- To provide maintenance and troubleshooting support.  
- To promote safe handling of electrical and mechanical components.  

---

### Table of Contents
1. Introduction  
2. Package Contents
3. Operating instructions
4. Modes Of operations
   - Autonomous Mode
   - Manual Remote Mode
   - Standby / Idle Mode
5. Obstacle Avoidance
   - How it works
   - How to use
   - Tips for Best Performance
   - Limitations
6. Controls
   - Manual Control
   - Autonomous Mode (Obstacle Avoidance)
   - LED Indicators 
7. Battery Management
   - Installing the Batteries
   - Charging the Batteries
   - Battery Safety Tips
   - Maximizing Battery Life
   - Battery Replacement
8. | **Category**                  | **Tasks**                                                                                                                                                                                         | **Notes**                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| **A) Cleaning**               | • Wipe robot with a soft, dry cloth.<br>• Use a slightly damp cloth for stubborn dirt (avoid soaking).<br>• Keep ultrasonic sensors clean and dust-free.<br>• Avoid strong chemicals or solvents. | Ensures accurate sensor readings and keeps the robot looking neat. |
| **B) Battery Care**           | • Remove Li-ion 18650 cells when the robot is unused for long periods.<br>• Inspect batteries for swelling, leaks, or damage.<br>• Store in a cool, dry place away from sunlight.                 | Prevents battery damage and improves lifespan.                     |
| **C) Motor & Wheels**         | • Check wheels for dust, hair, or debris.<br>• Tighten chassis screws regularly.                                                                                                                  | Keeps robot moving smoothly and prevents wear.                     |
| **D) Electrical Connections** | • Inspect jumper wires and solder joints.<br>• Do not pull wires by the cable — use connectors.<br>• If a sensor or LED fails, check wiring first.                                                | Maintains reliable electrical performance.                         |
| **E) Software & Updates**     | • Back up ESP32/Arduino code.<br>• Update software only with verified versions.<br>• Test motors and sensors after updates.                                                                       | Prevents software-related malfunctions.                            |


---
