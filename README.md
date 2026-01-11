# Differential Drive Robot (ROS2)

## Overview
This repository contains a **ROS2 workspace** for **visualizing and simulating a differential-drive robot** using **RViz** and **Gazebo**.

The project focuses on:
- Defining the robot using **XACRO / URDF**
- Visualizing the robot model in **RViz**
- Spawning and simulating the robot in **Gazebo**
- Bridging ROS2 and Gazebo using configuration files

This project is a learner project and is intended for **robot modeling, visualization, and simulation setup**. I made this with reference to a book named **ROS2 from Scratch** by Edouard Renard.


---

## Package Description

### my_robot_description
This package contains the **robot description**.

- Robot structure is defined using **XACRO**
- Modular files for:
  - Common properties
  - Differential drive mobile base
  - Gazebo-specific configuration
- RViz configuration for clear visualization
- Launch file to display the robot in RViz

This package defines **what the robot looks like and how it is structured**.

---

### my_robot_bringup
This package is responsible for **starting the simulation**.

- Launches Gazebo with the robot model
- Uses a **Gazebo bridge configuration** to connect ROS2 topics
- Acts as the main entry point to run the robot

This package connects the robot description with the simulation environment.

---

## How the Project Works (High Level)
1. XACRO files describe the robot’s links, joints and base.
2. The robot description is converted to URDF at runtime.
3. RViz visualizes the robot using a predefined configuration.
4. Gazebo simulates the robot with physics.
5. Bridge configuration enables communication between ROS2 and Gazebo.

---

## How to Run

### Prerequisites
- ROS2 Jazzy
- Gazebo
- Colcon build tools

### Steps
```bash
git clone https://github.com/ananyast81/Differential-Drive-Robot.git
cd Differential-Drive-Robot
```
```bash
source /opt/ros/jazzy/setup.bash
```
```bash
colcon build
source install/setup.bash
```
```bash
ros2 launch my_robot_bringup my_robot.launch.xml
```

