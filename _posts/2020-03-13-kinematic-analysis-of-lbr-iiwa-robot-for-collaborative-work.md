---
layout: post
title: Kinematic analysis of LBR iiwa robot for collaborative work
date: 2020-03-13 22:39 -0300
authors: [gavanzini, gfernandez, jpino]
categories: [Projects]
tags: [robotics, matlab]
---

## Summary

Kinematic analysis of the LBR iiwa manipulator robot of the manufacturer KUKA, with the objective of its implementation in collaborative and cooperative tasks within a work environment related to chemical laboratories, where hazardous materials are handled, or procedures are performed in an environment harmful to humans.

The Robotics, Vision & Control toolbox developed by Peter Corke for MATLAB was used as a simulation tool.

- Modeling of the kinematic chain of the robot following the Denavit-Hartenberg convention and its application in the calculation of direct kinematics.
- A possible method for the calculation of the inverse kinematics of the robot is proposed, taking into account its kinematic redundancy. This method consists of a combination of the geometric and algebraic methods by applying Pieper's method for robots with spherical motion. 
- A criterion for the determination of the third joint is proposed in order to reduce the infinite number of solutions to a finite number. This criterion is based on the optimization of the manipulability of the robot in the direction of motion.
- A comment on the procedure to find a velocity relation between joint and task space is made, and the mathematical singularities of the structure are studied analytically.
- The trajectory generation is discussed, and the results obtained in a simulation for 2 robots collaborating to perform a specific task are shown.

| Schematic from specification | Model with RVCtools toolbox by Peter Corke |
|------------------------------|--------------------------------------------|
| ![](/assets/img/kuka_iiwa-schematic.png) | ![](/assets/img/kuka_iiwa-model.png) |

![](/assets/img/kuka_iiwa-singularity.png)

- **Github repository:** [GinoAvanzini/iiwa-kinematics](https://github.com/GinoAvanzini/iiwa-kinematics)
- **Programming language:** Matlab

## Report

Link to PDF: [Kinematic analysis of LBR iiwa robot for collaborative work](https://github.com/GinoAvanzini/iiwa-kinematics/blob/master/ProyectoRobotica.pdf)

<center> 
    <object data="/assets/pdf/kuka_iiwa_analysis.pdf"
            width="100%"
            height="700"> 
    </object> 
</center>