---
title: Temperature Lecture Notes
subject: Physics
syllabus: 9702
parent: "[[10 Physics/01 Topics/14 Temperature/00 Overview|Temperature]]"
status: active
tags:
  - physics/9702/topic
  - physics/9702/thermal-physics
  - lecture-notes
---

# Temperature Lecture Notes

Temperature is not the same as thermal energy or internal energy. Temperature tells us the direction in which thermal energy will be transferred. Thermal energy is transferred from a region of higher temperature to a region of lower temperature until thermal equilibrium is reached.

This topic connects three ideas: how temperature is measured, how temperature scales are defined, and how much energy is needed to change temperature or change state.

## Source Route

- Primary syllabus source: CAIE Physics 9702, Topic 14 Temperature.
- Main subtopics: thermal equilibrium, temperature scales, specific heat capacity, and specific latent heat.
- Coursebook route: temperature measurement, thermodynamic temperature, absolute zero, heating and cooling curves, specific heat capacity, and specific latent heat.
- Useful earlier knowledge: energy transfer, power, electrical energy, particle model of matter, states of matter, and graph gradients.

## Visual Guide

![[assets/generated/physics/temperature.svg]]

The visual guide links three pictures: a thermometer reaches thermal equilibrium with what it measures, the kelvin scale is anchored at absolute zero, and heating curves separate temperature change from change of state.

## 1. Temperature and Thermal Equilibrium

Thermal energy is transferred from a region of higher temperature to a region of lower temperature.

If two objects are placed in thermal contact and have different temperatures, energy is transferred between them. The hotter object loses energy and the cooler object gains energy.

When two regions have equal temperature, they are in thermal equilibrium. In thermal equilibrium there is no net transfer of thermal energy between them.

This explains how a thermometer works. A thermometer does not instantly show the temperature of the object it is placed in. It first shows its own temperature. After energy has been transferred between the thermometer and the object, they reach thermal equilibrium. Then the thermometer reading can be taken as the temperature of the object.

Key point:

$$
\text{same temperature} \iff \text{thermal equilibrium}
$$

provided the objects are able to exchange thermal energy.

## 2. Temperature, Internal Energy, and Thermal Energy

The terms are close but not identical.

Temperature is related to the average kinetic energy of particles. A higher temperature usually means particles have greater average random kinetic energy.

Internal energy is the total energy stored microscopically in a system. It is the sum of the random kinetic energies and potential energies of the particles.

Thermal energy is energy transferred because of a temperature difference.

During ordinary heating within one state, such as warming water from room temperature to a higher temperature, the average kinetic energy of the molecules increases and the temperature rises.

During a change of state, energy can be transferred while temperature stays constant. The energy changes the arrangement and separation of particles, so the potential energy part of internal energy changes.

## 3. Temperature Measurement

A thermometer uses a physical property that varies with temperature. The property is called a thermometric property.

Examples include:

- density of a liquid
- volume of a gas at constant pressure
- resistance of a metal
- e.m.f. of a thermocouple
- length of a liquid column in a liquid-in-glass thermometer

To use a property as a thermometer, the device must be calibrated. Calibration means assigning known temperature values to measured values of the thermometric property, then constructing a scale.

Important thermometer qualities:

- Range: the interval of temperatures it can measure.
- Sensitivity: how large a change in reading is produced by a small change in temperature.
- Linearity: whether equal temperature changes produce equal changes in the thermometric property.
- Response time: how quickly the thermometer reaches thermal equilibrium with the object.

Different thermometers may agree at calibration points but disagree between them if their thermometric properties are not perfectly linear.

## 4. Thermodynamic Temperature and the Kelvin Scale

The thermodynamic temperature scale does not depend on the property of any particular substance. This makes it more fundamental than a scale based on, for example, the expansion of a particular liquid.

Thermodynamic temperature is measured in kelvin, symbol $\text{K}$. The kelvin is an SI base unit.

The lowest possible temperature on the thermodynamic scale is

$$
0\ \text{K}
$$

This is absolute zero. It is the temperature at which it is impossible to remove any more energy from a substance.

The Celsius scale and kelvin scale have equal-sized temperature intervals. A change of $1\ \text{K}$ is the same size as a change of $1\ ^\circ\text{C}$.

The conversion is

$$
T\ (\text{K}) = \theta\ (^\circ\text{C}) + 273.15
$$

and

$$
\theta\ (^\circ\text{C}) = T\ (\text{K}) - 273.15
$$

For many calculations, $273$ is used when the precision of the data does not justify $273.15$.

Do not write degree kelvin. The unit is kelvin.

## 5. Celsius Values and Temperature Differences

There is a useful distinction between temperature values and temperature differences.

For absolute temperature values in gas laws and thermodynamic formulae, use kelvin.

For temperature differences, the size of $1\ \text{K}$ is the same as the size of $1\ ^\circ\text{C}$. Therefore

$$
\Delta T = 15\ \text{K}
$$

and

$$
\Delta\theta = 15\ ^\circ\text{C}
$$

represent the same temperature change.

This is why specific heat capacity calculations can use a temperature change in either kelvin or degrees Celsius, as long as it is a difference, not an absolute temperature.

## 6. Heating Curves and Particle Energy

When a substance is heated at a steady rate, a graph of temperature against time can have sloping sections and flat sections.

In a sloping section:

- the substance stays in the same state
- temperature rises
- average kinetic energy of particles increases
- internal energy increases

In a flat section:

- the substance changes state
- temperature stays constant
- average kinetic energy does not increase
- particle separation and disorder increase
- potential energy part of internal energy increases

For water, the flat section at melting corresponds to ice changing into water. The flat section at boiling corresponds to water changing into steam. Boiling needs much more energy than melting for the same mass because molecules must separate much more completely in vaporisation.

This is why energy transfer does not always mean temperature change.

## 7. Specific Heat Capacity

The specific heat capacity of a substance is the energy required per unit mass to raise the temperature of the substance by $1\ \text{K}$, or equivalently by $1\ ^\circ\text{C}$.

The equation is

$$
E = mc\Delta\theta
$$

where:

- $E$ is energy transferred in $\text{J}$
- $m$ is mass in $\text{kg}$
- $c$ is specific heat capacity in $\text{J kg}^{-1}\text{ K}^{-1}$
- $\Delta\theta$ is temperature change in $\text{K}$ or $^\circ\text{C}$

Rearranging:

$$
c = \frac{E}{m\Delta\theta}
$$

A large value of $c$ means the substance needs a lot of energy for a given mass and temperature rise. Water has a large specific heat capacity, which is why it changes temperature relatively slowly when heated or cooled.

## 8. Measuring Specific Heat Capacity

A typical electrical method uses a heater, an ammeter, a voltmeter, a thermometer, insulation, and a block or liquid sample of known mass.

The energy supplied by the heater is

$$
E = Pt
$$

and, if electrical measurements are used,

$$
P = VI
$$

so

$$
E = VIt
$$

Then

$$
c = \frac{VIt}{m\Delta\theta}
$$

Main experimental issues:

- Energy may be lost to the surroundings, making the calculated $c$ too large.
- The sample may not be at a uniform temperature if heated too quickly.
- The thermometer or container may absorb energy.
- Insulation reduces heat loss but does not remove it completely.

A graph method can improve the analysis. If temperature is plotted against time while heating at constant power, the gradient is $\frac{\Delta\theta}{\Delta t}$. Since

$$
P = mc\frac{\Delta\theta}{\Delta t}
$$

we have

$$
c = \frac{P}{m \times \text{gradient}}
$$

## 9. Specific Latent Heat

Specific latent heat is the energy required per kilogram of a substance to change its state without any change in temperature.

The equation is

$$
E = mL
$$

where:

- $E$ is energy transferred in $\text{J}$
- $m$ is mass in $\text{kg}$
- $L$ is specific latent heat in $\text{J kg}^{-1}$

There is no temperature-change term because temperature does not change during the change of state.

Specific latent heat of fusion is for melting or freezing:

$$
\text{solid} \leftrightarrow \text{liquid}
$$

Specific latent heat of vaporisation is for boiling, evaporation, or condensation:

$$
\text{liquid} \leftrightarrow \text{gas}
$$

For the same substance, the specific latent heat of vaporisation is usually larger than the specific latent heat of fusion because molecules must become much more separated in the gas state.

## 10. Measuring Specific Latent Heat

To measure the specific latent heat of vaporisation, a liquid can be boiled using an electrical heater. Measure the power supplied and the mass lost during a known time.

If the useful energy transferred to the liquid is $E = Pt$ and the mass vaporised is $m$, then

$$
L = \frac{Pt}{m}
$$

If electrical measurements are used:

$$
L = \frac{VIt}{m}
$$

For fusion, ice can be melted using a heater and the mass of water produced can be measured.

Main experimental issues:

- In vaporisation experiments, energy lost to surroundings makes the measured $L$ too large.
- In fusion experiments, energy gained from surroundings may melt some ice without being supplied by the heater, making the measured $L$ too small.
- The substance must be at the change-of-state temperature before timing the energy transfer.

## 11. Working Routine

Use this routine for temperature and heating questions:

1. Decide whether the process is a temperature change, a change of state, or both.
2. If temperature changes, use $E = mc\Delta\theta$.
3. If state changes at constant temperature, use $E = mL$.
4. If a heater is involved, calculate energy from $E = Pt$ or $E = VIt$.
5. Convert mass to kilograms.
6. Use kelvin for absolute thermodynamic temperatures.
7. For temperature changes, kelvin and degrees Celsius intervals have the same size.
8. On a heating curve, use sloping sections for specific heat capacity and flat sections for latent heat.
9. State assumptions about insulation and energy losses.

## Common Traps

- Thinking a thermometer instantly measures the object's temperature. It must reach thermal equilibrium.
- Saying thermal energy always transfers from a larger object to a smaller object. It transfers from higher temperature to lower temperature.
- Confusing temperature with internal energy.
- Using degrees Celsius as an absolute temperature in gas or thermodynamic equations.
- Forgetting that $0\ ^\circ\text{C}$ is $273.15\ \text{K}$, not $0\ \text{K}$.
- Assuming temperature always rises when energy is supplied. During a change of state, temperature is constant.
- Confusing $c$ and $L$. Specific heat capacity has unit $\text{J kg}^{-1}\text{ K}^{-1}$; specific latent heat has unit $\text{J kg}^{-1}$.
- Forgetting to convert grams to kilograms.

## Quick Self-Check

You should be able to answer these without looking back:

- What does temperature tell us about energy transfer?
- What is thermal equilibrium?
- Why does a thermometer need time before its reading is valid?
- Name four thermometric properties.
- Why is the thermodynamic temperature scale not tied to one particular substance?
- How do you convert between degrees Celsius and kelvin?
- What is absolute zero?
- When should you use $E = mc\Delta\theta$?
- When should you use $E = mL$?
- What is the difference between specific latent heat of fusion and vaporisation?

## Connections

- [[10 Physics/01 Topics/15 Ideal Gases/00 Overview|Ideal Gases]] uses kelvin temperature in gas laws and kinetic theory.
- [[10 Physics/01 Topics/16 Thermodynamics/00 Overview|Thermodynamics]] develops internal energy and the first law of thermodynamics.
- [[10 Physics/01 Topics/09 Electricity/00 Overview|Electricity]] provides $P = VI$ for electrical heating experiments.
