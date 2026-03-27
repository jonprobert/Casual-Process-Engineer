---
tags:
  - Fluids
---
# Oxygen depletion in a fixed volume due to inert gas leak *with constant recycle*

The following is an extension of the work on [[Oxygen depletion in a fixed volume due to inert gas leak|this page]] for a system where nitrogen leakage into a room results in oxygen depletion—this only considered that the HVAC inlet was 100% pure air.

For a system with an HVAC outlet recycle stream, the following expression gives the required nitrogen flow rate $\dot{n}$ to maintain a target oxygen concentration $C_f$ in a space of volume $V_{\text{R}}$ with air change rate $N$, and air/recycle ratio $r_{\text{a}}$ in the combined stream.

$$
\boxed{\dot{n} = \frac{N V_{\text{R}} \left(1 - \dfrac{C_f}{0.21} \right)}{1 + \dfrac{C_f (1 - r_{\text{a}})}{0.21 r_{\text{a}}}}}
$$

![[oxygen-depletion-recycle-v1.png]]

| Symbol         | Description                                                                                              | Units |
| -------------- | -------------------------------------------------------------------------------------------------------- | ----- |
| $\dot{a}$      | Volumetric flow rate of air (contains 21% O₂)                                                            | m³/h  |
| $\dot{n}$      | Volumetric flow rate of pure nitrogen (contains 0% O₂)                                                   | m³/h  |
| $\dot{Q}$      | Vent flow rate from the room                                                                             | m³/h  |
| $\dot{R}$      | Recycle flow rate (taken from and returned to the room)                                                  | m³/h  |
| $V_{\text{R}}$ | Volume of the room                                                                                       | m³    |
| $N$            | Number of air changes per hour                                                                           | h⁻¹   |
| $C_f$          | Final steady-state oxygen concentration in the room (volume fraction)                                    | —     |
| $r_{\text{a}}$ | Fraction of air in the combined air + recycle stream: $r_{\text{a}} = \frac{\dot{a}}{\dot{a} + \dot{R}}$ | —     |

## Derivation

Determine the nitrogen flow rate $\dot{n}$ required to achieve a target final oxygen concentration $C_f$, in terms of $V_{\text{R}}$, $N$,  $C_f$, and $r_{\text{a}}$.

>[!Warning] Assumptions
>- Assumes instantaneous perfect mixing. Whilst concentration will average out to some degree in large spaces, this method does not account for local oxygen depletion. **This will be significant at the point of release.**
>- All flowrates given in $m^3/h$ at atmospheric pressure.
>- Air into the system via HVAC unit is a constant volumetric flow and taken as 21 vol% oxygen.

In a system where a proportion of the room air is recycled, we define the ratio of pure air in the total inlet stream (air + recycle):

$$
r_a = \frac{\dot{a}}{\dot{a} + \dot{R}} \tag{1}
$$

Assuming all gases are at room temperature and pressure we can do a volumetric flow balance:

$$
\dot{n}+\dot{a} = \dot{Q} \tag{2}
$$

The oxygen entering and leaving the system must also be balanced. Using the system boundary that includes both vent and recycle:

$$
0.21 \dot{a} + C_f \dot{R} = C_f Q + C_f \dot{R} \tag{3a}
$$

Cancelling $C_f \dot{R}$ from both sides:

$$
0.21 \dot{a} = C_f Q \tag{3b}
$$

Room changes now consider both vent and recycle flows:

$$
N V_R = \dot{Q} + \dot{R} \tag{4}
$$

From $(1)$ we rearrange to find $\dot{R}$:

$$
\dot{R} = \frac{\dot{a}(1 - r_a)}{r_a} \tag{5}
$$

Substitute $(5)$ into $(4)$:

$$
\dot{Q} = NV_R - \dot{R} = NV_R - \frac{\dot{a}(1 - r_a)}{r_a} \tag{6}
$$

From $(3b)$ we can say:

$$
\dot{a} = \frac{C_f \dot{Q}}{0.21} \tag{7}
$$

Substitute $(7)$ into $(6)$:

$$
\dot{Q} = NV_R - \frac{C_f \dot{Q}(1 - r_a)}{0.21 r_a} \tag{8}
$$

Rearrange $(8)$ for $\dot{Q}$:

$$
\dot{Q} = \frac{NV_R}{1 + \frac{C_f(1 - r_a)}{0.21 r_a}} \tag{9}
$$
From $(2)$ and $(7)$:

$$
\dot{n} = \dot{Q} - \frac{C_f \dot{Q}}{0.21}
= \dot{Q} \left(1 - \frac{C_f}{0.21} \right) \tag{10}
$$

Substitute $(9)$ into $(10)$ to eliminate $\dot{Q}$:

$$
\dot{n} = \frac{N V_R \left(1 - \frac{C_f}{0.21} \right)}
{1 + \frac{C_f (1 - r_a)}{0.21 r_a}} \tag{11}
$$
