# 🚗 Advanced Lane Finding

![Python](https://img.shields.io/badge/Python-Computer_Vision-blue?style=for-the-badge&logo=python&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-Lane_Detection-green?style=for-the-badge)
![Computer Vision](https://img.shields.io/badge/Focus-Geometric_Perception-red?style=for-the-badge)
![Autonomous Driving](https://img.shields.io/badge/Domain-Self_Driving_Cars-orange?style=for-the-badge)
![Udacity](https://img.shields.io/badge/Udacity-Self_Driving_Car_Engineer-purple?style=for-the-badge)

Advanced lane detection pipeline developed as part of the Self-Driving Car Engineer Nanodegree.

The project combines camera calibration, image processing, perspective transformations, lane tracking, and geometric estimation to identify lane boundaries and estimate vehicle position in road video streams.

---

## Overview

Lane detection is a fundamental perception task for autonomous vehicles.

Unlike simple edge detection approaches, this project implements a full computer vision pipeline capable of:

* Correcting camera distortion
* Transforming the road into a bird's-eye perspective
* Detecting lane pixels using gradient and color thresholding
* Tracking lane boundaries across frames
* Estimating lane curvature
* Estimating vehicle position relative to the lane center
* Rendering lane boundaries back onto the original road image

---

## Pipeline

The perception pipeline consists of the following stages:

```text
Camera Calibration
        ↓
Distortion Correction
        ↓
Gradient & Color Thresholding
        ↓
Perspective Transform
        ↓
Lane Pixel Detection
        ↓
Polynomial Lane Fitting
        ↓
Curvature Estimation
        ↓
Vehicle Offset Estimation
        ↓
Lane Overlay Rendering
