---
tags:
  - Fluids
  - PressureRelief
---
# Choked flow

## EPSHEG 8 explanation

Sometimes the topic of choked gas flow is not well explained, so here’s an intuitive way to think about the concept from an old ICI pressure relief guideline (EPSHEG8):

> The phenomenon of choking needs to be understood by the relief system designer because choking frequently limits the flow capacity of the system and influences the pressure distribution through the system. Choking occurs only in compressible flow systems, i.e. gas flow or two-phase flow.
> 
> Pressure drop is the driving force for flow. When the pressure drops in a compressible system, the fluid density decreases and the fluid velocity increases. As the pressure drops, the velocity can increase until the kinetic energy is a significant proportion of the total energy of the fluid. A point will be reached at which further drop in pressure would require more energy (due to the increased kinetic energy) than the energy available from the drop in pressure. At this point, the flow is said to be choked. For a gas, the velocity at choking is equal to the speed of sound in the gas and is frequently called the sonic velocity.
> 
> The maximum mass flowrate occurs at choking. If the available pressure drop is less than that required to cause choking, then the mass flowrate through the system will be less than it would have been if the pressure drop were high enough to cause choking. If the available pressure drop is more than that required to cause choking, then the mass flowrate will the choked flowrate. (There is an exception to this. A specially designed nozzle for supersonic flow, e.g. as in a supersonic wind tunnel, would have a mass flow lower than the sonic choked flow for the system. However, this is a very special case and it can be assumed that, in a pressure relief system, when the available pressure drop is high enough, choking will occur and the mass flow will be that at choking.)

I have my doubts about this last bit. Literature on convergent-divergent de Laval nozzles doesn't seem correct when they claim Mach numbers above 1, because they wrongly assume that the vapour exiting a restricted throat area instantly expands to fill the wider pipe area so that the vapour density (and therefore velocity) is constant over the wider pipe. Instead the centre core of the flow is of higher density and mach no. is always less than or equal to 1.

For further reading check out [[MPEC sonic velocity article|this rant]] on sonic limits.