---
tags:
  - ProcessControl
---
# Sensor response time

The response of instrumentation is a factor in determining the total SIF response time, which in turn determines the total [[Process safety time|process safety time]] of a trip.

The responsiveness of sensors is often described by vendors using a time constant $\tau$, which is the time for the sensor output to reach 63.2% of a step change. It is dependent on media type, flowrates, emissivity of sensor materials, thermal conductivity of sensor materials, etc.

$$T=T_1+(T_2-T_1)\left (1-e^{-\frac{t}{\tau}} \right ) \tag{1}$$

Where:

- $T$ = current sensor reading
- $T_1$ = Initial sensor temperature when it was put into new media
- $T_2$ = Temperature of the new media that the sensor is measuring
- $t$ = Elapsed time from the point when the sensor temperature was $T_1$     
- $\tau$ = Sensor time constant

Also see [[Thermowell Time Constant Estimation]].