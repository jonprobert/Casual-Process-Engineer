---
tags:
  - GravityFlow
  - Fluids
---
# Flow in partially full pipes

The [[Manning formula]] is often used to determine flow in partially full pipes however more modern practice is to use methods analogous to those used for full pipes under pressure flow based on the [[Darcy-Weisbach]] equation and the Colebrook-White equation for friction factor. The use of the Darcy Weisbach equation is further supported by our application (small diameter pipes) rather than large open channels such as rivers and waterways. The computations are made easier by the availability of a number of approximations to the Colebrook-White equation that are not explicit in friction factor.

## Inclined pipe capacity

### Flowrate
$$
Q=-15.95A_f\sqrt{R_hS_f}\log{\left [ {\left ( \frac{k_s}{14.8R_h} \right )^{1.11}}+{\frac{6.9}{4Re_R}} \right ]}
\tag{1}
$$

Where:

- $Q$ = volumetric flowrate ($m^3/s$)
- $A_f$ = cross sectional flow area ($m^2$) (not the pipe)
- $S_f$ = slope of the pipe ($m/m$)

### Hydraulic radius
$$
R_h=\frac{A}{P}
\tag{2}
$$

Where:

- $R_h$ = hydraulic radius ($m$)
- $A$ = cross sectional pipe area ($m^2$)
- $P$ = wetted perimeter ($m$)

### Reynolds number for open channel flow

$$
Re_R=\frac{\rho v R_h}{\mu}
\tag{3}
$$

Where:

- $\rho$ = liquid density ($kg/m^3$)
- $\mu$ = absolute viscosity ($Pas$)
- $v$ = fluid bulk (average) velocity ($m/s$)
- $R_h$ = hydraulic radius ($m$)
## Derivation of equation (1)

By [[Darcy-Weisbach]]:

$$
\Delta h_{f}=\frac{fLv^2}{2dg}
\tag{4}
$$

Where:
- $\Delta h_{f}$ = head loss due to friction (m)
- $f$ = friction factor
- $L$ = pipe length (m)
- $d$ = pipe diameter (m)
- $v$ = fluid bulk (average) velocity (m/s)
- $g$ = acceleration due to gravity ($m/s^2$)

Hydraulic radius is defined as:

$$
R_h=\frac{A}{P}
\tag{5}
$$

Where:

- $R_h$ = hydraulic radius ($m$)
- $A$ = cross sectional pipe area ($m^2$)
- $P$ = wetted perimeter ($m$)

So for a full pipe:

$$
R_h=\frac{d}{4}
\tag{6}
$$

Substituting into equation $(6)$ into $(4)$:

$$
\Delta h_{f}=\frac{fLv^2}{8gR_h}
\tag{7}
$$

Substituting the line slope $S_f=\frac{\Delta h_{f}}{L}$ and rearranging for velocity:

$$
v=\frac{1}{\sqrt{f}}\cdot\sqrt{8gR_hS_f}
\tag{8}
$$

$f$ can be determined from a number of approximations to the Colebrook-White equation for friction factor (ref. 1, 2). Ref. 4 presents a statistical comparison of a number of these approximations and the	Haaland equation (ref. 4, eqn 13) is selected as combining good accuracy with simplicity of formulation.

It should be noted that the equations as presented in ref. 4 include relative roughness and Reynolds	number in terms of the hydraulic diameter for full pipes $(d)$ rather than the hydraulic radius for part full pipes	$(Rh)$ and need to be re-expressed for use in this application.

$$
\frac{1}{\sqrt{f}}=-1.8\log{\left [ {\left ( \frac{\epsilon }{3.7} \right )^{1.11}}+{\frac{6.9}{Re_D}} \right ]}
\tag{9}
$$

Where:

- $\epsilon$ = relative roughness = $\frac{k_s}{d}$
- $d$ = hydraulic diameter (pipe diameter) (m)
- $k_s$ = absolute roughness (m)
- $Re_D$ = Reynolds number based on hydraulic diameter for full pipes

Reformulating the Haaland equation in terms of hydraulic radius for part full pipes $(R_h)$:

$$
\frac{1}{\sqrt{f}}=-1.8\log{\left [ {\left ( \frac{k_s }{14.8R_h} \right )^{1.11}}+{\frac{6.9}{4Re_R}} \right ]}
\tag{10}
$$

Where:

- $Re_R$ = Reynolds number based on hydraulic radius for part full pipes

Substituting equation (10) into (8):

$$
v=-1.8\log{\left [ {\left ( \frac{k_s }{14.8R_h} \right )^{1.11}}+{\frac{6.9}{4Re_R}} \right ]}\cdot\sqrt{8gR_hS_f}
\tag{11}
$$

Flowrate in the pipe $Q=vA_f$ where $A_f$ is cross sectional flow area ($m^2$) (not the pipe)

$$
Q=-15.95A_f\sqrt{R_hS_f}\log{\left [ {\left ( \frac{k_s}{14.8R_h} \right )^{1.11}}+{\frac{6.9}{4Re_R}} \right ]}
\tag{12}
$$

$R_h$ and $A_f$ can be determined using trig:

![[Liquid_height_1.png]]

Where a is the green area.
## References

1. Open Channel Flow Resistance, Yen B C, Journal of Hydraulic Engineering, Jan 2002
2. Computer Applications in Hydraulic Engineering, Halsted Methods Inc., 2002
3. Water & Wastewater Enginering Hydraulics, Casey T J, Aquaverra Research Ltd, 2004
4. A Review of Explicit Approximations of Colebrook's Equation, Genic et al, FME Transactions (2011) 39, 67-71
5. Perrys Chemical Engineers Handbook, 7th Edition
6. ASME BPE 2012
7. Designing Piping for Gravity Flow, P D Hills, Chemical Engineering, September 1983
8. HTFS Handbook, FM8, Design of Gravity Flow Systems
9. HTFS Handbook, FP3, Gravity Flow
10. Purging & Air Removal, Richard A Beier, Mechanical Engineering Technology Department, Oklahoma State University, 2009
11. Air In Pipelines, A Literature Review, HR Wallingford, Report SR 649, April 2005
12. Co-current air-water flow in downward sloping pipes, Pothof, Technical University of Delft, 2011
13. Simpson L.L. 1968 "Sizing Piping for Process Plants" Chem Eng 75 No. 13 (June 1968) p192
14. Not used.
15. Air Problems in Pipelines, A Design Manual, HR Wallingford, 2005. ISBN-10 1-898485-11-9
16. ANSI / HI 9.8 - 1998, American National Standard for Pump Intake Design
