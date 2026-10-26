---
layout: page
title: Home
permalink: /
---

# Mena Karam

**Robotic perception and 3D computer vision** 

M.Sc. Automation and Robotics, TU Dortmund (grade 1.4) | B.Sc. Mechanical Engineering, AASTMT (grade 1.0) | Dortmund, Germany

My work focuses on Physically-grounded visual perception, modeling how an image is formed (optics, defocus and motion blur, sensor limits) and integrating such a model in 3D reconstruction and robotic perception. I evaluate methods by the geometric downstream results rather than the visual quality of the images.

My research interest lies at the intersection of robotic perception, geometric reconstruction, and robot control. In particular, model-based and learning-based robotic perception methods.

[CV](https://eerie-cosmos.github.io/Assets/CV.pd) | [Research portfolio (PDF)](https://eerie-cosmos.github.io/Assets/docs/Research-portfolio.pdf) | [GitHub](https://github.com/eerie-cosmos) | Emails: mena0karam00@gmail.com and mena.karam@tu-dortmund.de

---

## Research

### Coupled Deblurring and 3D Reconstruction from Image Sequences
Master’s thesis, TU Dortmund, 2025 | supervisor Prof. Dr. Christian Wöhler

![Defocused image, plane of focus alignment, CoC values visualized](/Assets/master-thesis/thumb.jpg)

The microscopic camera CAM-M, mounted on the lunar rover Rashid-1 for close up image acquisition of the lunar regolith surface, has no refocus mechanism, resulting in a shallow depth of field that produce image with defocus blur and in turn reduced number of feature correspondences. The 3D reconstruction of a sequence of those overlapping defocused images can provide how much each pixel have deviated from the plane of focus which can be used to estimate blur and restore images sharpness. Images are deblurred using this geometry-derived, spatially varying blur model in Wiener filter and Richardson-Lucy deconvolution producing a 3D reconstruction with a significantly increased areal point density and thus a much higher spatial resolution than the initial 3D reconstruction. The developed method was successfully applied to CAM-M image sequences taken during a lunar rover test drive at the MBRSC.
**[Project page](/master-thesis/)** | [1-page abstract (PDF)](/Assets/docs/Master-thesis-abstrac—1p.pdf) | [2-page summary (PDF)](/Assets/docs/Master-thesis-summary-2p.pdf)

### 3D Models of Planetary Surfaces in Virtual Reality
M.Sc. project group, TU Dortmund, 2022, Role: rover-image photogrammetry pipeline

![3D model of Mars rock](/Assets/mars-vr/thumb.jpg)

Multi-view and Multi-camera Uncalibrated Perseverance imagery used for a textured 3D reconstruction of VR-ready model of the Cheiron Martian rock. The pipeline was based on uncalibrated stereo vision, SfM-MVS, and bundle adjustment concepts to generate dense point clouds from imagery acquired on the surface of Mars by
the NASA Perseverance rover. For the resulting multi-view 3D point cloud, data fusion, spatial alignment and stitching based on ICP and RANSAC techniques, as well as geometrical refinement were carried out for the reconstruction of 3D surface models integrated into an interactive, physics-enabled VR environment. The pipeline employed a variety of free and commercial programming environments, such as MATLAB, OpenCV, Agisoft Metashape Pro, OpenCV, MeshLab, CloudCompare, and Unity.
**[Project page](/mars-vr/)** | [1-page summary (PDF)](/Assets/docs/Mars-VR-project-summary.pdf)

### Robocup Major Teen-Size Humanoid Robot
Bachelor’s thesis, AASTMT, 2020 | team project, project lead

![Humanoid CAD and built lower body prototype](/Assets/humanoid/thumb.jpg)

Forward and inverse kinematics, ZMP-based gait generation with model-predictive control for dynamically stable walking gait. The method was validated in Simscape Multibodies simulation on MATLAB. ROS toolbox used to publish the simulated joint angles and speeds to the actuator. Prototype hardware implementation and testing halted due to COVID-19 restrictions. 
**[Project page](/Humanoid-robot-project/)** | [1-page summary (PDF)](/Assets/docs/Bachelor-thesis-summary/pdf)

### Ongoing: Active Photogrammetry
Address the research question of whether a robot view planner that models motion and defocus blur reach a target 3D accuracy faster than standard next-best-view planning. Incorporates: Calibration, SfM and bundle adjustment with covariance, implemented from first principles and tested against ground truth in MuJoCo.
status: in development

---

[All projects](/projects/) | [Methods and results](/methods/) | [CV](/cv/) | [Contact](/contact/)



