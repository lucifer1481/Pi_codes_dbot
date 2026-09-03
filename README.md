# 🦾 Security D-Bot: Core ROS2 Navigation & Hardware (dbot)

This repository hosts the central ROS2 workspace running on a Raspberry Pi 4[cite: 1]. It manages the sensing, actuation, and cloud communication layers of the intelligent surveillance system[cite: 1].

## 🔗 Related Repository
*   **[Auto--Agesis](https://github.com/lucifer1481/Auto--Agesis):** The Jetson Nano package handling AI inference, YOLO detection, and CNN face recognition[cite: 1].

## 📸 Project Gallery

**1. The Security D-Bot (Front View)**


(<img width="4096" height="1836" alt="1788410356088" src="https://github.com/user-attachments/assets/b7e5e07e-ddcf-4aa1-a3e5-e09f50bb7685" />jpg)

**2. Internal Hardware & Wiring (Raspberry Pi + Arduino + L298N)**
(<img width="1836" height="4096" alt="1788410355927" src="https://github.com/user-attachments/assets/088182a2-f764-41fa-91a6-acbf43d3d441" />
)


## ⚙️ Core Features
*   **Autonomous Navigation:** Integrates SLAM for mapping, Nav2 for path planning, and AMCL for localization[cite: 1]. 
*   **Hardware Actuation:** Sends velocity commands via Twist Mux to an Arduino Uno, driving L-shaped encoder motors through an L298N motor driver[cite: 1].
*   **Multimodal Sensing:** Processes data from an RPLIDAR and a camera module[cite: 1].
*   **Cloud Alerting:** Transmits alerts and frames to a web dashboard via MQTT[cite: 1].

## 🛠️ Prerequisites
*   Ubuntu (Server or Desktop) on Raspberry Pi 4
*   ROS2 Humble installed and sourced
*   Configured I2C/Serial connections for the Arduino Uno

## 🚀 Installation & Setup

1. Clone the repository:
   ```bash
   cd ~/ros2_ws/src
   git clone [https://github.com/lucifer1481/dbot.git](https://github.com/lucifer1481/dbot.git)
   #Source the workspace:
    source ~/ros2_ws/install/setup.bash
   
   #Launch the hardware and navigation nodes:
    ros2 launch dbot robot_core.launch.py
   
   #To generate a map using SLAM:
    ros2 launch dbot slam.launch.py
