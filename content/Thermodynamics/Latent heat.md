---
tags:
  - Thermodynamics
  - PressureRelief
aliases:
  - enthalpy of vapourisation
---
# Latent heat of vapourisation

Also called enthalpy of vapourisation, the latent heat is the amount of energy (enthalpy) that must be added to a liquid substance to transform a quantity of that substance into a gas. The enthalpy of vapourisation is a function of the pressure at which the transformation (vapourisation or evaporation) takes place.

Enthalpy changes of vapourisation are always positive (heat is absorbed by the substance), whereas enthalpy changes of condensation are always negative (heat is released by the substance).

It is equal to the increased internal energy of the vapour phase compared with the liquid phase, plus the work done against ambient pressure. The increase in the internal energy can be viewed as the energy required to overcome the intermolecular interactions in the liquid.

$$\Delta H_{vap}=\Delta U_{vap}+p\Delta V\tag{1}$$

## Estimation

When latent heat data is not available from the manufacturer, from a process simulator, or obtainable by direct measurement, an estimate can be made using a few different methods:

### Clausius-Clapeyron equation

>[!Note]
>Relies on vapour pressure data.

The latent heat can be calculated from vapour pressure data using the Clausius-Clapeyron equation, which relates the vapour/liquid phase transition line to the latent heat. At least two vapour pressures measured at two temperatures are required.

$$\ln\left( \frac{P_{1}}{P_{2}} \right)=\frac{\Delta H_{vap}}{R}\left( \frac{1}{T_{2}}-\frac{1}{T_{1}} \right)\tag{2}$$

Where $P_{1}$ and $P_{2}$ are the vapour pressures at two temperatures $T_{1}$ and $T_{2}$.

>[!warning] 
> Whilst we can reconstruct the entire vapourisation curve, there will be deviation from measured data because $\Delta H_{vap}$ varies with temperature.
>

> [!warning] 
> Use caution when estimating latent heat with this method.
> 
> Example variance in $\Delta H_{vap}$ between Peng-Robinson data and the Clausius-Calapeyron estimate using toluene as an example.
> 
> NB: vapour pressure data used to construct the Clausius-Calapeyron estimate below is also Peng-Robinson.
> 
>  ![[Toluene_dH_vap_estimate.png|500]]

A good reference on this topic is [here](https://chem.libretexts.org/Bookshelves/Physical_and_Theoretical_Chemistry_Textbook_Maps/Supplemental_Modules_(Physical_and_Theoretical_Chemistry)/Physical_Properties_of_Matter/States_of_Matter/Phase_Transitions/Clausius-Clapeyron_Equation). [[Clausius-Clapeyron Equation - Chemistry LibreTexts.pdf|PDF version]].

### Trouton's rule

>[!Note]
>Relies on boiling point data.

Trouton's rule says that for many (but not all) liquids, the entropy of vapourisation is approximately the same at ~85 $J mol^{-1}K^{-1}$. The (partial) success of the rule is due to the fact that the entropy of a gas is considerably larger than that of any liquid.

$$S_{gas}\gg S_{liquid}\tag{3}$$

Therefore, the entropy of the initial state (e.g. the liquid) is negligible in determining the entropy of vapourisation.

$$\Delta S_{vap} = S_{gas}-S_{liquid}\approx S_{gas}\tag{4}$$

When a liquid vapourises its entropy goes from a modest value to a significantly larger one. This is related to the ratio of the enthalpy of vapourisation and the temperature of the transition:

$$\Delta S_{vap} =\frac{\Delta H_{vap}}{T} \tag{5}$$

$\Delta S_{vap}$  is found to be approximately constant at the boiling point. 

>[!warning] 
> $\Delta S_{vap}\approx \text{85} J mol^{-1}K^{-1}$ but this is only at atmospheric pressure. See below.
> 
> It is also not true for all substances.

This is Trouton’s rule, which is valid for many liquids (e.g, the entropy of vapourisation of toluene is 87.30 $J mol^{-1}K^{-1}$, that of benzene is 89.45 $J mol^{-1}K^{-1}$, and that of chloroform is 87.92 $J mol^{-1}K^{-1}$). Because of its convenience, the rule is used to estimate the enthalpy of vapourisation of liquids whose boiling points are known.

A good reference on this topic is [here](https://chem.libretexts.org/Bookshelves/Physical_and_Theoretical_Chemistry_Textbook_Maps/Supplemental_Modules_(Physical_and_Theoretical_Chemistry)/Thermodynamics/Fundamentals_of_Thermodynamics/Troutons_rule#:~:text=Trouton's%20rule%20says%20that%20for,than%20that%20of%20any%20liquid.). [[Trouton_s rule - Chemistry LibreTexts.pdf|PDF version]].

#### Applicability at atmospheric pressure

Toluene at ==0 barg==. This is good match between 'measured' and Trouton estimated  $\Delta H_{vap}$ when using  $\Delta S_{vap}\approx 85 J mol^{-1}K^{-1}$.

![[Toluene Trouton 1.png|500]]

Extending this to ==10 barg== gives a poor match between 'measured' and Trouton estimated  $\Delta H_{vap}$ as $\Delta S_{vap}$ decreases to 50.7 $J mol^{-1}K^{-1}$.

![[Toluene Trouton 2.png|500]]

### Watson Equation

>[!Note]
>Relies on a reference latent heat/boiling point pair, and fluid critical temperature.

If an experimental value of the latent heat at the boiling point is known, the Watson equation (Watson, 1943), can be used to estimate the latent heat at other temperatures.
$$\Delta H_{vap,T}=\Delta H_{vap,T_b}\left[ \frac{T_{c}-T}{T_{c}-T_{b}} \right]^{0.38}\tag{6}$$

$\Delta H_{vap,T}$ = latent heat at temperature $T$, kJ/kmol
$T$ = temperature, K
$\Delta H_{vap,T_b}$ = latent heat at the normal boiling point, kJ/kmol
$T_b$ = boiling point, K
$T_c$ = critical temperature, K

Over a limited range of temperature, up to 100°C, the variation of latent heat with temperature can usually be taken as linear.

*Ref: Coulson & Richardson IV (3rd edition).*

> [!warning] 
> Use caution when estimating latent heat with this method.
> 
> Example variance in $\Delta H_{vap}$ between Peng-Robinson data and the Watson equation estimate using toluene as an example.
> 
> ![[Toluene_dH_vap_estimate_Watson_Clap.png|500]]
> 
> >[!Note]
> >The above estimate is based on a $\Delta H_{vap,T_b}$ and $T_b$ pair at atmospheric pressure. The closeness of this case is also good using a non-atmospheric reference pressure.

## Minimum value for use in external fire relief case

When determining the required relief rate in #PressureRelief assessments, the latent heat is used along with the fire heat input to determine the mass flow for the relief case.

In the absence of any other data/estimate, the following guidance on minimum $\Delta H_{vap}$ from API 521 can be considered to specify the fire relief case for 'hydrocarbons'.

> 4.4.13.2.5.2 Vapor
> 
> For pressure and temperature conditions below the critical point, the rate of vapor formation (a measure of the rate of vapor relief required) is equal to the total rate of heat absorption divided by the latent heat of vaporization. The vapor to be relieved is the vapor that is in equilibrium with the liquid under conditions that exist when the PRD is relieving at its accumulated pressure.
> 
> The latent heat and relative molecular mass values used in calculating the rate of vaporization should pertain to the conditions that are capable of generating the maximum vapor rate.
> 
> The vapor and liquid composition can change as vapors are released from the system. As a result, temperature and latent-heat values can change, affecting the required size of the PRD. On occasion, a multicomponent liquid can be heated at a pressure and temperature that exceed the critical temperature or pressure for one or more of the individual components. For example, vapors that are physically or chemically bound in solution can be liberated from the liquid upon heating. This is not a standard latent-heating effect but is more properly termed degassing or dissolution. Vapor generation is determined by the rate of change in equilibrium caused by increasing temperature.
> 
> For these and other multicomponent mixtures that have a wide boiling range, it might be necessary to develop a time-dependent model where the total heat input to the vessel not only causes vaporization but also raises the temperature of the remaining liquid, keeping it at its boiling point.
> 
> The recommended practice of finding a relief vapor flow rate from the heat input to the vessel and from the latent heat of liquid contained in the vessel becomes invalid near the critical point of the fluid, where the latent heat approaches zero and the sensible heat dominates. ==If no accurate latent heat value is available for these hydrocarbons near the critical point, a minimum value of 115 kJ/kg (50 Btu/b) is sometimes acceptable as an approximation.== If pressure-relieving conditions are above the critical point, the rate of vapor discharge typically depends on the rate at which the fluid expands as a result of the heat input because a phase change does not occur.
> 
> Reference 72 gives an example of a time-dependent model used to calculate relief requirements for a vessel that is exposed to fire and that contains fluids near or above the critical range.
> 
> *Extracted from API 521 (Pressure-relieving and Depressuring Systems) 7th Edition June 2020*