---
tags:
  - Thermodynamics
---
# Flash calculations

Flash calculations are used to determine the equilibrium distribution of components between the vapour and liquid phases when a multi-component mixture undergoes a phase change, such as in distillation, evaporation, or condensation processes. The calculations involve combining equations for Vapour Liquid Equilibrium (VLE) with the component mass balances, and in some cases the energy balance.

> [!WARNING]
> The calculations below primarily assume that VLE is based on [[Raoult's Law]] for ideal mixtures which states that the vapour pressure of each component is proportional to its mole fraction in the liquid phase.

The K-value for a component $i$ is expressed using Raoult's Law as:

$$
K_i=\frac{y_i}{x_i}=\frac{P_i^\theta}{P}
\tag{1}
$$

## Nomenclature

| Symbol       | Description                                                    | Unit              |
| ------------ | -------------------------------------------------------------- | ----------------- |
| $x_i$        | Mole fraction of component $i$ in the liquid phase             | $\text{mol frac}$ |
| $y_i$        | Mole fraction of component $i$ in the vapour phase             | $\text{mol frac}$ |
| $z_i$        | Mole fraction of component $i$ in the feed                     | $\text{mol frac}$ |
| $K_i$        | Raoult's Law K-value or Equilibrium Constant for component $i$ | -                 |
| $P$          | Total pressure of the system                                   | $\text{Pa}$       |
| $P_i$        | Partial pressure of component $i$                              | $\text{Pa}$       |
| $P_i^\theta$ | Vapour pressure of component $i$ at the system temperature     | $\text{Pa}$       |
| F            | Total molar feed flow to flash vessel                          | $\text{mol/s}$    |
| V            | Molar vapour flow from flash vessel                            | $\text{mol/s}$    |
| L            | Molar liquid flow from flash vessel                            | $\text{mol/s}$    |
| $h_F$        | Feed stream molar enthalpy                                     | $\text{kJ/mol}$   |
| $h_V$        | Vapour stream molar enthalpy                                   | $\text{kJ/mol}$   |
| $h_L$        | Liquid stream molar enthalpy                                   | $\text{kJ/mol}$   |

# Bubble point calculation

To find the point at which liquid just starts to boil at a given temperature we compute where the sum of the vapour fractions reaches 1.

$$
\sum_iy_i=\sum_iK_ix_i=1
\tag{2}
$$

Where [[Raoult's Law]] applies this gives:

$$
\sum_ix_iP_i^\theta=P
\tag{3}
$$

 $P_i^\theta$ is a function of temperature (one method to estimate vapour pressure is the [[Antoine Equation]]), so for a given liquid mixture composition at a given temperature we can directly calculate the bubble point pressure.

$$
P=x_1P_1^\theta+x_2P_2^\theta+x_3P_3^\theta+\cdots+x_nP_n^\theta
\tag{4}
$$

The vapour composition of each component can then be calculated:

$$
y_i=\frac{P_i}{P}
\tag{5}
$$

# Dew point calculation

To find the point at which vapour just starts to condense at a given temperature we compute where the sum of the liquid fractions reaches 1.

$$
\sum_ix_i=\sum_i\frac{y_i}{K_i}=1
\tag{6}
$$

Where [[Raoult's Law]] (substitute $K_i=\frac{P_i^\theta}{P}$) applies this gives:

$$
\sum_i\frac{y_i}{P_i^\theta}=\frac{1}{P}
\tag{7}
$$

 $P_i^\theta$ is a function of temperature (one method to estimate vapour pressure is the [[Antoine Equation]]), so for a given vapour mixture composition at a given temperature we can directly calculate the dew point pressure.

$$
\frac{1}{P}=\frac{y_1}{P_1^\theta}+\frac{y_2}{P_2^\theta}+\frac{y_3}{P_3^\theta}+\cdots+\frac{y_n}{P_n^\theta}
\tag{8}
$$

> [!NOTE]
> When calculating dew point with non-condensable component $\alpha$ far above its critical point we can assume $x_\alpha=0$, and so $\frac{y_\alpha}{P_\alpha^\theta}$ goes to zero.

# Flash to determine liquid and vapour streams

Flash on a stream that splits to a vapour and liquid stream.

![[flash_calculation.jpg|300]]

The initial material balance on component $i$:

$$
Fz_i=Vy_i+Lx_i
\tag{9}
$$

We add a further specification by assuming that the vapour and liquid are at equilibrium and follow [[Raoult's Law]]:

$$
y_i=K_ix_i
\tag{10}
$$
## Pressure-Temperature flash

By substituting equation $(10)$ into $(9)$ and solving to find the liquid mole fraction:

$$
Fz_i=VK_ix_i+Lx_i
\tag{11}
$$
Substituting total molar balance $(L=F-V)$:

$$
x_i=\frac{z_i}{1+\frac{V}{F}(K_i-1)}
\tag{12}
$$

The vapour split $V/F$ is not known so $x_i$ cannot be directly calculated. Considering that $\sum_i(y_i-x_i)=0$, this results in the Rachford-Rice equation:

$$
\sum_i\frac{z_i(K_i-1)}{1+\frac{V}{F}(K_i-1)}=0
\tag{13}
$$

which is easy enough to solve for the vapour split $V/F$. 

## Pressure-Enthalpy flash

For an adiabatic flash we must consider the energy balance of the system by maintaining a constant enthalpy:

$$
H_{in}=H_{out}
\tag{14}
$$

$$
Fh_F=Vh_V+Lh_L
\tag{15}
$$

Approach as per Pressure-Temperature flash above and iterate on $T$ until enthalpy requirement is met.