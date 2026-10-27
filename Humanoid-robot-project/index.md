---
layout: page
title: RoboCup Major Teen-Size Humanoid Robot
permalink: /Humanoid-robot-project/
---

Bachelor’s thesis • B.Sc. Mechanical Engineering, AASTMT, 2020 • team project • Role: project lead • grade 1.0 • Thesis available on request

Our team redesigned a teen-sized humanoid, in which I assisted with the FEA, modelled its kinematics and dynamics, and validated the full robot walk in physics simulation with a ZMP-based model predictive controller. The lower body prototype was built and assembles however COVID-19 restrictions hindered the hardware walking tests.

![Designed robo CAD, walking controller, Simscape walking simulation, built lower body prototype](/Assets/humanoid/pipeline.png)

## Problem

The team took over a RoboCup prototype with broken links and a high center of mass, problems that needs addressing in the design, material, and joint torques. The goal was a humanoid robot possessing efficient mechanical design and FEA, dynamically stable walking control and perception, all of which were designed together and verified in simulations before hardware tests.

## Approach

- **Mechanics**: links redesigned in SolidWorks, finite element analysis of 12 components under dynamic loads.
- **Kinematic**: Denavit-Hartenberg models, forward and inverse kinematics for the 6-DoF legs and 3-DoF arms, joint-trajectory planning.
- **Walking control**: a model predictive controller on a liner inverted pendulum (cart-table) model tracks a zero moment point (ZMP) reference, Stateflow stepping logic and leg inverse kinematics produce joint angles.
- **Simulation and ROS**: CAD to Simscape Multibody, and as URDF to Gazebo, MATLAB-ROS interfaces.
- **Perception**: Python/OpenCV webcam pipeline (HSV segmentation, contours, shape cues) for balls and field lines.

The ZMP is the point on the ground about which gravity and the robot’s own accelerations create no tipping moment. While it stays inside the area covered by the supporting foot, the robot does not tip over. The controller plans the body motion so that this point moves along a safe path from foot to foot.

## Results

- The full robot walked stably in Simscape Multibody, first with a predetermined gait and then with ZMP/MPC-generated foot trajectories.
- Knee and hip-roll joints carried the highest simulated torques, which stayed below the servo limits (8.4 Nm and 6.0 Nm).
- The lower body prototype was built and assembles, and MATLAB-ROS interface set up for publishing the joint actuator signals for hardware testing.

## Limitations

Walking was shown only in simulation, on flat ground and without significant interruptive disturbances. The upper body prototype was not built, and ROS control was not tested on hardware.

## My role
Project lead: I coordinated the team through the COVID-19 lockdown. My technical work: kinematics and trajectory planning, ZMP gait generation, state-space and MPC controllers, Simscape validation, OpenCV perception and MATLAB-ROS interfaces. I assisted with the FEA. Mechanical design and manufacturing were shared team work.

## More images

![Manufactured lower body prototype](/Assets/Prototype-lowerbody.png)

![CAD design, front and side views](/Assets/Final-design.png)
