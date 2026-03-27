---
tags:
  - ProcessSafety
  - Commissioning
---
# Plant commissioning basics

Following the mechanical completion of a new facility, the primary objective of the commissioning stage is to conduct comprehensive and safe testing of all relevant equipment before the introduction of chemicals. This process serves the dual purpose of ensuring the proper functionality of the installation at some point in its history and creating a documented record for future reference.

>[!warning]
>All commissioning activities must be executed with a paramount emphasis on safety, with zero injuries and no loss of containment, including water.

While expediency is not the primary concern, time becomes a critical factor, especially for the last plant to undergo commissioning. Consequently, commissioning plans should prioritise efficiency, particularly during activities such as filling operations, which can be time-consuming. It is advisable to coordinate and overlap activities with significant downtime to optimise the overall timeline.

Commissioning largely involves filling vessels with water to facilitate the testing of instruments and rotating machines. Vessels should be filled up to their high-high (HH) level once, preferably through the standard filling route. Subsequently, equipment testing should occur, encompassing activities such as running pumps, tuning control valves, and cross-checking temperature transmitters and flowmeters. Throughout the extended filling periods, operations should remain engaged and informed to enhance their understanding of the plant (it is their plant after all), thereby minimising potential delays.

Avoid duplicating tests that have already been conducted in pre-commissioning, such as safety instrumented system (SIS) tests and distributed control system (DCS) loop checks. A possible exception is ensuring vessels are filled up to the HH trip to verify the complete functionality. Test all components comprehensively within the available timeframe, as a more extended commissioning plan that uncovers equipment faults early proves superior to a shorter plan that defers discoveries until startup. Although commercial pressure to initiate plant operations may intensify over time, the implementation of a thorough commissioning plan significantly alleviates the stress associated with startup procedures.

## Commissioning pre-requisites

Before carrying out the procedure in the commissioning plans:

- Construction complete and checked against P&IDs (with appropriate certification applicable to local site procedure).

- Pre-commissioning completed ([[Hazard study 4|hazard study 4]], [[Hazard study 5|hazard study 5]], alarm checks, interlock checks, SIS checks, dry-run testing).

- Adjacent plants isolated from section to be commissioned.

## Commissioning plans

Commissioning plans delineate a systematic, step-by-step approach tailored to a specific system or sub-system (e.g cooling water, reactor A, refrigeration, etc). These plans must provide sufficient detail for any process engineer to execute the outlined tasks, specifying actions and recording procedures without necessarily delving into the underlying reasons unless clarity is lacking.

Define the commissioning boundary explicitly, outlining how it will be isolated from adjacent plants, thus minimising potential confusion. To eliminate ambiguity, tag all equipment within the plan.

Address common foreseeable challenges in the plan, offering strategies for navigating issues with upstream or downstream plants that are yet to undergo commissioning.

Recognise that certain facets of commissioning, particularly those requiring chemicals, cannot be undertaken in the water phase. Such activities should occur post-Authorisation To Introduce Chemicals (ATIC) but before startup. These tasks can be seamlessly integrated at the conclusion of the commissioning plan. Additionally, incorporate any final testing requirements that necessitate postponement until startup, such as those dependent on heat load, chemical reactions, or diverse process variable conditions.

Clearly stipulate the fluid to be used for commissioning, typically water or air, and pay attention to the ingress and egress of fluids into and out of the plant, including considerations for water, vents, and drains.

The plant should be left in a state conducive to startup, ensuring it is appropriately vented, dry, purged etc.

## Top tips

- Have a quickly accessible support team of C&I, automation, process, mechanical and operations. An issue occurring at 7pm without availability could mean a 12h delay.

- Conduct a daily commissioning meeting to inform everybody of progress and the plan. Thus avoiding delays as much as possible.
  
- Note that we are commissioning a plant, not a series of instruments. Fill tanks to HH level (rather than dropping level switches in a bucket of water - could be of insufficient length).

## Recommended testing

### Vessels

- Fill up to the highest trip level.

### Pumps

- Witness the initial start.
- Monitor noise, mechanical seals, bearing temperatures etc.
- Run with the suction vessel at minimum level with any agitator running to detect cavitation.
- Run at the duty flow rate.

Relevant: [[Operation of drives 'in hand']].
### Agitators

- Witness the first start.
- Ensure adequate agitation (if possible on water), absence of vortexing, and proper immersion at the low level.

### Columns

- Perform minimal gas flow checks, including pressure drop and flooding.

### Pipework

- Physically walk all pipes during the first fill.
- No testing required for manual valves, relief valves, and static mixers.
- Ensure heat tracing is operational , this is especially crucial for small bore pipework and instrument impulse lines.
- Collect water samples at designated sample points.

### Instrumentation

#### Trip valves (on/off)

- Only really worth testing if trip initiator is from HH vessel level.

#### Control valves

- Test control action, including a duty point, and conduct PID tuning.
- Verify tight shut-off.
- Re-trim if necessary.

#### Level

- Monitor during the fill and compare against actual conditions.

#### Pressure

- Ensure the instrument reads atmospheric pressure when the plant is vented.
- Check any differential pressures where feasible.

#### Temperature

- Verify temperature is reasonable compared to ambient conditions.

#### Flow

- Ensure proper ranging to cover the maximum process flow.
- Cross-check against error tolerance.

#### Analysers

- Vendor involvement is typically required and usually done after the introduction of chemicals.