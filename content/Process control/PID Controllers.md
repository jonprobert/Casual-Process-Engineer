---
tags:
  - ProcessControl
---
# PID controllers

> [!info] Related
> - [[PID controller tuning]]

A controller compares a measured process variable to a setpoint, and based on the error between them, generates a correction signal to be sent to a final element (i.e. a control valve) to eliminate the error.

> [!NOTE] Standard/series vs Parallel forms of controller
> PID controllers come in three forms: series (interactive), standard (non-interactive), and parallel. External [link](https://blog.opticontrols.com/archives/124) for further reading.
> 
> Note that the output equations below are the standard forms of the controllers. Most PID tuning rules, including the [[PID controller tuning#Ziegler-Nichols tuning method|Ziegler-Nichols]], [Cohen-Coon](https://blog.opticontrols.com/archives/383) and [Lambda](https://blog.opticontrols.com/archives/260) tuning rules were designed for this form. In the standard form the "Controller Gain" ($K_C$) affects all three modes.
> 
> Many academic textbooks discuss only the parallel form of PID controller, and don’t mention the others. This is where the proportional, integral, and derivative gains only affect their own control mode. Simpler to understand but not intuitive to tune. 

## Overview of control types[^1]

Some controller types are on/off, floating, proportional (P),  integral (I), and differential (D). Control loops often use a combination of these types.

### On/off control

The oldest and simplest type of control where an output is "on" with a positive error and "off" with a negative error. Often includes hysteresis; an intentional delay between turning the controller on and off to prevent rapid switching.
### Floating

This controller allows the input signal to float in a dead zone without taking any action. When outside the dead zone the output signal can be increase or decreasing at a constant rate. This reduces wear and tear by avoiding cycling and making small corrections initially.
### Proportional (P)

Examines and acts on the present state of the error.

Simple linear control with a constant relationship between input/output where output is proportional to the present error.
  $$m=K_ce+b$$
  Where:
  - $m$ is the output signal
  - $K_c$ is the gain of the controller
  - $e$ is the error (deviation from the setpoint)
  - $b$ is the "live zero" or bias of the output (e.g. 4mA for analogue loops)

The main limitation of proportional only control is that it cannot keep a controlled variable on set point due to proportional offset, instead stabilising with a small, steady error (the system needs some error to maintain an output). Offset can be reduced by increasing the gain. However many processes become unstable with high $K_c$ 

### Integral (I)

Examines and acts on the the past history of the error.

The integral mode eliminates proportional offset by accounting for past history of the error (seldom used alone).

$$m = \frac{1}{T_i} \int e \, dt + b$$
Where:
- $T_i$ is integral time or reset time (often as repeats/minute in DCS systems). In PI controllers this is the time taken for the controller output to change by the same amount as the proportional gain. Sometimes this is expressed as integral gain $K_i=\frac{1}{T_i}$.

A combined proportional plus integral (PI) controller where the integral element has been introduced to eliminate the offset that a plain proportional controller cannot remove:

$$m = K_c \left[ e + \frac{1}{T_i} \int e \, dt \right] + b$$

PI is the most widely used control mode configuration.

#### Integral windup protection

Integral windup occurs in a PI or PID controller when the integral term accumulates excessively because the controller output is limited (saturated) (i.e. a control valve fully open or heater at 100% duty etc). Error continues to be integrated, increasing the integral term. Once the error starts decreasing, the integral term is still large, causing an overshoot and a slow recovery once the system comes back within range.

**Example Scenario**

- A heating system with a PI controller is set to 22°C.
- On a cold day, the heater runs at 100% but the room takes time to warm up.
- During this time, the integral term keeps accumulating, expecting more correction.
- When the room reaches 22°C, the heater should reduce power, but due to windup, it stays too high and overshoots, making the room too hot.

Provide an anti-reset windup feature which protects the controller from saturating. There are different ways to combat this:

- Stop integrating when the output is saturated and Resume integration only when the output comes back within the allowable range.
- Adjust the integral term based on the difference between the actual actuator position and the controller output. Helps bring the controller back to normal operation quickly after saturation.
- Limit the maximum value of the integral term to prevent excessive accumulation.

### Differential (D)

Examines and acts on the anticipated future values of the error.

The derivative element is added in processes with high inertia that cause slow performance such as temperature or composition control, where the derivative action accelerates the response of the control loop.

The derivative contribution is based on the rate at which error is changing (here for a PD mode controller):

$$m = K_c \left[ e + T_d \frac{d}{dt} e \right] + b
$$
Where:
- $T_d$ is derivative time, the length of time by which the D-mode looks into the future.

PID control is more widely used than PD.

### Summary of mathematical descriptions of the conventional control modes[^1]

#### One mode

| **Symbol** | **Description**  | **Mathematical Expression**      |
| ---------- | ---------------- | -------------------------------- |
| P          | Proportional     | $m = K_c e + b$                  |
| I          | Integral (reset) | $\frac{1}{T_i} \int e \, dt + b$ |

#### Two mode

| **Symbol** | **Description**              | **Mathematical Expression**                                 | Uses                                          |
| ---------- | ---------------------------- | ----------------------------------------------------------- | --------------------------------------------- |
| PI         | Proportional-plus-integral   | $m = K_c \left[ e + \frac{1}{T_i} \int e \, dt \right] + b$ | Flow control, pressure control, level control |
| PD         | Proportional-plus-derivative | $m = K_c \left[ e + T_d \frac{d}{dt} e \right] + b$         |                                               |

#### Three mode

| **Symbol** | **Description**                            | **Mathematical Expression**                                                      | Uses                                                                                                                                              |
| ---------- | ------------------------------------------ | -------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| PID        | Proportional-plus-integral-plus-derivative | $m = K_c \left[ e + \frac{1}{T_i} \int e \, dt + T_d \frac{d}{dt} e \right] + b$ | - Systems with inertia that could get out of hand: i.e. temperature and concentration measurements on a reactor to avoid runaway.<br>- pH control |

[^1]: Instrument Engineers' Handbook - Volume 2 Process Control and Optimisation - Bela G. Liptak
