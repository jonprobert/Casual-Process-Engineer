---
tags:
  - Fluids
  - Pumps
---
# Affinity laws for centrifugal pumps and fans

The affinity laws describe how the volumetric flow rate, head, and power consumption of a centrifugal pump or fan change with impeller speed and/or impeller diameter. They are approximations, valid over a limited range, and assume constant efficiency.

I'm not planning to regurgitate the many sources on this topic. More detail available [here](https://www.engineeringtoolbox.com/affinity-laws-d_408.html) on Engineering Toolbox.

> [!Warning] Limitations
> 
> - These laws assume constant efficiency between states 1 and 2. In practice, efficiency falls off at the extremes of a pump's operating range, so results become less reliable far from the best efficiency point (BEP).
> - Diameter-based laws are generally reliable only for small trims (a few percent).
> - Always validate against manufacturer pump curves where precision matters. The affinity laws are a scaling tool, not a substitute for tested performance data.

## Fixed diameter, variable speed

For the same impeller, changing rotational speed $N$ (rpm):

$$
\frac{Q_2}{Q_1} = \frac{N_2}{N_1}
$$

$$
\frac{H_2}{H_1} = \left(\frac{N_2}{N_1}\right)^2
$$

$$
\frac{P_2}{P_1} = \left(\frac{N_2}{N_1}\right)^3
$$

where $Q$ is volumetric flow rate, $H$ is head, $P$ is power, and $N$ is rotational speed.

## Fixed speed, variable diameter

For the same speed, with a change in impeller diameter $D$ (small trims only — large changes distort the velocity triangles and this approximation degrades):

$$
\frac{Q_2}{Q_1} = \frac{D_2}{D_1}
$$

$$
\frac{H_2}{H_1} = \left(\frac{D_2}{D_1}\right)^2
$$

$$
\frac{P_2}{P_1} = \left(\frac{D_2}{D_1}\right)^3
$$