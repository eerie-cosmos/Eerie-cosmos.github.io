# Humanoid Robot: Design, Kinematic Modelling, and Simulation-Based Gait Evaluation

This project investigated how a humanoid robot can be designed and modelled so that planned walking motion is not only kinematically feasible, but also mechanically and dynamically credible. The work combined mechanical redesign, actuator-aware embodiment, forward and inverse kinematics, Zero-Moment Point-informed gait planning, and MATLAB/Simulink Simscape Multibody simulation.

My early interest in humanoid robotics was closely tied to the idea of using human-like embodied systems in environments that are hazardous, difficult to access, or operationally constrained. In retrospect, this project became an early foundation for a broader research direction that now centres on robotics perception, 3D computer vision, and physically grounded modelling for robotic action.

## Research focus

The central challenge was to study humanoid walking as a coupled problem of embodiment, kinematics, and balance-aware control rather than as geometric trajectory playback alone. Because a biped alternates between double-support and single-support phases, feasible locomotion must satisfy changing contact constraints while keeping body motion dynamically compatible with the support polygon.

## Technical contributions
- Redesigned a teen-sized humanoid platform to improve centre-of-mass placement, modularity, joint accessibility, and range of motion.
- Modelled the legs as six-degree-of-freedom serial chains and derived forward and inverse kinematics for trajectory generation.
- Used ZMP-based balance analysis to evaluate whether planned steps remained dynamically compatible with the support polygon.
- Simulated walking behavior in MATLAB/Simulink Simscape Multibody and analysed joint trajectories and torque demand.
- Assessed structural feasibility through finite-element analysis under representative loading cases.

## Methods

The leg kinematics were formulated using the Denavit–Hartenberg convention, and analytical inverse kinematics was used to recover joint configurations from desired foot trajectories. Walking primitives were then evaluated using the Zero-Moment Point criterion, linking CAD-based embodiment, kinematic modelling, gait planning, and multibody simulation into one integrated workflow.

## Results

The main outcome was the successful simulation of planned bipedal walking in Simscape Multibody using trajectories generated from the modelling and balance framework. A documented step example showed the Zero-Moment Point and floor projection of the centre of mass remaining within the support polygon during the planned motion, while torque plots were used to compare simulated joint demand against actuator capability.

Structural verification was performed through SolidWorks finite-element analysis, which supported claims about mechanical feasibility but should be distinguished from dynamic walking validation. Physical walking experiments on the fabricated prototype were not completed because laboratory access was disrupted during the COVID-19 period.

## Selected visuals

![Fabricated lower-body prototype](./Assets/Prototype-lowerbody.png)

*Fabricated lower-body humanoid prototype developed as a modular bipedal platform for gait modelling and simulation-based evaluation.*

![CAD design, front and side views](./Assets/Final-design.png)

*Final humanoid design showing the embodied platform used for kinematic modelling, actuator allocation, and gait-planning studies.*

![MATLAB control block diagram](./Assets/Gait-control-pipeline.png)

*Control and simulation workflow linking ZMP-based planning, linear inverted-pendulum modelling, stepping logic, and inverse kinematics for bipedal gait generation.*

![Simscape walking simulation](./Assets/Simscape-walking.png)

*Simscape Multibody model used to evaluate full-body walking behaviour generated from the planned gait pipeline.*

## Research direction

This page presents the project as an integrated humanoid-robotics and control project, while my Master’s-thesis and planetary-reconstruction work establish the deeper perception-and-geometry side of my research profile. Across these projects, the common direction is physically grounded robotic reasoning in which geometric or dynamical models provide the backbone, while learning-based methods refine aspects that cannot easily be specified from first principles.







