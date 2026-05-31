# 🚗 Advanced Lane Finding

![Python](https://img.shields.io/badge/Python-Computer_Vision-blue?style=for-the-badge&logo=python&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-Lane_Detection-green?style=for-the-badge)
![Computer Vision](https://img.shields.io/badge/Focus-Geometric_Perception-red?style=for-the-badge)
![Autonomous Driving](https://img.shields.io/badge/Domain-Self_Driving_Cars-orange?style=for-the-badge)
![Udacity](https://img.shields.io/badge/Udacity-Self_Driving_Car_Engineer-purple?style=for-the-badge)

Advanced lane detection pipeline developed as part of the Self-Driving Car Engineer Nanodegree.

This repository is part of a recovered Self-Driving Car Engineer portfolio. The goal is not only to preserve completed coursework, but to document the progression from classical computer vision toward modern AI and autonomous systems engineering.

---

## Overview

Lane detection is a fundamental perception task for autonomous vehicles.

Unlike simple edge detection approaches, this project implements a full computer vision pipeline capable of:

- Correcting camera distortion
- Transforming the road into a bird's-eye perspective
- Detecting lane pixels using gradient and color thresholding
- Tracking lane boundaries across frames
- Estimating lane curvature
- Estimating vehicle position relative to the lane center
- Rendering lane boundaries back onto the original road image

---

## Pipeline

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
```

---

## Techniques Used

### Camera Calibration

Chessboard calibration images are used to compute:

- Camera matrix
- Distortion coefficients

This allows removal of lens distortion before processing road images.

### Thresholding

Multiple feature extraction techniques are combined:

- Sobel gradients
- Gradient magnitude
- Gradient direction
- Color-space thresholding

The result is a binary image highlighting likely lane pixels.

### Perspective Transform

A homography transformation converts the road view into a top-down perspective.

This simplifies lane tracking and curvature estimation.

### Lane Detection

Lane pixels are identified using:

- Histogram analysis
- Sliding window search
- Polynomial fitting

The detected lanes are modeled as second-order polynomials.

### Geometry Estimation

The fitted lane curves are used to compute:

- Radius of curvature
- Vehicle lateral offset from lane center

---

## Results

The final pipeline successfully detects lane boundaries and projects them back onto the original road image while displaying:

- Lane region visualization
- Estimated lane curvature
- Vehicle position relative to lane center

The pipeline was evaluated on:

- Project video
- Challenge video
- Harder challenge video

---

## Repository Structure

```text
camera_cal/                 Camera calibration images
test_images/                Sample road images
output_images/              Pipeline outputs
examples/                   Example processing results
project_video.mp4           Original project video
project_video_output.mp4    Processed output video
my_advanced_laneline_project.ipynb
WRITE UP.pdf
```

---

## Technical Skills Demonstrated

- Python
- OpenCV
- Camera Calibration
- Perspective Geometry
- Feature Extraction
- Lane Tracking
- Polynomial Curve Fitting
- Computer Vision Pipelines
- Autonomous Vehicle Perception

---

## Documentation

A detailed technical report describing the implementation, design choices, limitations, and future improvements is included:

📄 **WRITE UP.pdf**

---

## Why This Project Matters

Advanced lane detection represents one of the core perception capabilities required by autonomous vehicles.

This project combines image processing, geometric reasoning, and real-time computer vision techniques to transform raw camera data into actionable information about road structure and vehicle positioning.

It illustrates the transition from basic computer vision techniques toward the more sophisticated perception pipelines used in modern autonomous systems.

---

## Acknowledgements

Developed as part of the Udacity Self-Driving Car Engineer Nanodegree.

Original project framework provided by Udacity. Implementation, experimentation, analysis, and project report completed as part of the program.
