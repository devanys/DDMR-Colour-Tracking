# Differential Drive Mobile Robot: Path Following Colour Tracking


https://github.com/user-attachments/assets/81dc65f6-cd88-4e63-ad33-f30aecf656b5

This repository contains a **Python OpenCV colour-tracking controller** and an **ESP32 WiFi motor driver** used to control a Differential Drive Mobile Robot.  
The robot tracks **two coloured markers (Red → Green)** and moves based on PID steering and real-time TCP commands.

---

## 🚀 Features

### Python (mobot_follow_color.py)
- Dual-colour tracking (Red & Green) using HSV segmentation  
- PID steering control  
- Distance estimation from bounding-box width  
- Real-time TCP commands to ESP32  
- Automatic reconnect  
- Lost-target auto-stop  
- HSV calibration load/save  
- Noise reduction (morphological filtering)  

### ESP32 Firmware
- WiFi TCP server at port `4210`  
- Differential drive control  
- Receives single-character commands:
  - `R` → Forward  
  - `L` → Backward  
  - `F` → Turn Right  
  - `B` → Turn Left  
  - `S` → Stop  

---
## 📷 System Architecture
---

## 🧠 How It Works

1. Webcam captures frame  
2. Convert BGR → HSV  
3. Detect red and green regions  
4. Compute:
   - centroid positions  
   - bounding box  
   - pixel error (cx_green - cx_red)  
5. PID calculates steering correction  
6. Convert PID output → robot movement  
7. TCP command sent to ESP32  
8. Distance estimation used to stop robot when close  

---


