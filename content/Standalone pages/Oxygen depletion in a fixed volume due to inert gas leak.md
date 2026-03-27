---
tags:
  - Fluids
---
# Oxygen depletion in a fixed volume due to inert gas leak

> [!NOTE]
> Also see an [[Oxygen depletion in a fixed volume due to inert gas leak with constant recycle|extension of this work]] which incorporates a recycle stream.

In a system where nitrogen leakage into a room results in oxygen depletion, the following may be used to determine the leakage rate resulting in a specified oxygen concentration at equilibrium.

![[oxygen_depletion.png|500]]

$$\dot{n}=NV_{room}\left(1- \frac{C_f}{0.21} \right)\tag{1}$$
Where:
$\dot{n}$ is nitrogen flow into room, $m^3/h$
$N$ is the no. of room change per hour due to HVAC, $h^{-1}$
$V_{room}$ is room volume, $m^3$
$C_f$ is final room oxygen concentration at equilibrium, (vol frac)

>[!Warning] Assumptions
>- Assumes instantaneous perfect mixing. Whilst concentration will average out to some degree in large spaces, this method does not account for local oxygen depletion. **This will be significant at the point of release.**
>- All flowrates given in $m^3/h$ at atmospheric pressure.
>- Air into the system via HVAC unit is a constant volumetric flow and taken as 21 vol% oxygen.

# Derivation

![[Oxygen_depletion_system.png|500]]

At equilibrium, oxygen in = oxygen out.
$$0.21\dot{a}=C_f\dot{Q}\tag{2}$$
Where:
$\dot{a}$ is air flow into the room, $m^3/h$
$C_f$ is final room oxygen concentration at equilibrium, (vol frac)
$\dot{Q}$ is vent flow out of the room, $m^3/h$

Since $\dot{a}=\dot{Q}-\dot{n}$, we can substitute to find:
$$0.21(\dot{Q}-\dot{n})=C_f\dot{Q}\tag{3}$$
Re-arranging for $\dot{n}$:
$$\dot{n}=\dot{Q}\left( \frac{0.21-C_f}{0.21} \right)\tag{4}$$
The vent flow is related simply to the number of air changes per hour:
$$\dot{Q}=NV_{room}\tag{5}$$
Where:
$N$ is the number of air changes per hour, $h^{-1}$
$V_{room}$ is the room volume, $m^3$

Substitute $\text{(5)}$ into $\text{(4)}$:
$$\dot{n}=NV_{room}\left(1- \frac{C_f}{0.21} \right)\tag{6}$$