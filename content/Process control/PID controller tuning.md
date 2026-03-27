---
tags:
  - ProcessControl
---
# PID controller tuning

> [!info] Related
> - [[PID Controllers]]

PID (Proportional-Integral-Derivative) controller tuning is the process of adjusting the three control parameters—[[PID Controllers#Proportional (P)|proportional (P)]], [[PID Controllers#Integral (I)|integral (I)]], and [[PID Controllers#Differential (D)|derivative (D)]] gains—to ensure the controller responds effectively to changes in the system. The goal is to achieve optimal control performance, balancing stability, speed, and accuracy while minimising overshoot, oscillation, and steady-state error.

PID controllers can be tuned manually or using various systematic methods, including:

- [[PID controller tuning#Manual tuning hints|Trial and Error]] – Adjusting parameters iteratively based on system response.
- [[PID controller tuning#Ziegler-Nichols tuning method|Ziegler-Nichols Method]] – A heuristic approach that provides a good starting point for tuning. ^d161eb
- Cohen-Coon Method – Suitable for first-order lag systems with dead time.
- Auto-Tuning – Many modern controllers feature automatic tuning algorithms that adjust parameters based on system behaviour.

> [!info]- Additional info on disturbances
> A controller's primary function is to maintain a controlled variable as close as possible to its set point. Disturbances arise from set point changes, load variations, and noise. Noise, being a high-frequency random disturbance, cannot be corrected by the controller and may instead be amplified. Controllers tuned for set point changes respond sluggishly to load disturbances, while those optimised for disturbance correction tend to overshoot when the set point is adjusted. In continuous process plants, most control loops function as regulators, maintaining a stable set point for extended periods.
> 
> Examples of variables held at constant set points include pressure and level variables, pH control, product-quality variables, and most temperature loops. These loops primarily manage load disturbances rather than set point changes, except for flow loops, which frequently adjust their set points. Batch plants, however, undergo frequent state transitions, requiring rapid response to set point changes with minimal overshoot. Large set point changes—especially at startup—can saturate the controller, leading to [[PID Controllers#Integral windup protection|integral windup]].
> 
> Load variations, caused by changes in flow rates entering and leaving process vessels are a key challenge in continuous processes. For instance, a liquid-level controller regulates the flow of one stream while other streams represent the load. In temperature control, load represents the heat flow required to maintain temperature, and fluctuations in liquid flow or inlet temperature alter the demand for steam flow, requiring constant adjustment to keep the exit temperature stable.

## Manual tuning hints

Ref[^1]

- If it overshoots a lot and oscillates, either the integral gain (I) needs to be increased or all gains (P,I,D) should be reduced
- Too much overshoot? Increase D, decrease P.
- Response too damped? Increase P.
- Ramps up quickly to a value below target value and then slows down as it approaches target value? Try increasing the I constant.

## Ziegler-Nichols tuning method

Section to be expanded based on Instrument Engineers' Handbook - Volume 2 Process Control and Optimisation - Bela G. Liptak. For now see [wiki article](https://en.wikipedia.org/wiki/Ziegler–Nichols_method).

[^1]: Taken from https://grauonline.de/alexwww/ardumower/pid/pid.html
