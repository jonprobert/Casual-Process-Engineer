---
tags:
  - Commissioning
  - ProcessControl
---
# Operation of drives 'in hand'

‘In hand’ or 'hand' operation on drives (pump, compressor motors etc.) refers to running equipment in manual mode via a local control point, such as a switch or pushbutton on the MCC (Motor Control Centre). In this mode, the motor is started directly by an operator, bypassing the DCS (Distributed Control System). The local control circuit takes over, and DCS based permissives and interlocks (e.g. low flow, low suction pressure) are typically not enforced.

This mode is used primarily during maintenance, commissioning, or fault-finding. It allows operations to start and stop equipment for tasks like motor tests, line flushing, or checking pump rotation, without being hindered by interlocks designed for normal operation. Since ‘in hand’ mode overrides automated protection and sequencing, its use is usually controlled through using the permit-to-work system or requires supervisor authorisation.

It’s important to note that while DCS interlocks are bypassed, SIS (Safety Instrumented System) trips and ESD (Emergency Shut Down) functions are not. These remain active in all control modes, including ‘hand’, and will shut down the motor if their conditions are met. SIL-rated protections—such as high bearing temperature or process-critical trips—are hardwired and independent of DCS logic, ensuring that safety integrity is not compromised.