---
title: Temperature Worked Examples
subject: Physics
syllabus: 9702
parent: "[Temperature](00%20Overview.md)"
status: active
tags:
  - physics/9702/topic
  - physics/9702/thermal-physics
  - worked-examples
---

# Temperature Worked Examples

These examples model the standard CAIE route through thermal equilibrium,
thermometric properties, thermodynamic temperature, specific heat capacity,
specific latent heat, heating curves, and experimental energy-loss checks.

## Source Route

- Syllabus: CAIE Physics 9702 section 14, Temperature.
- Main subtopics: thermal equilibrium, temperature scales, specific heat
  capacity, and specific latent heat.
- Coursebook route: temperature measurement, kelvin scale, absolute zero,
  heating curves, electrical heating experiments, and changes of state.

## Example 1: Thermal Equilibrium and a Thermometer

**Prompt.** A thermometer initially at room temperature is placed in hot water.
Explain why its reading should not be taken immediately.

**Solution.**

Thermal energy is transferred from the hotter water to the cooler thermometer.
The thermometer reading changes while this energy transfer is taking place.

The thermometer gives the temperature of the water only after the thermometer
and the water have reached thermal equilibrium. At thermal equilibrium, they
have the same temperature and there is no net transfer of thermal energy
between them.

This is the basis of temperature measurement: the measuring device must reach
thermal equilibrium with the object being measured.

**What this example trains.** Temperature is linked to the direction of
thermal energy transfer, not to the total amount of internal energy in an
object.

## Example 2: Calibrating a Thermometric Property

**Prompt.** A resistance thermometer has resistance $100.0\ \Omega$ at
$0.0\ ^\circ\mathrm{C}$ and $138.5\ \Omega$ at
$100.0\ ^\circ\mathrm{C}$. Assuming a linear scale, find the temperature when
the resistance is $119.25\ \Omega$.

**Solution.**

Resistance is the thermometric property. If it varies linearly with
temperature, the fraction of the temperature interval is the same as the
fraction of the resistance interval:

$$
\frac{\theta-0.0}{100.0-0.0}
=
\frac{119.25-100.0}{138.5-100.0}.
$$

So

$$
\theta
=
100.0
\left(
\frac{19.25}{38.5}
\right)
=50.0\ ^\circ\mathrm{C}.
$$

Examples of thermometric properties include density of a liquid, volume of a
gas at constant pressure, resistance of a metal, and e.m.f. of a thermocouple.

**What this example trains.** A thermometer needs a property that changes with
temperature and a calibration scale.

## Example 3: Celsius and Kelvin

**Prompt.** Convert $25.0\ ^\circ\mathrm{C}$ and
$-40.0\ ^\circ\mathrm{C}$ into kelvin. Convert $300\ \mathrm{K}$ into degrees
Celsius. State the size of a $12\ ^\circ\mathrm{C}$ temperature change in
kelvin.

**Solution.**

Use

$$
T\ (\mathrm{K})=\theta\ (^\circ\mathrm{C})+273.15.
$$

Therefore

$$
25.0\ ^\circ\mathrm{C}
=298.15\ \mathrm{K},
$$

and

$$
-40.0\ ^\circ\mathrm{C}
=233.15\ \mathrm{K}.
$$

For $300\ \mathrm{K}$,

$$
\theta
=300-273.15
=26.85\ ^\circ\mathrm{C}.
$$

A temperature change of $12\ ^\circ\mathrm{C}$ has the same size as a
temperature change of $12\ \mathrm{K}$.

**What this example trains.** Absolute temperatures use kelvin, but Celsius
and kelvin intervals have the same size.

## Example 4: Specific Heat Capacity from Electrical Heating

**Prompt.** A $1.00\ \mathrm{kg}$ aluminium block is heated by a
$12.0\ \mathrm{V}$, $3.00\ \mathrm{A}$ heater for $300\ \mathrm{s}$. Its
temperature rises by $12.0\ \mathrm{K}$. Estimate the specific heat capacity
of aluminium, assuming all electrical energy heats the block.

**Solution.**

Electrical energy supplied:

$$
E=VIt=(12.0)(3.00)(300)=1.08 \times 10^4\ \mathrm{J}.
$$

For a temperature change,

$$
E=mc\Delta\theta.
$$

So

$$
c=\frac{E}{m\Delta\theta}
=
\frac{1.08 \times 10^4}{(1.00)(12.0)}
=900\ \mathrm{J\ kg^{-1}\ K^{-1}}.
$$

If energy is lost to the surroundings, the calculated value will be too large
because not all the supplied energy heated the block.

**What this example trains.** Use $E=mc\Delta\theta$ only for a temperature
change within one state.

## Example 5: Specific Heat Capacity from a Heating Graph

**Prompt.** A $0.20\ \mathrm{kg}$ sample is heated at constant power
$50\ \mathrm{W}$. The temperature-time graph has gradient
$0.12\ \mathrm{K\ s^{-1}}$. Find the specific heat capacity.

**Solution.**

For heating at constant power,

$$
P=mc\frac{\Delta\theta}{\Delta t}.
$$

The graph gradient is

$$
\frac{\Delta\theta}{\Delta t}=0.12\ \mathrm{K\ s^{-1}}.
$$

Therefore

$$
c=
\frac{P}{m \times \text{gradient}}
=
\frac{50}{(0.20)(0.12)}
=2.1 \times 10^3\ \mathrm{J\ kg^{-1}\ K^{-1}}.
$$

**What this example trains.** The gradient of a sloping heating-curve section
is linked to specific heat capacity.

## Example 6: Specific Latent Heat

**Prompt.** Find the energy needed to melt $0.020\ \mathrm{kg}$ of ice at its
melting point. Use $L_f=3.34 \times 10^5\ \mathrm{J\ kg^{-1}}$. Then compare
this with the energy needed to vaporise the same mass of water at its boiling
point, using $L_v=2.26 \times 10^6\ \mathrm{J\ kg^{-1}}$.

**Solution.**

For a change of state at constant temperature,

$$
E=mL.
$$

For melting,

$$
E_f=(0.020)(3.34 \times 10^5)
=6.68 \times 10^3\ \mathrm{J}.
$$

For vaporisation,

$$
E_v=(0.020)(2.26 \times 10^6)
=4.52 \times 10^4\ \mathrm{J}.
$$

The vaporisation energy is much larger because molecules must become much more
separated in the gas state.

**What this example trains.** Latent heat changes state without changing
temperature.

## Example 7: A Combined Heating Process

**Prompt.** A $0.050\ \mathrm{kg}$ sample of ice at
$-10\ ^\circ\mathrm{C}$ is heated until it becomes water at
$20\ ^\circ\mathrm{C}$. Use
$c_{\text{ice}}=2100\ \mathrm{J\ kg^{-1}\ K^{-1}}$,
$L_f=3.34 \times 10^5\ \mathrm{J\ kg^{-1}}$, and
$c_{\text{water}}=4200\ \mathrm{J\ kg^{-1}\ K^{-1}}$.

**Solution.**

There are three stages.

First warm the ice from $-10\ ^\circ\mathrm{C}$ to
$0\ ^\circ\mathrm{C}$:

$$
E_1=mc_{\text{ice}}\Delta\theta
=(0.050)(2100)(10)
=1.05 \times 10^3\ \mathrm{J}.
$$

Then melt the ice at constant temperature:

$$
E_2=mL_f
=(0.050)(3.34 \times 10^5)
=1.67 \times 10^4\ \mathrm{J}.
$$

Then warm the water from $0\ ^\circ\mathrm{C}$ to
$20\ ^\circ\mathrm{C}$:

$$
E_3=mc_{\text{water}}\Delta\theta
=(0.050)(4200)(20)
=4.20 \times 10^3\ \mathrm{J}.
$$

Total energy:

$$
E=E_1+E_2+E_3
=2.20 \times 10^4\ \mathrm{J}.
$$

**What this example trains.** Split a heating curve into sloping sections and
flat sections before choosing equations.

## Example 8: Measuring Latent Heat of Vaporisation

**Prompt.** A heater supplies $12.0\ \mathrm{V}$ at $2.50\ \mathrm{A}$ for
$600\ \mathrm{s}$ to a boiling liquid. The mass lost is
$8.0 \times 10^{-3}\ \mathrm{kg}$. Estimate the specific latent heat of
vaporisation.

**Solution.**

Electrical energy supplied:

$$
E=VIt=(12.0)(2.50)(600)=1.80 \times 10^4\ \mathrm{J}.
$$

Use

$$
L=\frac{E}{m}.
$$

So

$$
L=
\frac{1.80 \times 10^4}{8.0 \times 10^{-3}}
=2.25 \times 10^6\ \mathrm{J\ kg^{-1}}.
$$

The sample should already be boiling before timing begins. If some supplied
energy heats the container or is lost to the surroundings, the calculated
value of $L$ will be too large.

**What this example trains.** In a latent-heat experiment, energy should go
into changing state, not raising temperature first.
