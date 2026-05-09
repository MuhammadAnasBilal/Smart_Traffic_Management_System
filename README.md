<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=28&pause=1000&color=2F81F7&center=true&vCenter=true&width=700&lines=Smart+Traffic+Light+Management+System" alt="Smart Traffic Light Management System" />

<p>A C++/Qt desktop application that uses YOLOv8 computer vision to dynamically<br>control traffic signals, detect red-light violations, and optimize intersection flow.</p>

<br>

<img src="https://img.shields.io/badge/C++-C++17-00599C?style=for-the-badge&logo=cplusplus&logoColor=white" />
<img src="https://img.shields.io/badge/Qt-5%2F6-41CD52?style=for-the-badge&logo=qt&logoColor=white" />
<img src="https://img.shields.io/badge/OpenCV-4.11.0-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white" />
<img src="https://img.shields.io/badge/YOLOv8-ONNX-FF6F00?style=for-the-badge" />
<img src="https://img.shields.io/badge/Arduino-Hardware-00878F?style=for-the-badge&logo=arduino&logoColor=white" />

<br><br>

<img src="https://img.shields.io/badge/Status-Active%20Development-brightgreen?style=flat-square" />
<img src="https://img.shields.io/badge/Semester-BSAI%202nd-blue?style=flat-square" />
<img src="https://img.shields.io/badge/License-Educational-orange?style=flat-square" />

<br><br>

<a href="https://github.com/MuhammadAnasBilal/Smart_Traffic_Management_System">
  <img src="https://img.shields.io/badge/View%20Repository-181717?style=for-the-badge&logo=github&logoColor=white" />
</a>
&nbsp;
<a href="https://github.com/MuhammadAnasBilal/Smart_Traffic_Management_System/releases/download/v1.0.0/Smart-Traffic-System-v1.0.zip">
  <img src="https://img.shields.io/badge/Download%20v1.0.0-%E2%AC%87%EF%B8%8F%2055.9%20MB-2ea44f?style=for-the-badge&logo=github&logoColor=white" />
</a>

</div>

---

## Download

<div align="center">

| Release | Platform | Size | Date |
|:---:|:---:|:---:|:---:|
| [**v1.0.0 — Initial Release**](https://github.com/MuhammadAnasBilal/Smart_Traffic_Management_System/releases/tag/v1.0.0) | Windows 64-bit | 55.9 MB | Jun 17, 2025 |

<br>

<a href="https://github.com/MuhammadAnasBilal/Smart_Traffic_Management_System/releases/download/v1.0.0/Smart-Traffic-System-v1.0.zip">
  <img src="https://img.shields.io/badge/%E2%AC%87%EF%B8%8F%20Smart--Traffic--System--v1.0.zip-2ea44f?style=for-the-badge" />
</a>

</div>

<br>

> Extract the zip and run `SmartTrafficSystem.exe` — no installation required. Make sure `yolov8n.onnx` and `coco.names` are in the same directory before launching.

---

## Overview

Traditional fixed-timer traffic lights cannot respond to actual road conditions — they waste time and fuel regardless of congestion. This system replaces that logic entirely.

Live camera feeds are analyzed by a YOLOv8 model, counting and classifying vehicles per lane at a 4-way intersection. The application assigns green-light durations proportional to traffic density. When a vehicle runs a red light, the system flags it instantly, timestamps the event, and saves a snapshot as evidence. A physical Arduino connection drives real LED traffic lights from the same commands controlling the on-screen simulation.

Built as a 2nd-semester OOP project by four BSAI students, with equal contribution across backend logic, computer vision, UI, and hardware integration.

---

## Features

<table>
  <tr>
    <td><b>&#128246; Adaptive Signal Timing</b></td>
    <td>Green-light duration scales with real-time vehicle count and size — no fixed timers</td>
  </tr>
  <tr>
    <td><b>&#128065; YOLOv8 Detection</b></td>
    <td>Identifies cars, buses, trucks, and motorcycles per lane using the ONNX model</td>
  </tr>
  <tr>
    <td><b>&#128200; Density Classification</b></td>
    <td>Five-tier system from OFF to VERY HIGH drives lane priority decisions</td>
  </tr>
  <tr>
    <td><b>&#9889; Energy Saving Mode</b></td>
    <td>Signal deactivates automatically when no vehicles are detected in a lane</td>
  </tr>
  <tr>
    <td><b>&#128247; Violation Detection</b></td>
    <td>Flags red-light runners with timestamp and saved image evidence automatically</td>
  </tr>
  <tr>
    <td><b>&#128268; Arduino Integration</b></td>
    <td>Controls physical LED traffic lights via serial communication in real time</td>
  </tr>
  <tr>
    <td><b>&#128507; 4-Way Intersection</b></td>
    <td>Monitors all four roads simultaneously with independent density tracking</td>
  </tr>
  <tr>
    <td><b>&#128187; Real-Time Dashboard</b></td>
    <td>Live camera feeds, traffic metrics, violation log, and system events in one UI</td>
  </tr>
</table>

---

## Tech Stack

<div align="center">

| Layer | Technology |
|---|---|
| Language | C++ (C++17) |
| GUI Framework | Qt 5.15+ / Qt 6.x — Widgets, SerialPort |
| Computer Vision | OpenCV 4.11.0 — DNN module |
| Detection Model | YOLOv8n — ONNX format |
| Hardware | Arduino — serial communication |
| Build System | qmake |

</div>

---

## Getting Started

### Prerequisites

- Qt 5.15+ or Qt 6.x
- OpenCV 4.11.0 with DNN support
- MSVC 2019/2022 (Windows) or GCC/Clang (Linux)
- `yolov8n.onnx` and `coco.names` model files

### Model Files

Place both files in the application directory before running:

```
yolov8n.onnx    —  YOLOv8 nano detection model
coco.names      —  COCO dataset class labels
```

### Build

```bash
# Clone the repository
git clone https://github.com/MuhammadAnasBilal/Smart_Traffic_Management_System.git
cd Smart_Traffic_Management_System
```

Update OpenCV paths in `oopfinalproj.pro` to match your installation:

```pro
INCLUDEPATH += "C:/opencv/build/include"
LIBS += -L"C:/opencv/build/x64/vc16/lib" -lopencv_world4110
```

Build and run:

```bash
qmake oopfinalproj.pro
make
./SmartTrafficSystem
```

---

## Usage

| Step | Action | Description |
|:---:|---|---|
| 1 | **Connect Cameras** | Enter sources — device index, video file path, or RTSP stream URL |
| 2 | **Configure Arduino** | Select a serial COM port, or enable simulation mode |
| 3 | **Start System** | Begin the traffic management cycle from the dashboard |
| 4 | **Adjust Settings** | Tune light durations, YOLO thresholds, and energy-saving behavior |
| 5 | **Review Violations** | Browse infractions and captured image evidence in the log panel |

---

## Configuration

**Traffic Light Timings**

| Density | Vehicle Count | Green Duration |
|---|:---:|:---:|
| ⚫ OFF | 0 | 5s |
| 🟢 LOW | 1 – 3 | 8s |
| 🟡 MEDIUM | 4 – 7 | 12s |
| 🟠 HIGH | 8 – 12 | 18s |
| 🔴 VERY HIGH | 13+ | 25s |

> Yellow light: `3s` (configurable) &nbsp;·&nbsp; Confidence threshold: `0.45` &nbsp;·&nbsp; NMS threshold: `0.4`

---

## Project Structure

```
├── main.cpp                    # Application entry point
├── mainwindow.h/cpp/ui         # GUI interface
├── trafficsystem.h/cpp         # Core traffic controller logic
├── processingworker.h/cpp      # YOLO detection worker thread
├── traffic_types.h             # Enums: TrafficLight, TrafficDensity
└── oopfinalproj.pro            # Qt project file
```

---

## Troubleshooting

<details>
<summary><b>System fails to initialize</b></summary>
<br>
Verify that <code>yolov8n.onnx</code> and <code>coco.names</code> are present in the application directory.
</details>

<details>
<summary><b>Camera connection fails</b></summary>
<br>
Check device availability and system camera permissions.
</details>

<details>
<summary><b>Arduino not detected</b></summary>
<br>
Confirm the correct COM port, install required drivers, or switch to simulation mode.
</details>

<details>
<summary><b>Poor detection accuracy</b></summary>
<br>
Lower the YOLO confidence threshold, configure a Region of Interest (ROI), and ensure adequate lighting on the camera feed.
</details>

---

## Team

<div align="center">

<table>
  <tr>
    <td align="center">
      <a href="https://github.com/MuhammadAnasBilal">
        <img src="https://github.com/MuhammadAnasBilal.png" width="80" /><br><br>
        <b>Muhammad Anas Bilal</b><br>
        <sub>241478</sub>
      </a>
    </td>
    <td align="center">
      <a href="https://github.com/eyadarshad">
        <img src="https://github.com/eyadarshad.png" width="80" /><br><br>
        <b>Eyad Arshad</b><br>
        <sub>241464</sub>
      </a>
    </td>
    <td align="center">
      <a href="https://github.com/Shahzaib-Pervez">
        <img src="https://github.com/Shahzaib-Pervez.png" width="80" /><br><br>
        <b>Shahzaib Pervez</b><br>
        <sub>241392</sub>
      </a>
    </td>
  </tr>
</table>

</div>

---

## Project Status

<div align="center">

<img src="https://img.shields.io/badge/%E2%97%8F%20Active%20Development-2ea44f?style=for-the-badge" />

</div>

---

<div align="center">
<sub>For educational and research purposes only &nbsp;·&nbsp; BSAI 2nd Semester OOP Project</sub>
</div>
