---
tags:
  - PressureRelief
  - ProcessSafety
---
# Identification of events leading to relief scenarios

> [!Warning] Warning
> There are many possible approaches to identifying credible relief events. The following is a common method but the **examples are non-exhaustive**. 

For each protected system[^1] a plant/process condition and prime event (fault, defect etc.) is identified.

[^1]: A pressure system may include several items and will include piping and fittings. The design pressure of the overall system is the design pressure of the weakest part of the system.

## Plant conditions

**1 - System blocked in** - all inlets and outlets of a pressure system are closed.
**2 - Restricted outlet** - outlets from a pressure system are closed, restricted or too small.
**3 - Restricted inlet** - inlets from a pressure system are closed, restricted or too small.
**4 - Chemical reaction** - where a chemical process can cause pressure to rise if outflow/heat removal is restricted.

## Prime events

**A - External fire**

**B - Process abnormality** - maloperation of the process (by the operator or by deviation in input materials chemical or physical properties).
- Closed or blocked liquid outlet/overfilling
- Closed or blocked vapour outlet
- Chemical reaction
- Abnormal heat input
- Reflux failure
- Reverse flow
- Inlet control valve and/or bypass valve fully open
- Accumulation of non-condensables
- Abnormal addition of hot/volatile material

**C - Equipment and services failure**
- Heat exchanger tube rupture
- Coil leaks
- Cooling failure (loss of cooling water, refrigeration, etc.)
- Electrical power failure
- Instrument air failure
- Steam failure
- Loss of fuel supply
- Nitrogen/inert gas supply failure

**D - Change in ambient condition** - solar radiation, temperature, rainfall, wind, etc.
- Inbreathing and outbreathing (due to thermal effects) - additive to effects of restricted inlets/outlets and the associated changes to inflow and outflow.

A more extensive matrix of **Prime Event** against **Plant Condition** with examples of relief scenarios can be found in EPSHEG8 Part B.

## Double jeopardy

> [!quote] References in API521
> > The simultaneous occurrence of two or more unrelated causes of overpressure (also known as double or multiple jeopardy) is not a basis for design. Examples of double jeopardy scenarios are fire exposure simultaneous with heat exchanger internal tube failure, fire exposure simultaneous with failure of administrative controls to drain and depressure isolated equipment, or operator error that leads to a blocked outlet coincident with a power failure. On the other hand, instrument air failure during fire exposure may be considered single jeopardy if the fire exposure causes local air line failures
> **API 521 (7th edition) §4.2.3**
> 
> However note that...
> >The user may choose to go beyond these practices and assess multiple jeopardy scenarios, particularly for severe consequence events.
> >**API 521 (7th edition) §4.2.3**

Whilst most of the over/underpressure hazards above can be considered independent of one another—and can often be correctly discounted under the guise of "we don't design for double jeopardy"—the potential for simultaneous occurrence of hazards is important to consider (e.g. instrument failure during fire exposure).

It is not double jeopardy to consider latent failure (i.e. absence of beneficial instrumentation which might have already failed and the operator hasn't noticed).