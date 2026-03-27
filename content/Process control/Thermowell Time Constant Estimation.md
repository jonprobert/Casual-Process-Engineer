---
tags:
  - ProcessControl
---
# Thermowell time constant estimation

> [!NOTE] References
> 1. Principles of Measurement Systems (John P Bentley)

## Derivation of time constant

For a thermowell we can assume the probe internal temperature is largely uniform and a 'lumped system analysis' can be performed to determine the body temperature as a function of time.

Heat transfer into the body over time $dt$ = the increase of energy in the body over time $dt$.

$$UA(T_\infty-T(t)))dt=mC_PdT$$
Where:
$T_\infty$ is the bulk fluid temperature, $K$.
$U$ is the overall heat transfer coefficient, $W/m^2K$.
$A$ is the heat transfer area, $m^2$.
$m$ is the mass of the probe, $kg$.
$C_P$ us the probe material heat capacity, $kJ/kgK$.
$T$ is probe temperature, $K$. $T_0$ at time $0$.

Since it can be said that $dT=d(T(t)-T_\infty)$ when $T_\infty$ is assumed constant:

$$\frac{d(T(t)-T_\infty)}{(T(t)-T_\infty)}=-\frac{UA}{C_P}dt$$

Integrating and rearranging we find $\frac{T(t)-T_\infty}{T_0-T_\infty}=e^{-bt}$ where $b=\frac{UA}{mC_P}$. The reciprocal of $b$ is called the time constant ($s$).

$$\tau=\frac{mC_P}{UA}$$
## Heat transfer coefficient for a thermowell

**Adapted from reference 1, §14, p367.**

The temperature of a sensing element at any instant of time depends on the rate of transfer of heat both to and from the sensor. Heat transfer takes place as a result of one or more of three possible types of mechanism – conduction, convection and radiation. Conduction is the main heat transfer mechanism inside solids. 

A solid may be regarded as a chain of interconnected atoms, each vibrating about a ﬁxed  position. An increase in temperature at one end of a solid bar causes an increase in the vibrational energy and amplitude of the atoms at that end of the chain. This energy increase is transmitted from one atom to the next along the chain, so that ultimately the temperature increase is transmitted to the other end of the bar. 

For heat transfer between a sensing element and the ﬂuid in which it is situated the main heat transfer mechanism is convection. Here heat is transferred to and from the sensor by the random, highly disordered motion of molecules of ﬂuid past the sensor. This random motion and corresponding heat transfer occur even when the average velocity of the bulk ﬂuid past the sensor is zero. This is known as natural convection. If the bulk ﬂuid is made to move so that the average velocity past the sensor is no longer zero, then there is a corresponding increase in rate of heat transfer. This is referred to as forced convection.

From Newton’s law of cooling the convective heat ﬂow $W$  between a sensor at $T$ $°C$ and ﬂuid at $T_F$ $°C$ is given by:

$$W = UA(T − T_F)\tag{1}$$

Where:
$U$ is the convection heat transfer coefﬁcient, $W/m^2K$.
$A$ is the heat transfer area, $m^2$.

Heat transfer coefﬁcients are calculated using the correlation:

$$Nu=\phi(Re,Pr)\tag{2}$$

The three dimensionless numbers are

$$Nu=\frac{Ud}{k} \\ Re=\frac{vd\rho}{\mu} \\ Pr=\frac{c\mu}{k} \tag{3}$$

Where: 

$d$ is sensor diameter, $m$.
$v$ is ﬂuid velocity, $m/s$.
$\rho$ is ﬂuid density, $kg/m^3$.
$\mu$ is ﬂuid viscosity, $Pa \space s$.
$C_P$ is fluid heat capacity, $kJ/kgK$.
$k$ is ﬂuid thermal conductivity, $W/mK$.

The function $\phi$ is determined experimentally; its form depends on the shape of the sensor, the type of convection and the direction of ﬂuid ﬂow in relation to the sensor. For example, a **correlation for forced convection cross-ﬂow over a cylinder** is:

$$Nu=0.48(Re)^{0.5}(Pr)^{0.3}\tag{4}$$

Combining $(3)$ and $(4)$:

$$U=0.48\frac{k^{0.7}\rho^{0.5}{C_P}^{0.3}v^{0.5}}{d^{0.5}\mu^{0.2}} \tag{5}$$

For two-dimensional, natural and forced convection from a cylinder, the approximate correlation is

$$Nu=0.24+0.56(Re)^{0.5}\tag{6}$$

$$U=\frac{0.24k}{d}+0.56k\left( \frac{\rho v}{d\mu} \right)^{0.5}\tag{7}$$

From $(5)$ and $(7)$ we see that the convection heat transfer coefﬁcient for a given sensor depends critically on the physical properties and velocity of the surrounding ﬂuid.

## Estimation of true time constant from test data

Using the heat transfer coefficients (possibly estimated from the method above) for both the bench test and at the operating condition of the thermowell, the following simple relation can be used to estimate the true time constant.

$$\tau_{process \space fluid}=\tau_{test}\frac{U_{test}}{U_{operating \space conditions}}$$

This follows from $\tau=\frac{mC_P}{UA}$ where we assume the mass of the probe, the probe heat capacity, and heat transfer area remain constant.