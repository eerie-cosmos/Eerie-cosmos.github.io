---
layout: page
title: Projects
permalink: /projects/
---

# Selected Projects

## Coupled Deblurring and 3D Reconstruction from Image Sequences

**Institution:** TU Dortmund University  
**Project type:** Master’s thesis

### Research question
How can spatially varying image blur in microscopic imagery be modeled and compensated for in a physically grounded manner so that downstream 3D reconstruction becomes denser, more complete and spatially informative?

### Context
The thesis addressed image sequences acquired using the CAM-M microscopic camera of lunar regolith simulant during a lunar rover-related ground testing. In such close-range imaging of non-flat regolith surfaces, shallow depth of field causes some regions to appear sharp and others blurred. This affects feature matching and reduces the quality and density of the resulting 3D reconstruction based on bundle adjustment.

### Contribution
The work developed and evaluated a reconstruction pipeline that linked optical image formation model and geometric reconstruction rather than treating them as separate stages. The method estimated a plane of sharpness in the scene, inferred defocus blur through the circle of confusion, translated that into a location-dependent point spread function, and then applied spatially varying deconvolution using Wiener and Richardson–Lucy approaches before repeating the reconstruction step with the resulting restored images.

### Methods and tools
- Optical defocus modeling based on real-aperture camera model
- Sharp areas estimation and plane-of-focus reasoning
- Spatially varying point spread function modeling
- Wiener filtering and Richardson–Lucy deconvolution
- Python-supported SfM/MVS reconstruction in Agisoft Metashape Pro
- Geometric comparison and point cloud density maps analysis

### Outcome
The method improved the areal point density and spatial resolution of the reconstructed 3D point clouds relative to the initial reconstruction, showing how image degradation directly affects downstream geometric representation quality.

### Research relevance
This project is representative of a broader research interest in physically grounded perception: understanding how sensing limitations propagate into later geometric, spatial, and robotic decisions.

### Code and data
Source code is not publicly released at present. This page documents the scientific motivation, methodology, and representative outcomes of the work.

---

## 3D Models of Planetary Surfaces in Virtual Reality

**Institution:** TU Dortmund University  
**Project type:** Research-oriented student group project

### Research question
How can multi-view rover imagery be turned into geometrically meaningful 3D terrain models that support analysis, inspection, and spatial interpretation?

### Context
The project used image data acquired by NASA’s Perseverance rover to reconstruct planetary terrain surfaces under realistic imaging and geometric constraints.

### Contribution
The work involved building and refining a 3D reconstruction workflow based on calibrated and uncalibrated stereo vision, structure from motion, multi-view stereo, bundle adjustment, dense point-cloud generation, geometric alignment, and refinement. The resulting terrain models were then integrated into a Unity virtual-reality environment for interactive spatial inspection.

### Methods and tools
- Stereo geometry
- Structure from motion
- Bundle adjustment
- Dense point-cloud generation
- Point cloud registration and refinement
- MATLAB Agisoft Metashape Pro, OpenCV, CloudCompare, MeshLab, Unity

### Outcome
The project produced usable terrain reconstructions and demonstrated the link between image-based geometry, spatial representation, and downstream interpretation.

### Research relevance
This project extends the same research thread from microscopic reconstruction to terrain-scale geometric modeling and mapping-related representation.

### Code and data
Project code is not publicly released. This page provides a summary of the methods, workflow, and visual outcomes.

---

## Teen-Sized Humanoid Robot: Modeling and Control

**Institution:** AASTMT  
**Project type:** Bachelor’s thesis

### Research question
How can a teen-sized humanoid platform be modeled and controlled to produce coordinated, dynamically informed biped legged locomotion?

### Context
The project focused on the modeling and control of a RoboCup teen-sized humanoid robot, with attention to articulated-body kinematics, gait generation, motion planning, and stability-aware control.

### Contribution
The work included forward and inverse kinematics, joint-trajectory generation, ZMP-based gait generation, state-space control design, model-predictive control concepts, multibody simulation, and ROS/Gazebo integration path with MATLAB’s ROS toolbox. Final hardware validation was limited by pandemic laboratory restrictions, whereas the modeling and control workflow was fully developed.

### Methods and tools
- Forward and inverse kinematics
- Joint-trajectory generation
- ZMP-based gait planning
- State-space and Model-predictive control
- MATLAB, Simulink, Simscape Multibodies, Robotics Toolbox, ROS Toolbox, ROS/Gazebo

### Outcome
The project established a complete articulated-control workflow and provided strong foundations in embodiment-aware robot modeling and locomotion control.

### Research relevance
It connects perception-oriented work with full-body robotic control and supports later interests in locomotion, planning, and environment-aware robot behavior.

### Code and data
Project source code is not publicly released. A concise technical summary and visual documentation are provided instead.

---

## Omniwheel Robot: Embedded Perception and Closed-Loop Control

**Institution:** AASTMT  
**Project type:** Robotics applied systems project

### Research question
How can an omnidirectional wheeled robot integrate heterogeneous onboard sensing and actuation into a responsive closed-loop control system?

### Context
This project involved an omniwheel RoboCup robot operating with multiple sensing and actuation channels in a real embedded-robotics setting.

### Contribution
The work included omnidirectional wheel modeling, multi-sensor integration using encoder, ultrasonic, infrared, magnetic, and camera signals, motor control via PWM, and embedded communication through interfaces such as UART and SPI.

### Methods and tools
- Mobile-robot kinematics and dynamics
- Closed-loop control
- Multi-sensor fusion at system level
- PWM motor actuation
- Embedded communication and integration

### Outcome
The project provided practical experience with noisy sensing, feedback loops, actuator control, and full-system embedded robotics.

### Research relevance
It demonstrates hands-on understanding of how robotic perception, control, and hardware interact beyond simulation-only environments.

### Code and data
Public code is not currently provided. The page emphasizes the platform architecture, sensing chain, and control logic.

---

## UR10 Motion Control in ROS

**Institution:** TU Dortmund University  
**Project type:** Master’s robotics course project

### Research question
How can a manipulator’s motion be formulated and executed in a ROS-based simulation and control framework using inverse kinematics and trajectory control?

### Context
The project focused on simulation and control of the Universal Robot UR10 within ROS, Gazebo, RViz, and MATLAB-based interfaces.

### Contribution
The work involved numerical inverse kinematics, task-space and joint-space reasoning, point-to-point and waypoint trajectory generation, ROS publishers and subscribers, and action-based trajectory execution through controller interfaces.

### Methods and tools
- Numerical inverse kinematics
- Joint-space trajectory generation
- Gazebo simulation
- RViz visualization
- ROS topics, actions, feedback, and controller interfaces

### Outcome
The project strengthened manipulation-oriented systems knowledge and practical familiarity with ROS-based robot control workflows.

### Research relevance
It supports later work in manipulation, planning, and robot-system integration.

### Code and data
This was a graded academic project. Representative documentation is presented here instead of a full public code release.
