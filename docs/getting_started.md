# **Getting Started**

Welcome to the **J16MOTO ROS 2 Tutorials** documentation.

This guide helps you set up your environment and start working with the **J16MOTO** platform using **ROS 2**. It is designed for beginners who want to get the tutorials running quickly, while also providing enough structure for more advanced users.

---

## What you will learn

In this documentation, you will learn how to:

- set up the development environment
- install the required dependencies
- configure the ROS 2 workspace
- run basic examples
- understand the J16MOTO software structure
- work with topics, services, actions, and debugging tools
- build up to the final autonomous docking application

---

## Prerequisites

Before starting, make sure you have:

- a Linux machine or a supported development environment
- ROS 2 installed
- Python 3 available
- Git installed
- basic familiarity with terminal commands
- access to the J16MOTO project files or repository

---

## Recommended environment

The tutorials are intended to work best with:

- **Ubuntu 22.04**
- **ROS 2 Humble**
- **Python 3.10+**

Other setups may work, but the examples and commands in this documentation assume this baseline environment.

---

## Folder structure

A typical workspace may look like this:

```bash
~/j16moto_ws/
├── src/
│   ├── j16moto_bringup/
│   ├── j16moto_description/
│   ├── j16moto_interfaces/
│   └── j16moto_examples/
├── build/
├── install/
└── log/
```