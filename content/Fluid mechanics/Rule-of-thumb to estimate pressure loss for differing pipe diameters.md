---
tags:
  - Fluids
---
# Rule-of-thumb to estimate pressure loss for differing pipe diameters

A useful rule-of-thumb to estimate the frictional losses in a system for a different pipe diameter is to multiply your calculated frictional losses for a known diameter by the ratio of diameters to the fifth power.

[[Darcy-Weisbach]] tells Us:

$$\Delta P=\frac{\rho fLv^2}{2D}$$

At constant volumetric flow velocity changes with pipe area, so substitute $v=\frac{Q}{A}=\frac{4Q}{\pi D^2}$

$$\Delta P=\frac{8\rho fLQ^2}{\pi^2D^5}$$

Assuming density, Darcy friction factor, volumetric flowrate, and pipe length are constant we can simplify to:

$$\Delta P\propto\frac{1}{D^5}$$

Applying this to states 1 and 2 with differing pipe diameter and constants as described above:

$$\Delta P_{2}=\Delta P_{1}\left ( \frac{D_{1}}{D_{2}} \right )^5$$

> [!warning]
> For incompressible flow only (i.e. liquids). May be used with caution for compressibles where $\Delta P<10\%\;P_{inlet}$.

> [!warning]
> This relation does not account for static head as it applies to frictional losses only.