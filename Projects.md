---
layout: page
title: Projects
permalink: /projects/
---

# Selected Projects

My work has progressively converged to physically grounded robotics perception, geometric 3D vision, and model-based control, with particular interest in systems where explicit geometric or dynamical structure is combined with learning where needed.

## Coupled Deblurring and 3D Reconstruction from Image Sequences

**Institution:** TU Dortmund University  
**Project type:** Master’s thesis

This thesis investigated how spatially varying defocus blur in microscopic image sequences can be modelled and compensated in a physically grounded manner to improve downstream 3D reconstruction. The work was motivated by close-range microscopic imagery of lunar regolith simulant acquired with the CAM-M camera during rover-related ground testing, where shallow depth of field degraded feature correspondence and reduced the density and completeness of bundle-adjustment-based reconstruction.

The developed pipeline explicitly coupled optical image formation with geometric reconstruction rather than treating restoration and 3D recovery as independent stages. It estimated a scene plane of sharpness, modelled defocus through the circle of confusion, derived a spatially varying point spread function, and applied location-dependent deconvolution using Wiener and Richardson–Lucy methods before repeating the reconstruction step on the restored imagery.

This physically informed treatment of image degradation led to denser and more spatially informative 3D point clouds than the initial reconstruction, demonstrating how sensing limitations propagate into later geometric representation quality. More broadly, the project reflects a continuing research interest in physically grounded perception, particularly in settings where optical effects, scene geometry, and reconstruction performance are tightly coupled.

**Methods and tools:** Optical defocus modelling, plane-of-focus estimation, spatially varying PSF modelling, Wiener filtering, Richardson–Lucy deconvolution, Python-supported SfM/MVS in Agisoft Metashape Pro, geometric comparison, and point-cloud density-map analysis.

**Code and data:** Source code is not publicly released at present. This page documents the scientific motivation, methodology, and representative outcomes of the work.

---

## 3D Models of Planetary Surfaces in Virtual Reality

**Institution:** TU Dortmund University  
**Project type:** Research-oriented student group project

This project examined how multi-view rover imagery can be transformed into geometrically meaningful 3D terrain models for analysis, inspection, and spatial interpretation. Using image data acquired by NASA’s Perseverance rover, the work addressed planetary-surface reconstruction under realistic geometric and imaging constraints, with emphasis on the relationship between image formation, camera geometry, and downstream spatial representation.

The reconstruction workflow combined calibrated and uncalibrated stereo vision, structure from motion, bundle adjustment, multi-view stereo, dense point-cloud generation, registration, and geometric refinement. The resulting terrain models were subsequently integrated into a Unity-based virtual-reality environment to support interactive inspection and interpretation of reconstructed planetary scenes.

Beyond the immediate reconstruction outcome, the project extended an ongoing research thread from fine-scale microscopic reconstruction to terrain-scale geometric modelling and mapping-oriented representation. It strengthened my interest in perception pipelines that combine image-based inference with explicit geometric structure, particularly where 3D models serve as intermediate representations for later robotic reasoning, navigation, or interaction.

**Methods and tools:** Stereo geometry, structure from motion, bundle adjustment, dense reconstruction, point-cloud registration and refinement, MATLAB, Agisoft Metashape Pro, OpenCV, CloudCompare, MeshLab, and Unity.

**Code and data:** Project code is not publicly released. This page provides a summary of the workflow, methods, and representative visual outcomes.

---

## Teen-Sized Humanoid Robot: Modeling and Control

**Institution:** AASTMT  
**Project type:** Bachelor’s thesis

This thesis focused on the modelling and control of a RoboCup teen-sized humanoid robot, with emphasis on articulated-body kinematics, gait generation, and stability-aware locomotion. The project originated from an early interest in human-like embodied systems for operation in environments that are hazardous, difficult to access, or otherwise constrained for direct human presence, and it remains foundational to my later research interests in robotics perception, control, and embodied intelligence.

The work included forward and inverse kinematics, joint-trajectory generation, ZMP-based gait planning, state-space control design, model-predictive-control concepts, multibody simulation, and a ROS/Gazebo integration path using MATLAB’s robotics and ROS toolboxes. Particular attention was given to physically meaningful modelling choices, including embodiment, balance, support constraints, and the relationship between kinematic structure and dynamically informed walking behaviour.

Although final hardware validation was limited by pandemic-related laboratory restrictions, the modelling, control, and simulation workflow was developed in full. The project established a strong foundation in embodiment-aware robot design and locomotion control, and it continues to inform my interest in systems where geometric or dynamical structure provides the backbone and learning-based components refine the aspects that are difficult to specify from first principles.

**Methods and tools:** Forward and inverse kinematics, joint-trajectory generation, ZMP-based gait planning, state-space control, model-predictive control, MATLAB, Simulink, Simscape Multibody, Robotics Toolbox, ROS Toolbox, and ROS/Gazebo.

**Code and data:** Project source code is not publicly released. A concise technical summary and visual documentation are provided instead.

---

## Omniwheel Robot: Embedded Perception and Closed-Loop Control

**Institution:** AASTMT  
**Project type:** Robotics applied systems project

This project addressed the integration of heterogeneous sensing, actuation, and embedded communication within an omnidirectional mobile robotic platform. The central objective was to build a responsive closed-loop system in which perception, control, and hardware interfacing were treated as parts of a single robotic architecture rather than as isolated subsystems.

The work involved omnidirectional wheel modelling, motor actuation through PWM control, and the integration of encoder, ultrasonic, infrared, magnetic, and camera signals in a real embedded-robotics setting. It also required communication and systems interfacing through channels such as UART and SPI, alongside practical handling of noisy measurements, feedback loops, and low-level control behaviour.

This project was especially formative in developing intuition for how robotic behaviour emerges from the interaction between sensing constraints, actuation limits, and embedded implementation details. In retrospect, it forms an early systems-level counterpart to my later work in perception and estimation, and it remains relevant to research directions that require tight coupling between real-world sensing, control, and task execution.

**Methods and tools:** Mobile-robot kinematics and dynamics, closed-loop control, multi-sensor system integration, PWM motor actuation, embedded communication, and platform-level robotics implementation.

**Code and data:** Public code is not currently provided. The page emphasizes the platform architecture, sensing chain, and control logic.

---

## UR10 Motion Control in ROS

**Institution:** TU Dortmund University  
**Project type:** Master’s robotics course project

This project focused on model-based manipulator motion generation and execution for the Universal Robot UR10 within a ROS-based simulation and control environment. It combined inverse kinematics, task-space to joint-space transformation, and controller-compatible trajectory execution in a workflow spanning MATLAB, Gazebo, RViz, and ROS communication interfaces.

The implementation involved numerical inverse kinematics, point-to-point and multi-waypoint trajectory generation, ROS publishers and subscribers, and action-based controller execution with feedback and monitoring. A key aspect of the project was the translation of end-effector pose objectives into feasible joint-space motion while maintaining a clear connection between kinematic reasoning, motion specification, and executable control commands.

The project strengthened my manipulation-oriented systems background and reinforced a research direction centered on physically grounded perception and estimation for robotics, especially in settings where geometric or dynamical models define the core structure and learned components can later be incorporated in a principled way. It also provided a useful bridge between perception-oriented interests and action-oriented robot control.

**Methods and tools:** Numerical inverse kinematics, joint-space trajectory generation, Gazebo simulation, RViz visualization, ROS topics, ROS actions, feedback monitoring, and controller interfaces.

**Code and data:** This was a graded academic project. Representative documentation is presented here instead of a full public code release.
