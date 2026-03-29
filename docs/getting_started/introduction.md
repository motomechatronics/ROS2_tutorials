# ROS 2 Tutorials for MOTO Mobile Autonomous Robots

Welcome to the **ROS 2 Tutorials** section dedicated to the **mobile autonomous robots developed by MOTO Mechatronics**.

These tutorials are specifically designed for **MOTO Mechatronics robotic platforms**, with a particular focus on the **J16MOTO** robot.

The tutorials can be directly implemented using the **MOTO Mechatronics Application Development Environment**, available at:  
https://github.com/motomechatronics/amrj16moto_utimac

This section provides a **structured and comprehensive learning path** for students, researchers, and engineers aiming to acquire **practical and professional competencies in mobile robotics using ROS 2**, working on real robotic systems rather than abstract examples.

---

## Purpose of this Section

The objective of these tutorials is to:

- Provide a **structured and progressive introduction** to ROS 2 applied to mobile robotics  
- Bridge the gap between **theoretical knowledge and real robotic systems**  
- Enable **hands-on experimentation** on MOTO Mechatronics platforms  
- Promote **sound engineering practices**, including reproducibility, clarity, and documentation  

These tutorials are not intended as isolated exercises, but as part of a **coherent learning pathway**, where each topic builds upon the previous one.

---

## Target Platforms

The tutorials are developed and validated on **mobile autonomous robots produced by MOTO Mechatronics**, including educational and research-oriented platforms.

While the primary focus is on MOTO systems, the methodologies and workflows follow **ROS 2 standards**, making them transferable to other robotic platforms.

---

## Tutorial Scope

This section covers the core components of the ROS 2 ecosystem for mobile robotics:

- **ROS 2 Fundamentals**
  - Nodes, topics, services, and actions  
  - Parameters and lifecycle nodes  
  - Package structure and best practices  

- **Robot Description**
  - URDF and Xacro  
  - TF and coordinate frames  
  - Modeling of sensors and actuators  

- **Simulation**
  - Gazebo and compatible simulators  
  - Simulation versus real robot workflows  
  - Debugging in simulated environments  

- **Navigation**
  - Nav2 stack  
  - Localization (AMCL)  
  - Mapping and SLAM  
  - Costmaps and planning algorithms  

- **Perception**
  - Integration of cameras and LiDAR  
  - Sensor data processing  
  - Basic perception pipelines  

- **System Integration**
  - Launch files  
  - Configuration management  
  - Debugging and logging  

---

## Methodology

Each tutorial is designed according to the following principles:

- **Applied** – all commands and code are executed on real systems  
- **Explanatory** – each step is introduced with its underlying rationale  
- **Incremental** – complexity is introduced progressively  
- **Reproducible** – results should be consistent and verifiable  

Users are encouraged to experiment actively, including modifying and troubleshooting the system as part of the learning process.

---

## Intended Audience

These tutorials are intended for:

- University students in robotics, automation, or computer science  
- Internship candidates working with MOTO Mechatronics  
- Junior engineers approaching ROS 2 for mobile robotics  
- Practitioners seeking a **clear and application-oriented introduction to ROS 2**  

A basic understanding of Linux and programming (Python and/or C++) is recommended.

---

## Learning Philosophy

ROS 2 is not only a middleware, but a framework for designing and reasoning about robotic systems.

These tutorials aim to develop both **practical skills** and the ability to **analyze system architecture, data flow, and behavior** in real-world conditions.

---

## Notes

- The tutorials are continuously updated and expanded  
- Feedback and contributions are encouraged  
- All content is intended for **educational and training purposes**  

---

## Example: ROS 2 Node

This section illustrates the creation and execution of a minimal ROS 2 node.

---

### Initialization

!!! note
    Ensure that ROS 2 is correctly installed and that the environment has been sourced before executing any command.

---

### Running a Node

!!! tip
    Execute the following command to run a ROS 2 node:

    ```bash
    ros2 run my_package my_node
    ```

---

### Common Issue

!!! warning "Environment not sourced"
    If commands are not recognized, verify that the ROS 2 environment has been sourced:

    ```bash
    source /opt/ros/humble/setup.bash
    ```

---

### Python Node Example

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