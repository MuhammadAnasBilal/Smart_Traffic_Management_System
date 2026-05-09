<h1 align="center">Smart Traffic Management System (STMS)</h1>

<p align="center">
  AI-powered adaptive traffic control and violation monitoring system built using
  <b>C++</b>, <b>Qt</b>, <b>OpenCV</b>, <b>YOLOv8</b>, and <b>Arduino</b>.
</p>

<p align="center">
  Developed as a second-semester BSAI Object-Oriented Programming project.
</p>

<hr>

<h2>Project Overview</h2>

<p>
Traditional traffic systems rely on fixed timers that cannot adapt to changing
road conditions. This often leads to:
</p>

<ul>
  <li>Unnecessary congestion</li>
  <li>Increased waiting times</li>
  <li>Fuel wastage</li>
  <li>Poor traffic flow</li>
  <li>Weak traffic violation enforcement</li>
</ul>

<p>
The <b>Smart Traffic Management System (STMS)</b> addresses these problems using
real-time vehicle detection and adaptive signal timing.
</p>

<p>
Using live camera feeds and YOLOv8 object detection, the system analyzes traffic
density at intersections and dynamically controls traffic lights accordingly.
It also detects red-light violations and captures evidence automatically.
</p>

<p>
This project combines:
</p>

<ul>
  <li>Artificial Intelligence</li>
  <li>Computer Vision</li>
  <li>Object-Oriented Programming</li>
  <li>Embedded Systems</li>
  <li>Real-Time Monitoring</li>
</ul>

<hr>

<h2>Core Features</h2>

<h3>Adaptive Traffic Signal Control</h3>

<p>
Traffic light timings automatically adjust according to real-time vehicle density
instead of relying on fixed timers.
</p>

<h3>Real-Time Vehicle Detection</h3>

<p>Uses YOLOv8 + OpenCV DNN to detect and count:</p>

<ul>
  <li>Cars</li>
  <li>Trucks</li>
  <li>Buses</li>
  <li>Motorcycles</li>
</ul>

<p>from live video streams.</p>

<h3>Red-Light Violation Detection</h3>

<p>Automatically detects vehicles crossing during red signals and stores:</p>

<ul>
  <li>Violation timestamp</li>
  <li>Captured evidence image</li>
  <li>Violation logs</li>
</ul>

<h3>Arduino Integration</h3>

<p>
Supports physical traffic light simulation using Arduino and serial communication.
</p>

<h3>Multi-Road Intersection Support</h3>

<p>
Capable of monitoring and managing multiple roads simultaneously in a
4-way intersection model.
</p>

<h3>Real-Time Monitoring Dashboard</h3>

<p>Built using Qt GUI with:</p>

<ul>
  <li>Live camera feeds</li>
  <li>Traffic statistics</li>
  <li>Detection overlays</li>
  <li>Signal states</li>
  <li>System logs</li>
</ul>

<h3>Simulation & Testing Support</h3>

<p>The system can operate with:</p>

<ul>
  <li>Real cameras</li>
  <li>Video files</li>
  <li>RTSP streams</li>
  <li>Pure simulation mode</li>
</ul>

<hr>

<h2>System Architecture</h2>

<h3>1. Computer Vision Layer</h3>

<p><b>Responsible for:</b></p>

<ul>
  <li>Vehicle detection</li>
  <li>Vehicle counting</li>
  <li>Density estimation</li>
  <li>Frame processing</li>
</ul>

<p><b>Implemented using:</b></p>

<ul>
  <li>OpenCV</li>
  <li>YOLOv8 ONNX model</li>
</ul>

<h3>2. Decision-Making Layer</h3>

<p><b>Responsible for:</b></p>

<ul>
  <li>Traffic density analysis</li>
  <li>Signal timing calculation</li>
  <li>Traffic flow optimization</li>
  <li>Violation logic</li>
</ul>

<p><b>Implemented using:</b></p>

<ul>
  <li>C++</li>
  <li>Object-Oriented Programming principles</li>
  <li>Qt backend logic</li>
</ul>

<h3>3. Hardware & Interface Layer</h3>

<p><b>Responsible for:</b></p>

<ul>
  <li>GUI visualization</li>
  <li>Arduino communication</li>
  <li>Traffic signal simulation</li>
  <li>User interaction</li>
</ul>

<p><b>Implemented using:</b></p>

<ul>
  <li>Qt Widgets</li>
  <li>Qt SerialPort</li>
  <li>Arduino</li>
</ul>

<hr>

<h2>Tech Stack</h2>

<ul>
  <li>C++17</li>
  <li>Qt 5/6</li>
  <li>OpenCV 4.x</li>
  <li>YOLOv8 (ONNX)</li>
  <li>Arduino</li>
  <li>Qt SerialPort</li>
  <li>qmake</li>
</ul>

<hr>

<h2>Installation</h2>

<h3>Prerequisites</h3>

<p>Before building the project, install:</p>

<ul>
  <li>Qt 5.15+ or Qt 6.x</li>
  <li>OpenCV 4.x with DNN support</li>
  <li>MSVC 2019/2022 (Windows) or GCC/Clang (Linux)</li>
  <li>YOLOv8 ONNX model</li>
</ul>

<h3>Required Model Files</h3>

<p>Place the following files inside the application directory:</p>

<pre>
yolov8n.onnx
coco.names
</pre>

<h3>Clone Repository</h3>

<pre>
git clone https://github.com/MuhammadAnasBilal/Smart_Traffic_Management_System
cd SmartTrafficManagementSystem
</pre>

<h3>Configure OpenCV Paths</h3>

<p>Update OpenCV include/library paths inside:</p>

<pre>
project.pro
</pre>

<p>Example:</p>

<pre>
INCLUDEPATH += "C:/opencv/build/include"

LIBS += -L"C:/opencv/build/x64/vc16/lib" -lopencv_world4110
</pre>

<h3>Build Project</h3>

<pre>
qmake
make
</pre>

<p>Run:</p>

<pre>
./SmartTrafficSystem
</pre>

<hr>

<h2>Usage</h2>

<h3>Step 1 — Connect Camera Sources</h3>

<ul>
  <li>Webcam index</li>
  <li>Video file</li>
  <li>RTSP stream</li>
</ul>

<h3>Step 2 — Configure Arduino</h3>

<ul>
  <li>Serial COM port</li>
  <li>Simulation mode</li>
</ul>

<h3>Step 3 — Start Traffic System</h3>

<p>The system will:</p>

<ul>
  <li>Detect vehicles</li>
  <li>Estimate traffic density</li>
  <li>Control traffic lights dynamically</li>
</ul>

<h3>Step 4 — Monitor Violations</h3>

<p>
Violation events are automatically logged with evidence capture.
</p>

<hr>

<h2>Traffic Density Logic</h2>

<table>
  <tr>
    <th>Density Level</th>
    <th>Vehicle Count</th>
    <th>Green Signal Duration</th>
  </tr>
  <tr>
    <td>OFF</td>
    <td>0</td>
    <td>5 sec</td>
  </tr>
  <tr>
    <td>LOW</td>
    <td>1–3</td>
    <td>8 sec</td>
  </tr>
  <tr>
    <td>MEDIUM</td>
    <td>4–7</td>
    <td>12 sec</td>
  </tr>
  <tr>
    <td>HIGH</td>
    <td>8–12</td>
    <td>18 sec</td>
  </tr>
  <tr>
    <td>VERY HIGH</td>
    <td>13+</td>
    <td>25 sec</td>
  </tr>
</table>

<p><b>Yellow Signal Duration:</b> 3 seconds</p>

<hr>

<h2>YOLO Configuration</h2>

<pre>
Confidence Threshold: 0.45
NMS Threshold: 0.40
</pre>

<hr>

<h2>Project Structure</h2>

<pre>
├── main.cpp
├── mainwindow.h / .cpp / .ui
├── trafficsystem.h / .cpp
├── processingworker.h / .cpp
├── traffic_types.h
├── resources/
├── yolov8n.onnx
├── coco.names
└── project.pro
</pre>

<hr>

<h2>Team Contribution</h2>

<p>
This project was developed collaboratively by a team of BSAI students,
where each member contributed across:
</p>

<ul>
  <li>Backend development</li>
  <li>Computer vision integration</li>
  <li>GUI design</li>
  <li>Hardware communication</li>
  <li>Testing and debugging</li>
</ul>

<h3>Team Members</h3>

<ul>
  <li>
    <a href="https://github.com/MuhammadAnasBilal">Muhammad Anas Bilal</a>
  </li>
  <li>
    <a href="https://github.com/eyadarshad">Eyad Arshad</a>
  </li>
  <li>
    <a href="https://github.com/Shahzaib-Pervez">Shahzaib Pervez</a>
  </li>
</ul>

<hr>

<h2>License</h2>

<p>
This project is developed for:
</p>

<ul>
  <li>Educational purposes</li>
  <li>Research purposes</li>
  <li>Learning and experimentation</li>
</ul>

<hr>

<h2>Project Status</h2>

<p><b>Active Development</b></p>
