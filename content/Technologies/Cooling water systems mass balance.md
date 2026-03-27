---
tags:
  - Design
  - CoolingWater
---
# Cooling water system mass balance

## Overview

Cooling water is essential in many industries for process cooling. Heat is absorbed from process equipment and dissipated at a cooling tower before the water is recirculated. Cooling towers use evaporative cooling to remove heat, requiring a continuous supply of make-up water to compensate for evaporation losses.

For new projects, a study should compare different cooling system options based on cost, water availability, environmental constraints, weather, and space. The main cooling system types are:

- **Once-through systems**: Water is drawn from and discharged back into a natural source, with no cooling tower.
- **Closed recirculating systems**: Water is reused in a closed loop, minimising consumption and thermal pollution.
- **Open recirculating systems**: Water is reused multiple times through a cooling tower before discharge.

Cooling towers can be natural draft, induced draft (crossflow or counterflow), or forced draft. They include a water basin (sump), pumps, filtration, chemical dosing, and heat exchangers. As water evaporates, dissolved solids concentrate, requiring blowdown to maintain water quality. Cycles of Concentration (CC) refer to the level of dissolved solids in the circulating water.

## Generic simplified induced draft cooling tower system

![[Generic simplified induced draft cooling tower system v2.png]]

## Mass balance

### Make-up flow

To determine the make-up water requirement, the rates of evaporation loss and system blowdown are required. This is simply:

$$\dot{q}_m = \dot{q}_e + \dot{q}_d + \overline{\dot{q}_b}
$$

Where:

- $\dot{q}_m$ is make-up flow (m³/h)
- $\dot{q}_e$ is evaporative losses (m³/h)
- $\dot{q}_d$ is drift losses (m³/h)
- $\overline{\dot{q}_b}$ is the average rate of blowdown (m³/h), i.e. as if continuous.

### Estimated evaporative losses

A preliminary estimate of evaporative losses can be obtained using the following equation[^2]:
$$\dot{q}_e = 0.0008 \times 1.8 \times \dot{Q} \Delta T
$$
Where:

- $\dot{q}_e$ is evaporative losses (m³/h)
- $\dot{Q}$ is total system recirculation rate (m³/h)
- $\Delta T$ is temperature range (K), i.e. $T_{return}-T_{supply}$

Note this is an empirical relation for preliminary estimate. The cooling tower vendor should confirm the evaporation loss for their given design.

### Blowdown rate

To determine the average rate of blowdown use the following equation[^1]:

Where:

$$\overline{\dot{q}_b} = \frac{\dot{q}_e}{C - 1}
$$

- $\overline{\dot{q}_b}$ is the average rate of blowdown (m³/h), i.e. as if continuous.
- $\dot{q}_e$ is evaporative losses (m³/h)
- $C$ is the cycles of concentration

Cycles of Concentration is the ratio of dissolved solids in the circulating water to the dissolved solids in make-up water, usually conductivity is used to measure dissolved solids in water. Other dissolved species can also be used to determine the cycles of concentration, such as chlorides. The cycles of concentration can be as low as 2 (for poor make-up water quality) and at or above 12 (pure make-up water). The lower CC the larger the blowdown rate required and make-up water (i.e. higher cycles are more water efficient). The optimum number of concentration cycles depends on the water chemistry and the material of construction within the system, e.g. if stainless steel is in contact with the cooling water, this will require a lower chloride content in the water when compared to carbon steel due to corrosion issues.

In order to determine a proper design figure for the cycles of concentration it is recommended to seek advice from a water chemical treatment program provider and/or experience from the customer with respect to their water supply quality and any existing installations.

[^1]: U.S. Department of Energy. Cooling Towers: Understanding Key Components of Cooling Towers and How to Improve Water Efficiency.

[^2]: Cooling Tower Fundamentals. SPX Cooling Technologies. 2nd Edition 2009