# Ratio Control System for a Blending Process

A MATLAB/Simulink project that designs and compares a **Ratio Control System** and an **Independent Flow Control System** for a blending process. The objective is to maintain a fixed composition between two inlet streams under varying flow disturbances and evaluate the performance of both control strategies.

---

## Problem Statement

Design and simulate a ratio control system for a blending process, where two inlet streams must maintain a fixed composition despite flow disturbances, and compare its performance with independent flow control loops.

---

## Overview

This project implements and compares two industrial control strategies:

- **Ratio Control**
- **Independent Flow Control**

using **MATLAB/Simulink**.

The simulation demonstrates that ratio control provides superior disturbance rejection, improved coordination between streams, and significantly lower steady-state error.

---

## Control Strategies

### 1. Ratio Control

- Stream 2 acts as the **Wild Flow**.
- Stream 1 is the **Controlled Flow**.
- The controller continuously maintains

```
Controlled Flow = Ratio × Wild Flow
```

using feedforward and feedback control.

### Features

- Feedforward disturbance compensation
- Automatic ratio maintenance
- Fast disturbance rejection
- Better composition accuracy

---

### 2. Independent Flow Control

Each stream is controlled independently using separate controllers.

Given

```
FB = FA × R
```

where

- FA = Flow of Stream 1
- FB = Flow of Stream 2
- R = Desired Ratio

Both loops operate independently without direct coordination.

---

## System Models

The project includes:

- Ratio Control Block Diagram
- Independent Flow Control Block Diagram
- Transfer Function Models
- MATLAB/Simulink Simulation

---

## Results

### Ratio Control

| Parameter | Value |
|-----------|------:|
| Wild Flow | 66.175 L/s |
| Controlled Flow | 330.795 L/s |
| Desired Flow | 330.900 L/s |
| Obtained Ratio | 4.999 |
| Desired Ratio | 5.000 |

---

### Independent Flow Control

| Parameter | Value |
|-----------|------:|
| Flow 1 | 490.50 L/s |
| Flow 2 | 99.29 L/s |
| Obtained Ratio | 4.912 |
| Desired Ratio | 5.000 |
| Steady-State Error | 0.088 (1.76%) |

---

## Performance Comparison

| Feature | Ratio Control | Independent Flow Control |
|----------|---------------|--------------------------|
| Ratio Accuracy | Excellent | Moderate |
| Disturbance Rejection | Excellent | Limited |
| Steady-State Error | ~0.02% | 1.76% |
| Stream Coordination | Automatic | Independent |
| Composition Control | Highly Accurate | Less Accurate |

---

## Discussion

### Accuracy

Ratio Control achieved an output ratio of **4.999**, extremely close to the desired ratio of **5.000**, with an error of only **0.001 (0.02%)**.

Independent Flow Control achieved a ratio of **4.912**, corresponding to a **1.76% steady-state error**.

---

### Disturbance Rejection

Ratio Control continuously updates the controlled stream according to changes in the wild flow, resulting in excellent disturbance rejection.

Independent Flow Control relies solely on feedback, causing slower correction and temporary deviations from the desired ratio.

---

### Dynamic Response

Ratio Control synchronizes both streams automatically, minimizing phase lag and overshoot.

Independent controllers operate separately, leading to transient mismatch during disturbances.

---

### Industrial Significance

Ratio Control is widely used in:

- Chemical blending
- Fuel mixing
- Pharmaceutical manufacturing
- Food processing
- Process industries

where maintaining product composition is critical.

---

## Challenges Faced

- Handling sudden flow disturbances
- Valve saturation (control signal limited to 0–1)
- Nonlinear valve characteristics
- Limited operating range
- Accurate model linearization
- Controller tuning under actuator constraints

---

## Future Improvements

- Implement Cascade Control for improved disturbance rejection.
- Develop a Total Flow + Ratio (2-DOF) control structure.
- Introduce Adaptive Feedforward (Gain Scheduling).
- Replace PID with IMC-based controller tuning.
- Extend the system using Model Predictive Control (MPC) for multivariable optimization.

---

## Tools & Technologies

- MATLAB
- Simulink
- PID Controllers
- Ratio Control
- Feedforward & Feedback Control
- Process Control Systems

---

## Repository Structure

```
.
├── Simulink_Model/
├── Images/
├── Report/
├── Results/
└── README.md
```

---

## Team Members

| Name | Scholar ID |
|------|-----------|
| Raushan Kumar | 2315027 |
| Varanasi Anand Bharadwaj | 2315051 |
| Aishwarya Shukla | 2315057 |
| Faruk Ahmed | 2315058 |
| Narendra Kumar Gupta | 2315066 |

---

## License

This project was developed as part of a **Process Control** academic coursework and is intended for educational purposes.
