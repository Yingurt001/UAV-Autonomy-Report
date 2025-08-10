# UAV Autonomy Workflow (ROS Noetic + PX4)

**Keywords**: ROS Noetic, Gazebo, PX4, MAVROS, QGroundControl, Offboard Mode, Keyboard Teleoperation, Simulation, Real Flight

This project aims to **replicate and extend** the workflow of controlling a PX4 UAV in Gazebo using keyboard teleoperation, followed by real-world manual flight tests and parameter logging — laying the groundwork for future **autonomous flight** and **machine learning / reinforcement learning** applications.

> 📌 This repository contains: complete installation steps, simulation & real-flight workflows, experiment templates, and troubleshooting guidelines.

---

## 1. Introduction

The project investigates and evaluates UAV autonomous flight performance.  
Using both a virtual UAV simulation environment and real UAV hardware, the workflow starts with **Ubuntu 20.04 + ROS Noetic + Gazebo + PX4** setup, then integrates MAVROS for communication and control.  
Manual flight is first tested in simulation (keyboard control), then replicated in real hardware.

---

## 2. Literature Review

Several studies demonstrate that integrating advanced sensors with complex ML algorithms can greatly enhance UAV autonomy. Key technologies include:
- Navigation and positioning systems
- Autonomous decision-making algorithms
- Sensor data fusion

For example:
- Smith et al. (2021) explored GPS + vision-based dual-modality positioning.
- Jones et al. (2022) studied deep learning–based obstacle avoidance strategies.

---

## 3. Methods

A mixed-methods approach was adopted, combining theoretical study and practical implementation:
1. **Simulation Setup**  
   - OS: Ubuntu 20.04  
   - Installed ROS Noetic & Gazebo  
   - Configured PX4 SITL with MAVROS
2. **Hardware Setup**  
   - Selected compatible sensors & FCU for stable and safe flight  
   - Integrated logging & telemetry systems
3. **Data Collection**  
   - Log files and live telemetry
4. **Analysis**  
   - Flight performance metrics
   - Behavioural analysis under test scenarios

---

## 4. Installation (Simulation)

### 4.1 Install ROS Noetic & Gazebo
```bash
sudo sh -c '. /etc/lsb-release && echo "deb http://mirrors.ustc.edu.cn/ros/ubuntu/ $DISTRIB_CODENAME main" > /etc/apt/sources.list.d/ros-latest.list'
sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654
sudo apt update
sudo apt install ros-noetic-desktop-full
sudo rosdep init
rosdep update
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
