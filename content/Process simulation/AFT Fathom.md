---
tags:
  - Fluids
  - ProcessSimulation
---
# AFT Fathom

AFT Fathom is fluid dynamic simulation software for engineers, used to calculate pressure drop and pipe flow distribution in liquid and low-velocity gas piping and ducting systems.

NB: AFT Fathom calculates both static and stagnation pressures along flowstreams and it is important to understand the difference—especially when specifying pressure boundaries. Further discussion [[Static versus stagnation pressure|here]].

For systems containing gases use [[AFT Arrow]].

## Limitations

### Static head limitation

> [!NOTE] Version
> Behaviour noted in AFT Fathom version 11.

> [!abstract]
> Fathom will warn of issues in a piping system where pressure starts dipping to the fluid's vapour pressure $(P_{vap})$ (due to either frictional losses or increases in elevation). However, the warning given will not prevent a flow developing between the two junctions, or pressure reducing below 0 bara.

The first example below uses ambient temperature water at a fixed 5 barg source at 0m elevation (J1), passing through 100m of 2" pipe to a high point of 5 metres above the pressure source (J2). The pipe then continues another 100m of 2" pipe back down to 0m elevation to an atmospheric pressure sink (J3). 

![[AFT_001.png|500]]

A flow of 2.3 $m^3/h$ develops, and pressure drops to 2 barg at the highest point (a combination of static head and frictional losses).

In this second example the pipe size, lengths, and pressures remain the same, but the elevation of J3 has been increased to 30m.

![[AFT_002.png|500]]

The same flow of 2.3 $m^3/h$ develops, and pressure drops to -0.45 barg at the highest point. A elevation increase of 30m water equates to a static head decrease of ~3 bar. There is a further loss of ~2.45 bar associated with friction. The calculated flow, and resultant pressure at J2 are realistic, as the lowest pressure along the route is still higher than the vapour pressure of water at ambient temperature (~0.02 bara) and the fluid remains in the liquid phase.

In the third example the elevation of J3 has been further increased to 40m. 

![[AFT_003.png|500]]
According to Fathom, a flow of 2.3 $m^3/h$ develops again, and pressure falls to a physically impossible -1.4 barg at the highest point. 

Since the pressure at J1 is sufficient to overcome 40m of static head, the reality is this that system would develop flow, but not the full 2.3 $m^3/h$. The pressure at J2 can only dip to $P_{vap}$ . Meanwhile all we get in Fathom is a warning:

![[AFT_004.png|500]]

![[AFT_005.png]]

Be wary when putting together your piping systems that you don't fall into this trap just because the programme is reporting a flow in all pipes.