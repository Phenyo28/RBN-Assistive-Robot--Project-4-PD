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

## User Manual
