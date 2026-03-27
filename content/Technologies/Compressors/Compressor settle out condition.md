---
tags:
  - Compressors
---
# Compressor settle out condition

The settle-out pressure of a gas compression system is defined as the equilibrium reached due to equalisation of the pressure between the suction and discharge side of the compressor, when the compressor has been shut down from normal operation, without depressurising the system to a plant cold vent or flare.

## Method for determining settle out temperature and pressure for a vapour filled system


> [!WARNING] Warning
> This method is applicable to vapour systems only. Any liquid flashing and auto-refrigeration effects due to decreased pressure should be considered separately (such is in closed circuit refrigeration units).
> 
> For refrigeration units, also consider if there is any flashing of high pressure liquid to the low pressure side. Letdown valves are normally driven closed in a trip scenario. 
 
### Nomenclature

| Symbol   | Description                                     | Unit                                     |
| -------- | ----------------------------------------------- | ---------------------------------------- |
| $n_i$    | Moles of vapour in section $i$                  | $\text{mol}$                             |
| $n_s$    | Total moles of vapour at settle out             | $\text{mol}$                             |
| $m_i$    | Mass of vapour in section $i$                   | $\text{kg}$                              |
| $m_s$    | Total mass of vapour at settle out              | $\text{kg}$                              |
| $\rho_i$ | Density of vapour in section $i$                | $\text{kg m}^{-3}$                       |
| $P_i$    | Pressure of vapour in section $i$               | $\text{Pa}$                              |
| $P_s$    | Settle out pressure                             | $\text{Pa}$                              |
| $T_i$    | Temperature of vapour in section $i$            | $\text{°C}$                              |
| $T_s$    | Settle out temperature                          | $\text{°C}$                              |
| $V_i$    | Volume of section $i$                           | $\text{m}^3$                             |
| $V_s$    | Total system volume                             | $\text{m}^3$                             |
| $Z_i$    | Compressibility factor of vapour in section $i$ | -                                        |
| $Z_s$    | Compressibility factor at settle out            | -                                        |
| $R$      | Ideal gas constant                              | $\text{8.314 J K}^{-1} \text{ mol}^{-1}$ |

### Method

Define the trapped gas volume by defining suitable boundaries (consider the action of trip valves etc.) and divide the system into sections (e.g. suction side, intermediate side, discharge side).

Calculate the total moles of vapour in each section at their given operating conditions (before settle out). Using the non-ideal gas law:

$$n_i=\frac{P_iV_i}{Z_iRT_i}\tag{1}$$

Find the total number of moles in the system (which will be the same before/after compressor trip):

$$n_s=\sum_{i=1}^{\infty} n_i\tag{2}$$

Find the total system volume in a similar manner. The volume of each section is estimated through using approximate pipe length values, pipe sizes, equipment volumes etc.

$$V_s=\sum_{i=1}^{\infty} V_i\tag{3}$$

Find the mass of vapour in each section and the system total.

$$m_i=\rho_iV_i\tag{4}$$

Vapour density can be from physical property data, or calculate $m_i$ using molecular mass (as $n_i$ is known).

$$m_s=\sum_{i=1}^{\infty} m_i\tag{5}$$

Calculate the settle-out temperature using a mass weighted average temperature method.

$$T_s=\frac{\sum_{i=1}^{\infty} m_iT_i}{m_s}\tag{6}$$
 
Settle-out compressibility factor is determined through the use of the following equation.

$$Z_s=\frac{\sum_{i=1}^{\infty} m_iZ_i}{m_s}\tag{7}$$
 
The settle-out pressure is calculated using the average values of compressibility factor, temperature and total volume and mass.
 
$$P_s=\frac{Z_sRT_s}{V_s}\tag{8}$$