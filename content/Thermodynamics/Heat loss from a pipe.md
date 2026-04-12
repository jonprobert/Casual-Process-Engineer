---
title: Heat loss from a pipe
date: 2026-04-12
tags:
  - Thermodynamics
  - Fluids
  - Design
---
# Heat loss from a pipe

The total heat loss from a pipe is given by:

$$
Q = \frac{T_f - T_{amb}}{R_{tot}}
$$

where $R_{tot} = R_i + R_{\text{pipe}} + R_{\text{ins}} + R_o$, giving:

$$
\boxed{
Q = \frac{T_f - T_{amb}}{\underbrace{\dfrac{1}{h_i A_i}}_{R_i}+\underbrace{\dfrac{\ln(r_2/r_1)}{2\pi k_1 l}}_{R_{\text{pipe}}}+\underbrace{\dfrac{\ln(r_3/r_2)}{2\pi k_2 l}}_{R_{\text{ins}}}+\underbrace{\dfrac{1}{(h_o + h_r) A_o}}_{R_o}}
}
$$

![[pipe_heatloss_overall.png|300]]

This assumes steady-state, one-dimensional radial heat transfer with resistances acting in series. The model covers three physical mechanisms: conduction through the pipe wall and insulation, convection at the inner and outer surfaces, and radiation from the outer insulation surface to the surroundings.

> [!INFO]- Iterative solution required
> The radiative coefficient $h_r$ depends on the outer insulation surface temperature $T_3$, which is itself an output of the calculation. The resistance network must therefore be solved iteratively: assume $T_3$, compute $h_r$, solve for $Q$, back-calculate $T_3$ from the outer resistance, and repeat until convergence.

## Nomenclature

| Symbol            | Description                                             | Units   |
| ----------------- | ------------------------------------------------------- | ------- |
| $Q$               | Total heat loss rate                                    | W       |
| $T_f$             | Bulk fluid temperature (inside pipe)                    | K       |
| $T_{amb}$         | Ambient temperature (surroundings)                      | K       |
| $T_1$             | Inner pipe wall temperature                             | K       |
| $T_2$             | Outer pipe wall temperature (pipe–insulation interface) | K       |
| $T_3$             | Outer insulation surface temperature                    | K       |
| $h_i$             | Inner convective heat transfer coefficient              | W/m²·K  |
| $h_o$             | Outer convective heat transfer coefficient              | W/m²·K  |
| $h_r$             | Radiative heat transfer coefficient                     | W/m²·K  |
| $A_i$             | Inner pipe surface area, $2\pi r_1 l$                   | m²      |
| $A_o$             | Outer insulation surface area, $2\pi r_3 l$             | m²      |
| $r_1$             | Inner pipe radius                                       | m       |
| $r_2$             | Outer pipe radius (pipe–insulation interface)           | m       |
| $r_3$             | Outer insulation radius                                 | m       |
| $k_1$             | Thermal conductivity of pipe wall                       | W/m·K   |
| $k_2$             | Thermal conductivity of insulation                      | W/m·K   |
| $l$               | Pipe length                                             | m       |
| $\varepsilon$     | Emissivity of insulation outer surface                  | —       |
| $\sigma$          | Stefan–Boltzmann constant, $5.67 \times 10^{-8}$        | W/m²·K⁴ |
| $R_i$             | Inner convective resistance                             | K/W     |
| $R_{\text{pipe}}$ | Pipe wall conduction resistance                         | K/W     |
| $R_{\text{ins}}$  | Insulation conduction resistance                        | K/W     |
| $R_o$             | Outer combined (convection + radiation) resistance      | K/W     |

## Mechanisms

### Conduction

> In a solid, the flow of heat by conduction is the result of the transfer of vibrational energy from one molecule to another, and in fluids it occurs in addition as a result of the transfer of kinetic energy. Heat transfer by conduction may also arise from the movement of free electrons, a process which is particularly important with metals and accounts for their high thermal conductivities.
> 
> _— Coulson and Richardson, Vol. 1_

#### Conduction through plane walls

The rate of heat flow $Q$ across area $A$ over an infinitesimal distance $dx$ in a material of thermal conductivity $k$ is given by Fourier's law:

$$
Q = -kA\left(\frac{\mathrm{d}T}{\mathrm{d}x}\right)
\tag{1}
$$

> [!INFO]
> The negative sign indicates that heat flows in the direction of decreasing temperature. Integrating over a finite thickness $x$, where $k$ varies linearly with temperature:

$$
k_a(T_1 - T_2) = Q\int_{x_1}^{x_2} \frac{\mathrm{d}x}{A}
\tag{2}
$$

$$
Q=\frac{(T_1 - T_2),A}{x/k_a}
\tag{3}
$$

where $k_a$ is the arithmetic mean of the thermal conductivities at $T_1$ and $T_2$.

![[conduction1.png|300]]

The ratio $x/k$ represents the thermal resistance per unit area. For multiple layers in series:

![[conduction2.png|500]]

$$
Q = \frac{\text{Total driving force}}{\text{Total (thermal resistance/area)}}=\frac{(T_1 - T_4)}{\left(\dfrac{x_1}{k_1 A} + \dfrac{x_2}{k_2 A} + \dfrac{x_3}{k_3 A}\right)}
\tag{4}
$$

#### Conduction through a tube wall

![[conduction3.png|300]]

For a cylindrical geometry, the heat flux is proportional to the local surface area, which increases with radius. The temperature gradient is therefore inversely proportional to radius. At any radius $r$ in a tube of length $l$ and thermal conductivity $k$:

$$
Q = -k, 2\pi r l, \frac{\mathrm{d}T}{\mathrm{d}r}
\tag{5}
$$

Separating variables and integrating between $r_1$ and $r_2$:

$$
Q = \frac{2\pi l k,(T_1 - T_2)}{\ln(r_2/r_1)}
\tag{6}
$$

For multiple layers (e.g. over a pipe wall and insulation):

![[conduction4.png|300]]

$$
Q = \frac{2\pi l,(T_1 - T_3)}{\dfrac{\ln(r_2/r_1)}{k_1} + \dfrac{\ln(r_3/r_2)}{k_2}} 
\tag{7}
$$

### Convection

> Heat transfer by convection arises from the mixing of elements of fluid. If this mixing occurs as a result of density differences — as, for example, when a pool of liquid is heated from below — the process is known as _natural convection_. If the mixing results from eddy movement in the fluid, for example when a fluid flows through a pipe heated on the outside, it is called _forced convection_. It is important to note that convection requires mixing of fluid elements, and is not governed by temperature difference alone as is the case in conduction and radiation.
> 
> _— Coulson and Richardson, Vol. 1_

When a fluid is in contact with a surface at a different temperature, heat is transferred by convection. The rate of heat transfer is described by Newton's law of cooling:

$$
Q = hA(T_s - T_b)
\tag{8}
$$

where $h$ is the convective heat transfer coefficient, $A$ is the surface area, $T_s$ is the surface temperature, and $T_b$ is the bulk fluid temperature.

#### Inner convection — fluid to pipe inner wall

$$
Q_{\text{conv},i} = h_i A_i (T_f - T_1)
\tag{9}
$$

where $h_i$ is the inner convective heat transfer coefficient, $A_i = 2\pi r_1 l$, $T_f$ is the bulk fluid temperature, and $T_1$ is the pipe inner wall temperature. For turbulent internal flow, $h_i$ is typically estimated using the Dittus–Boelter equation or a suitable Nusselt number correlation.

#### Outer convection — insulation surface to ambient air

$$
Q_{\text{conv},o} = h_o A_o (T_3 - T_{amb})
\tag{10}
$$

where $A_o = 2\pi r_3 l$ and $T_{amb}$ is the ambient air temperature.

The outer convective coefficient $h_o$ is not a fixed property — it depends on the pipe geometry, the surface-to-air temperature difference, and the physical properties of the surrounding fluid. For a horizontal pipe losing heat to quiescent air by natural convection, the calculation chain proceeds as follows.

The Grashof number quantifies the ratio of buoyancy to viscous forces:

$$
\mathrm{Gr} = \frac{g\beta(T_3 - T_{amb})D_o^3}{\nu^2}
$$

where $g$ is gravitational acceleration, $\beta$ is the thermal expansion coefficient of air, $D_o$ is the pipe outer diameter (the characteristic length), and $\nu$ is the kinematic viscosity of air. Multiplying by the Prandtl number $\mathrm{Pr}$ gives the Rayleigh number:

$$
\mathrm{Ra} = \mathrm{Gr} \cdot \mathrm{Pr}
$$

An empirical correlation maps $\mathrm{Ra}$ to the Nusselt number $\mathrm{Nu}$, with the form depending on whether the boundary layer is laminar or turbulent. The coefficient $h_o$ is then recovered from:

$$
h_o = \frac{\mathrm{Nu}\cdot k_{air}}{D_o}
\tag{11}
$$

where $k_{air}$ is the thermal conductivity of air evaluated at an appropriate film temperature.

### Radiation

> All materials radiate thermal energy in the form of electromagnetic waves. When this radiation falls on a second body it may be partially reflected, transmitted, or absorbed. It is only the fraction that is absorbed that appears as heat in the body.
> 
> _— Coulson and Richardson, Vol. 1_

Radiation from the outer insulation surface to the surroundings is given by the Stefan–Boltzmann law:

$$
Q_{rad} = \varepsilon\sigma A_o (T_3^4 - T_{amb}^4)
\tag{12}
$$

where $\varepsilon$ is the emissivity of the outer insulation surface and $\sigma = 5.67 \times 10^{-8}$ W/m²·K⁴.

This expression is appropriate for a pipe radiating to an open environment but should be reconsidered if the pipe is in a confined or high-temperature enclosure.

#### Linearised radiative coefficient

To incorporate radiation into the resistance network, equation (12) is linearised so the radiative heat flux can be written in the form $Q_{rad} = h_r A_o (T_3 - T_{amb})$:

$$
h_r = \varepsilon\sigma(T_3^2 + T_{amb}^2)(T_3 + T_{amb})
\tag{13}
$$

> [!INFO]- Reference
> Ref equation (5-12) in Perry's Chemical Engineers Handbook
> 
> ![[Perrys5-12b.png|500]]

The total outer heat transfer (convection and radiation **in parallel**, sharing the same surface area and the same driving temperature $T_3 - T_{amb}$) is then:

$$
Q_o = (h_o + h_r)A_o(T_3 - T_{amb})
$$

which yields the outer thermal resistance:

$$
R_o = \frac{1}{(h_o + h_r)A_o}
$$

The parallel addition of $h_o$ and $h_r$ is valid provided the convective reference temperature equals the radiative sink temperature, i.e. $T_{air} = T_{surr}$. This holds in most outdoor and unconfined industrial settings but may not hold near furnaces etc.

Since $h_r$ depends on $T_3$, which is itself unknown, the solution is implicit and requires iteration (see note at the start of this article).