# Predator Deterrent System for the Southern African Foundation for the Conservation of Coastal Birds (SANCCOB)

This repository contains the final year project for EEE4114F at the University of Cape Town (2025), titled **"A Predator Deterrent System for SANCCOB"**. The project focuses on the design, development, and implementation of an embedded system to detect and deter honey badgers from entering penguin enclosures at SANCCOB's Cape Town facility.

## Table of Contents
- [Overview](#overview)
- [System Architecture](#system-architecture)
- [Sub-Modules](#sub-modules)
- [Technologies Used](#technologies-used)
- [Installation and Setup](#installation-and-setup)
- [Usage](#usage)
- [Project Contributors](#project-contributors)
- [License](#license)

---

## Overview

Honey badger intrusions pose a significant threat to African penguins under the care of SANCCOB. This project aims to build a modular and scalable embedded system that detects intrusions and deploys non-lethal acoustic deterrents while providing data logging and a user-friendly interface for rangers to monitor the situation.

The solution consists of three main components:
1. **Camera Sensing Subsystem** for predator detection
2. **Acoustic Deterrent Subsystem** to repel honey badgers
3. **User Interface Subsystem** for monitoring, analysis, and control

---

## System Architecture

The system follows a distributed modular architecture:
- **Central Embedded Controller (STM32 Nucleo Board)** receives classified detection data and issues deterrent commands.
- **Raspberry Pi** handles image processing using a YOLOv8 object detection model.
- **Audio Amplifier and Speaker System** for deterrent audio.
- **Python-based GUI** allows SANCCOB rangers to monitor detections, system status, and export logs.

---

## Sub-Modules

### 🧠 Camera Sensing Subsystem
- Captures live footage using Raspberry Pi camera
- Detects honey badgers using YOLOv8
- Sends detection signal to STM32 controller

### 🔊 Deterrent Subsystem
- STM32 triggers playback of deterrent audio
- MOSFET-based circuit drives speaker system

### 📊 User Interface Subsystem
- GUI developed in Python
- Displays system alerts, logs, and allows export to CSV
- Provides real-time feedback and system control for rangers

---

## Technologies Used

- **STM32 Nucleo Board**
- **Raspberry Pi 4**
- **Python 3.9**
- **OpenCV + Ultralytics YOLOv8**
- **Embedded C (Keil/STM32CubeIDE)**
- **PyQt for GUI**
- **MATLAB for prototyping**

---

## Installation and Setup

1. **Clone this repository**  
   ```bash
   git clone https://github.com/yourusername/sanccob-deterrent-system.git
   cd sanccob-deterrent-system
   ```

2. **Install dependencies for the GUI and object detection**  
   See `requirements.txt` for Python dependencies.

3. **Upload embedded firmware**  
   Use STM32CubeIDE to upload the `.hex` firmware to the STM32 board.

4. **Start the object detection module**  
   Ensure the camera is connected and run the detection script from the Raspberry Pi.

---

## Usage

- Run the `main.py` GUI application for interface controls and monitoring.
- The system will automatically:
  - Detect honey badgers via camera
  - Trigger acoustic deterrents
  - Log events and alerts for review

---

## Project Contributors

- **[Your Name]** – Embedded System Engineer  
- Project conducted in partial fulfillment of the BSc(Eng) Electrical and Computer Engineering degree, University of Cape Town.

---

## License

This project is intended for academic and non-commercial use by SANCCOB and the UCT EEE department. Licensing for commercial adaptation requires permission from the authors and SANCCOB.
