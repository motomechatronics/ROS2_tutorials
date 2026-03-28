# ROS 2 Tutorials for MOTO Mobile Autonomous Robots

Welcome to the **ROS 2 Tutorials** section dedicated to the **mobile autonomous robots developed by MOTO Mechatronics**.

These tutorials are specifically designed for **MOTO Mechatronics robotic platforms**, with a particular focus on the **J16MOTO** robot.

These tutorials can be directly implemented using the **MOTO Mechatronics Application Development Environment**, which can be downloaded from: https://github.com/motomechatronics/amrj16moto_utimac

This area provides a **complete learning path** for students, researchers, and engineers who want to acquire **practical and professional skills in mobile robotics using ROS 2**, working on real robotic platforms rather than abstract examples.

---

## 🎯 Purpose of this Section

The goal of these tutorials is to:

- provide a **structured and progressive introduction** to ROS 2 applied to mobile robots  
- bridge the gap between **theoretical ROS knowledge and real robotic systems**
- guide users through **hands-on experimentation** on MOTO Mechatronics robots
- promote **good engineering practices**, including documentation, reproducibility, and clarity

These tutorials are not meant to be isolated exercises.  
They are part of a **coherent learning journey**, where each topic prepares the ground for the next one.

---

## 🤖 Target Platforms

The tutorials are developed and tested on **mobile autonomous robots produced by MOTO Mechatronics**, including educational and research-oriented platforms.

While the focus is on MOTO robots, the concepts and workflows presented here follow **ROS 2 standards** and are therefore transferable to other mobile robotic systems.

---

## 📚 Tutorial Scope 

This section covers the full ROS 2 ecosystem for mobile robotics, including:

- **ROS 2 fundamentals**
  - Nodes, topics, services, actions
  - Parameters and lifecycle nodes
  - Package structure and best practices

- **Robot description**
  - URDF / Xacro
  - TF and coordinate frames
  - Sensors and actuators modeling

- **Simulation**
  - Gazebo / other supported simulators
  - Simulation vs real robot workflows
  - Debugging in simulation

- **Navigation**
  - Nav2 stack
  - Localization (AMCL)
  - Mapping and SLAM
  - Costmaps and planners

- **Perception**
  - Cameras and LiDAR integration
  - Sensor data processing
  - Basic perception pipelines

- **System integration**
  - Launch files
  - Configuration management
  - Debugging and logging

---

## 🧭 How the Tutorials Are Written

Each tutorial is designed to be:

- **Applied** – commands and code are executed on real projects  
- **Narrative** – every section explains *why* a step is needed before showing *how*  
- **Incremental** – no big jumps in complexity without preparation  
- **Reproducible** – the reader should always obtain the expected result  

You are encouraged to **run, modify, break, and fix** things while following the tutorials.

If something does not work as expected, it is considered part of the learning process.

---

## 👨‍🎓 Who This Is For

These tutorials are suitable for:

- university students in robotics, automation, or computer science
- internship candidates working with MOTO Mechatronics
- junior engineers approaching ROS 2 for mobile robotics
- anyone who wants a **clear, applied, and realistic introduction to ROS 2**

A basic knowledge of Linux and programming (Python and/or C++) is recommended.

---

## 🧠 Learning Philosophy

> ROS 2 is not just a middleware.  
> It is a way of thinking about robotic systems.

These tutorials aim to teach not only *how to use ROS 2*, but also **how to reason about robotic architectures**, data flow, and system behavior in real-world scenarios.

---

## 📌 Notes

- Tutorials are continuously improved and expanded.
- Feedback and suggestions are welcome.
- All content is intended for **educational and training purposes**.

---

Happy learning,  
**MOTO Mechatronics – Robotics Education & Research**

# ROS 2 Node Example

This section explains how to create and run a simple ROS 2 node.

---

## 📌 Initialization

!!! note
    Make sure ROS 2 is properly installed and sourced before running any command.

---

## 🚀 Run a Node

!!! tip
    Use the following command to run your node:

    ```bash
    ros2 run my_package my_node
    ```

---

## ⚠️ Common Issue

!!! warning "Environment not sourced"
    If you see errors like *command not found*, you probably forgot to source ROS 2:

    ```bash
    source /opt/ros/humble/setup.bash
    ```

---

## 🧠 Python Node Example

```python
import rclpy
from rclpy.node import Node


class MyNode(Node):
    def __init__(self):
        super().__init__('my_node')
        self.get_logger().info("Hello ROS2")


def main(args=None):
    rclpy.init(args=args)
    node = MyNode()
    rclpy.spin(node)
    node.destroy_node()
    rclpy.shutdown()

```