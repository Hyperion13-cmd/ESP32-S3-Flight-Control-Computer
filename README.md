# ESP32-S3-Flight-Control-Computer
Advanced Flight Control Computer for high-altitude rockets. Features ESP32-S3, ADXL375 High-G IMU, MPU9250, MS5611, and 1W LoRa E22-900M30S telemetry. Powered by AP64500 Sync-Buck. Currently in schematic/PCB design phase.
# Advanced ESP32-S3 Flight Control Computer (Under Development)

<img width="949" height="690" alt="image" src="https://github.com/user-attachments/assets/3f6a5bcd-e271-4cf4-914a-7ab073bac249" />
<img width="1090" height="774" alt="image" src="https://github.com/user-attachments/assets/f8bd7da9-01c5-4c58-9825-2d4b03a52331" />
<img width="1105" height="812" alt="image" src="https://github.com/user-attachments/assets/abaa3640-6caa-4d80-9411-4a79678f81a9" />



## 📌 Project Overview
This project represents a next-generation, custom-designed Flight Control Computer tailored for high-altitude and supersonic rocket competitions. Currently in the hardware design phase, this board is engineered from the ground up to handle extreme G-forces, provide ultra-long-range telemetry, and ensure fail-safe pyro deployments.

### ⚙️ Core System Architecture
The system is built around the powerful **ESP32-S3** microcontroller, providing dual-core processing capabilities and wireless ground configuration, supported by a robust hardware stack:

* **High-G Dynamics:** **ADXL375** 3-axis accelerometer capable of measuring up to ±200g, ensuring data integrity during the violent shock of motor ignition.
* **Precision IMU:** **MPU9250** (9-DOF) for high-resolution orientation, pitch, roll, and yaw tracking during the coast phase.
* **Altitude & Apogee:** **MS5611** high-precision barometer for exact apogee detection.
* **Extreme Range Telemetry:** **LoRa E22 900M30S (1 Watt / 30dBm)** module, guaranteeing unbroken air-to-ground data links even at extreme altitudes.
* **Positioning:** Quectel L86-M33 GPS with integrated antenna.
* **Power Management:** **AP64500 Synchronous Buck Converter** delivering a highly efficient, stable 5A continuous output to handle the immense transient current spikes of the 1W LoRa module.

---

## 🛠️ Engineering Focus & Design Challenges
*(Note: This board is currently in the PCB routing phase)*

* **Transient Power Management:** The E22 900M30S LoRa module draws over 1A of current during maximum transmit bursts. The power delivery network (PDN) is being carefully routed with high-capacitance bulk decoupling to prevent the ESP32-S3 from browning out during transmission.
* **Sensor Redundancy:** Utilizing both an MPU9250 and an ADXL375 prevents sensor clipping. The MPU9250 handles flight orientation, while the ADXL375 captures the launch shockwave that would otherwise saturate standard accelerometers.
* **Hardware Interfacing:** Integrated TTL-to-RS232 shifting for reliable external module communication, alongside dedicated, optically or electrically isolated pyro-channels for deployment safety.

---

## 📁 Repository Structure
* `\Hardware_Design`: Altium Designer Schematic (.SchDoc) and PCB Layout (.PcbDoc) files (WIP).
* `\Datasheets`: Technical documentation for critical components (ADXL375, AP64500, E22-900M30S).
* `\Manufacturing`: Assembly files, BOM, and Gerbers used for the actual flight hardware production.
