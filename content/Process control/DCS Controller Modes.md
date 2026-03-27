---
tags:
  - ProcessControl
  - Commissioning
---
# DCS Controller Modes

## PID function block modes

### OOS - Out Of Service

 The block algorithm is not active. The output is maintained at the last value or at a specified failure action value.

### IMAN - Initialising Manual

The upstream block of a cascade pair is put into this mode when its downstream partner is in a non-cascade mode. This prevents the upstream block from closing the cascade. When the downstream block returns to a cascade mode ([[DCS Controller Modes#CAS - Cascade|CAS]] or ([[DCS Controller Modes#RCAS - Remote Cascade|RCAS]]), the upstream block leaves IMAN and returns to its target mode.

### MAN - Manual

Also called 'open-loop control', in MAN mode the MV (manipulated variable) can be changed directly. The block output is set directly by the operator.

### AUTO - Automatic

Also called 'closed-loop control', AUTO mode is where the MV value can’t be changed; it is automatically calculated. This is the output going to the Final Control Element.

In this mode, the control algorithm of the block is active. An operator-entered setpoint is used in the control algorithm to determine the block output.

On the faceplate of the PID controller the process variable (PV) from the field is displayed. The setpoint/Set Value (SV) needs to be manually entered by the operator. 

### CAS - Cascade

In CAS mode/loop the output of primary controller (say MV1) determines the setpoint of the secondary controller (SV2). The output of secondary controller goes to final control element. The setpoint comes from another block through the 'CAS_IN' input connector.

Also for a cascade loop, the primary controller can be in [[DCS Controller Modes#AUTO - Automatic|AUTO]] or [[DCS Controller Modes#MAN - Manual|MAN]] mode, but the secondary controller has to be in CAS mode.

This mode is similar to [[DCS Controller Modes#AUTO - Automatic|AUTO]] except that the setpoint is supplied by another function block through the CAS_IN parameter. The block maintains a back calculation output value (BKCAL_OUT) to provide bumpless mode transfer when the mode is changed.

### RCAS - Remote Cascade

Used for supervisory or model-predictive control. The setpoint comes from a host computer that writes to RCAS_IN.

This mode is similar to [[DCS Controller Modes#CAS - Cascade|CAS]] except that the setpoint is supplied by an external control program through the RCAS_IN parameter. The block maintains a back calculation output value (RCAS_OUT) to provide bumpless transfer when the mode is changed.

### ROUT - Remote Output

Used to position outputs for batch operation, transitions, start-up, shutdown and abnormal conditions.

This mode is similar to [[DCS Controller Modes#MAN - Manual|MAN]] except that the OUT value is supplied by an external control program rather than directly by the operator. OUT is supplied through the ROUT_IN parameter. The block maintains a back calculation output value (ROUT_OUT) to provide bumpless transfer when the mode is changed.

## Emerson examples from fieldbus manual

![[PID Controller Modes.png]]
https://www.emerson.com/documents/automation/manual-mlt-1-mlt-2-cat-200-foundation-fieldbus-communication-software-3rd-ed-rosemount-en-69940.pdf