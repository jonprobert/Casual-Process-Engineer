---
tags:
  - ProcessControl
  - ProcessSafety
---
# Process safety time

Process safety time (PST) is the sum of early response time, operator reaction time, and SIF (Safety Instrumented Function) response time[^1].

[^1]: Is defined in BS EN 61511-1.
## Early response time

The time after a failure has occurred where the process variable is changing and no alarm has been triggered.

## Operator reaction time

The time between alarm and SIF activation in which the operator could take manual corrective action.

## SIF response time

SIF response time is the time between the SIF setpoint being reached, and the hazardous condition occurring. It should consider [[Sensor response time|sensor response time]], and time to fully operate final elements such as shutdown valves.

>[!info]
>A common rule-of-thumb for shutdown valves is to assume 1 second per inch of nominal bore for preliminary assessment.