---
tags:
  - Pumps
  - Fluids
---
# Centrifugal pump rundown time

## Introduction

The rundown time is the time taken for the pump to decelerate from its normal operating speed to a complete stop after its power supply is lost or the pump is tripped. A longer rundown time maintains flow and discharge head for longer following a trip, reducing the rate of flow drop off and often the magnitude of surge. Conversely short rundown times cause rapid loss of head and potentially leading to larger pressure transients. 

Following loss of power the pump continues to deliver flow, but both flow and pump head then decrease as its rotational speed drops. Rundown time depends on pump/motor inertia, hydraulic load, and frictional losses, and is an important parameter in surge assessments.

The formulae below used to estimate rundown time are contingent on the following assumptions:

- rundown of a centrifugal pump
- affinity laws can be applied (progressively more inaccurate at low speeds)
- valve positions remain unchanged
- incompressible liquid
- total inertia remains constant
- mechanical losses neglected
- hydraulic braking dominates
- only valid until the pump reaches zero rotational speed and does not model reverse rotation caused by reverse flow.

## Nomenclature

| Symbol      | Description                                                           | Units        |
| ----------- | --------------------------------------------------------------------- | ------------ |
| $t$         | Time elapsed since pump trip                                          | s            |
| $\Delta t$  | Euler integration timestep                                            | s            |
| $P$         | Shaft power at the current operating speed                            | kW           |
| $P_0$       | Shaft power at the initial operating condition                        | kW           |
| $T$         | Shaft (resisting) torque                                              | N m          |
| $I_{Pump}$  | Rotational inertia of the pump, impeller, shaft, and entrained liquid | kg m$^2$     |
| $I_{Motor}$ | Rotational inertia of the motor rotor                                 | kg m$^2$     |
| $I_{Total}$ | Total rotating inertia of the coupled system                          | kg m$^2$     |
| $\omega$    | Angular velocity                                                      | rad s$^{-1}$ |
| $\omega_0$  | Initial angular velocity                                              | rad s$^{-1}$ |
| $\alpha$    | Angular acceleration (negative during rundown)                        | rad s$^{-2}$ |
| $N$         | Rotational speed                                                      | rpm          |
| $N_0$       | Initial rotational speed                                              | rpm          |
| $r$         | Speed ratio, defined as $r=\dfrac{\omega}{\omega_0}=\dfrac{N}{N_0}$   | –            |


## Total rotating inertia

The rundown time of a centrifugal pump may be estimated by first estimating the total rotational inertia of the system. This must include all rotating components: the motor rotor, shaft, impeller, entrained liquid, coupling, and any other connected components. This is often quite difficult to get hold of for individual components, and the most accurate way to obtain the total figure is to source it from your manufacturer.

In lieu of vendor data, a statistical analysis of industry data in *Fluid Transients in Pipeline Systems (Thorley)* can be used to predict the total inertia 

$$
I_{Total}=I_{Pump}+I_{Motor} \tag{1}
$$
For a lot of systems this may estimated as:

$$
\boxed{I_{Total}=1.501\times10^7\left(\frac{P}{N^3}\right)^{0.9556}+I_{Motor}=118.4\left(\frac{P}{N}\right)^{1.48}} \tag{2}
$$

The source of these individual terms and limitations are given below.

### Pump inertia

A linear regression of the two datasets analysed by Thorley give the following estimates of pump inertia for two different datasets.

A correlation for a wide range of rotodynamic pumps used in the water supply, sewage, process and petro-chemical fields, including horizontal spindle, single and double entry, split-case machines as well
as vertical spindle borehole and wet-well pumps:

$$
I_{Pump}=1.501\times10^7\left(\frac{P}{N^3}\right)^{0.9556} \tag{3}
$$

Another correlation is shown which applies to relatively small pumps of a lightweight design:

$$
I_{Pump}=1.344\times10^6\left(\frac{P}{N^3}\right)^{0.844} \tag{4}
$$

(both equations are adjusted to standard units: pump rotational inertia $I_{Pump}$ $\mathrm{(kg\,m^2)}$, shaft power $P$ $\mathrm{(kW)}$ at rated conditions, shaft speed (rpm)).

Full dataset from *Fluid Transients in Pipeline Systems (Thorley)*:

![[pump_inertia_thorley.png]]

> [!Warning]
> Use these inertia estimates with caution and apply margins where necessary when changes of pump speed are critical. Thorley notes:
> > *Despite these apparently good correlations, it will be noted from observation of the graphs that the actual range of inertias above and below the predictions is of the order of +100 % and -50 %. This will only be important in those systems where the rate at which pumps change speed is significant, such as in networks or short pipelines of, say, 5 kilometres or less. This can easily be checked by doing an analysis with the predicted inertia, and then doubling and halving it.*

### Motor inertia

A linear regression of a datasets analysed by Thorley give the following estimate of motor inertia.

$$
I_{Motor}=118.4\left(\frac{P}{N}\right)^{1.48} \tag{5}
$$

(equation adjusted to standard units: motor rotational inertia $I_{Motor}$ $\mathrm{(kg\,m^2)}$, shaft power $P$ $\mathrm{(kW)}$ at rated conditions, shaft speed (rpm)).

Full dataset from *Fluid Transients in Pipeline Systems (Thorley)*:

![[motor_inertia_thorley.png]]

## Rundown time estimate

### Euler timestep method 

Repeat over a constant timestep $\Delta t$ in a spreadsheet:

1. Known shaft speed.
2. Calculate power (starting from shaft power at operating conditions). $P=P_0\left(\frac{\omega}{\omega_0}\right)^3$
3. Calculate torque. $T=\frac{P}{\omega}$
4. Calculate deceleration. $\alpha=-\frac{T}{I_{Total}}$
5. Calculate new speed. $\omega_{i+1}=\omega_i+\alpha\Delta t$
6. Repeat

### Direct calculation of rundown time at a given final speed ratio

Power–torque relationship
$$  
T=\frac{P}{\omega} \tag{6}
$$
From Newton’s second law for rotation, the net torque acting on a rotating system is equal to the product of total inertia and angular acceleration:

$$
T=I_{\mathrm{Total}}\alpha \tag{7}
$$

where $I_{Total}$​ is the combined rotational inertia of the pump and any coupled rotating equipment.

Angular acceleration is defined as:

$$
\alpha=\frac{d\omega}{dt} \tag{8}
$$

Substitute into the torque balance:

$$
I_{\mathrm{Total}}\frac{d\omega}{dt}=-\frac{P}{\omega} \tag{9}
$$

For a centrifugal pump operating under [[affinity laws]], power scales with the cube of rotational speed:

$$
P=P_0\left(\frac{\omega}{\omega_0}\right)^3 \tag{10}
$$

where $P_0$​ and $\omega_0$ are the initial operating power and speed respectively.

Substitute power into torque balance:

$$
I_{\mathrm{Total}}\frac{d\omega}{dt}=-\frac{P_0}{\omega_0^3}\omega^2 \tag{11}
$$

Integrating to find total rundown time:

$$
\boxed{t=\frac{I_{\mathrm{Total}}\omega_0^2}{P_0}\left(\frac{1}{r}-1\right)} \tag{12}
$$
Where
$$
r=\frac{\omega}{\omega_0}=\frac{N}{N_0} \tag{13}
$$