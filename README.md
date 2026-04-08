# Spatially Verified Diffusion (SVD) for Safe Outdoor Exploration

[![Project Page](https://img.shields.io/badge/Project-Page-blue.svg)](https://your-username.github.io/SVD-Nav/)
[![ROS 2](https://img.shields.io/badge/ROS-2-22314E.svg)](https://docs.ros.org/en/humble/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> **Spatially Verified Diffusion for Lightweight and Safe Exploration in Grass-Dominated Outdoor Environments** > *Chengwei Zhang, Yifan Du* > *Sun Yat-sen University*

This repository contains the official implementation of **Spatially Verified Diffusion (SVD)**, a modular framework that augments diffusion-based trajectory generation with an external spatial verification layer for safe robotic navigation in grass-dominated environments.

---

## 🚀 Overview

Diffusion-based navigation policies can generate diverse short-horizon trajectory hypotheses from visual observations. However, unconstrained diffusion policies may generate trajectory samples that cross soft boundaries in outdoor environments (e.g., grass-to-pavement transitions). 

SVD solves this by:
1. Constructing a transient robot-centric bird's-eye-view (BEV) feasibility space from semantic traversability predictions (YOLOv8) and camera geometry.
2. Filtering candidate trajectories *before* execution, enforcing hard spatial constraints post hoc.
3. Operating natively in a **ROS 2** closed-loop architecture directly on embedded edge hardware.

## 🛠 Hardware System

Our experimental platform is designed for high-performance mobile robotics, consisting of:
* **Chassis:** Traxxas TRX4 (1800KV Brushless, High-torque servo)
* **Perception:** Intel RealSense D435 (Global Shutter, 87°×58° Depth FOV)
* **Compute:** NVIDIA Jetson Orin Nano (40 TOPS, 8GB LPDDR5)

## 💻 Installation & Setup

### Prerequisites
* Ubuntu 22.04
* ROS 2 (Humble recommended)
* Python 3.8+
* CUDA & TensorRT (for Jetson deployment)

### Clone the Repository
```bash
git clone [https://github.com/your-username/SVD-Nav.git](https://github.com/your-username/SVD-Nav.git)
cd SVD-Nav