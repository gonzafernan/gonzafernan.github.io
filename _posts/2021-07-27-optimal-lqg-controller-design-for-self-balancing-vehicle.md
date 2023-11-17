---
layout: post
title: Optimal LQG controller design for self-balancing vehicle
date: 2021-07-27 18:14 -0300
author: gfernandez
categories: [Projects]
tags: [robotics, control, matlab]
---

## Summary
Formulation of a mathematical model of a self-balancing two-wheeled vehicle.
Implementation of mechanical model in Simscape Multibody with 3D visualization.
Design of linear quadratic Gaussian LQG controller, combination of linear 
quadratic regulator LQR and linear quadratic observer (Kalman filter), for 
stabilization and tracking of translation setpoints.
Controller performance analysis for initial angles different from 0 and thrust 
forces on the vehicle.

- **Github repository:** [gonzafernan/self-balencing-lqg](https://github.com/gonzafernan/self-balancing-lqg)
- **Technologies:** Matlab/Simulink.

![](/assets/img/reference_lqr.gif)

## XIX Work Meeting on Information Processing and Control (RPIC)

{% include embed/youtube.html id='03BDdzO6KVY' %}

## Report

Link to PDF: [Optimal LQG controller design for self-balancing two-wheeled vehicle stabilization](https://github.com/gonzafernan/gonzafernan.github.io/blob/main/assets/pdf/self_balancing_lqg_control.pdf)

<center> 
    <object data="/assets/pdf/self_balancing_lqg_control.pdf"
            width="100%"
            height="700"> 
    </object> 
</center>

## LQG controller design process with MATLAB & Simulink®
**Control requirements:** follow a sinusoidal position reference with an 0.5m amplitude and 15s period remaining stable. 
The tolerance allowed is 1s in time and 10cm in position.

**Formulation of plant model:**
- Euler-Lagrange equations
- Non-linear model state-space representation
- Non-linear model linearization around a fixed point
- LTI model state-space representation
- Sensor modeling: Quadrature encoder and IMU (Ref. MPU6050) with gyroscope and accelerometer

**Full-state feedback design:** 
- Controllability analysis
- Manual pole placement
- Linear Quadratic Regulator (LQR) design
- Non-minimal phase system analysis

**Full-state estimator design:** 
- Observability analysis
- Manual estimator's pole placement
- Linear Quadratic Estimator (Kalman filter) design

## Mechanical model with Simscape Multibody™
In order to have a more reliable simulation, a mechanical model of the robot was implemented with Simscape Multibody™ (formerly SimMechanics™)  which provides a multibody simulation environment for 3D mechanical systems.

An automatically generated 3D animation provides a visualization of the system's dynamic.

| Following reference (LQR) | Disturbance rejection (LQR) |
|:-------------------------:|:---------------------------:|
|![](/assets/img/reference_lqr.gif)|![](/assets/img/disturbance_lqr.gif)|

An interesting feature of this model is the wheel-floor contact model by using the external *Simscape Multibody Contact Forces Library*. The contact is modeled as a *sphere to plane force* and, as a small disclaimer, it's working but with a different behavior from the previous analysis. It's neccesary to tune the different parameters to make it works as supposed: Contact stiffness, contact damping, static and kinetic friction, etc. (If you find the parameters to make it works please make a pull request!).
