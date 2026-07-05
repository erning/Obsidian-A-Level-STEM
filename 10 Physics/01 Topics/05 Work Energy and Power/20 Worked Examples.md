---
title: Work, Energy and Power Worked Examples
subject: Physics
syllabus: 9702
parent: "[[10 Physics/01 Topics/05 Work Energy and Power/00 Overview|Work, Energy and Power]]"
status: active
tags:
  - physics/9702/topic
  - physics/9702/mechanics
  - worked-examples
---

# Work, Energy and Power Worked Examples

These examples model the standard CAIE route through work done, energy
transfer, conservation of energy, efficiency, and power. Take
$g=9.81\ \mathrm{m\ s^{-2}}$ where needed.

## Source Route

- Syllabus: CAIE Physics 9702 section 5, Work, energy and power.
- Coursebook route: Chapter 5, especially doing work, gravitational potential
  energy, kinetic energy, energy transfers, conservation of energy, and power.

## Example 1: Work Done by an Angled Pull

**Prompt.** A rope pulls a box with a force of $200\ \mathrm{N}$ at
$30^\circ$ to the horizontal. The box moves $5.0\ \mathrm{m}$ horizontally.
Calculate the work done by the rope on the box.

**Solution.**

Work done uses the component of force in the direction of displacement:

$$
W=Fs\cos\theta.
$$

Here the displacement is horizontal and the force is at $30^\circ$ to it, so

$$
W=(200)(5.0)\cos30^\circ
=866\ \mathrm{J}.
$$

The answer is positive because the force has a component in the direction of
motion.

**What this example trains.** Always check the angle between the force and the
displacement before using $W=Fs$.

## Example 2: Positive, Negative, and Zero Work

**Prompt.** A crate moves $4.0\ \mathrm{m}$ along a horizontal floor. A
$50\ \mathrm{N}$ pull acts along the motion and friction of $18\ \mathrm{N}$
acts opposite the motion. State the work done by the pull, friction, the weight,
and the normal contact force.

**Solution.**

The pull is in the direction of displacement:

$$
W_{\text{pull}}=(50)(4.0)=200\ \mathrm{J}.
$$

Friction is opposite the displacement, so its work is negative:

$$
W_{\text{friction}}=-(18)(4.0)=-72\ \mathrm{J}.
$$

The weight and normal contact force are vertical while the displacement is
horizontal. Each is at $90^\circ$ to the displacement, so each does zero work.

The net work done on the crate is

$$
200-72=128\ \mathrm{J}.
$$

**What this example trains.** A force does work only through the component
parallel to the displacement.

## Example 3: Work Done from a Force-Displacement Graph

**Prompt.** A force increases uniformly from $0$ to $40\ \mathrm{N}$ during
the first $0.60\ \mathrm{m}$ of motion, then remains at $40\ \mathrm{N}$ for a
further $0.80\ \mathrm{m}$. Find the work done.

**Solution.**

Work done is the area under the force-displacement graph.

For the first section, the area is a triangle:

$$
W_1=\frac{1}{2}(0.60)(40)=12\ \mathrm{J}.
$$

For the second section, the area is a rectangle:

$$
W_2=(0.80)(40)=32\ \mathrm{J}.
$$

Total work done:

$$
W=W_1+W_2=12+32=44\ \mathrm{J}.
$$

**What this example trains.** When the force changes with displacement, use
area, not a single force value chosen by guesswork.

## Example 4: Change in Gravitational Potential Energy

**Prompt.** A student of mass $65\ \mathrm{kg}$ climbs a vertical height of
$3.0\ \mathrm{m}$ in $4.5\ \mathrm{s}$. Calculate the gain in gravitational
potential energy and the useful output power against gravity.

**Solution.**

The gain in gravitational potential energy is

$$
\Delta E_p=mg\Delta h.
$$

So

$$
\Delta E_p=(65)(9.81)(3.0)
=1913\ \mathrm{J}.
$$

Useful power against gravity is the useful energy transferred per unit time:

$$
P=\frac{W}{t}
=\frac{1913}{4.5}
=425\ \mathrm{W}.
$$

**What this example trains.** In $\Delta E_p=mg\Delta h$, use the vertical
height change, not the path length along stairs or a slope.

## Example 5: Change in Kinetic Energy

**Prompt.** A car of mass $800\ \mathrm{kg}$ accelerates from
$20\ \mathrm{m\ s^{-1}}$ to $30\ \mathrm{m\ s^{-1}}$. Calculate the increase
in its kinetic energy.

**Solution.**

Calculate the initial and final kinetic energies separately:

$$
E_{k,i}=\frac{1}{2}(800)(20)^2
=1.60\times 10^5\ \mathrm{J},
$$

$$
E_{k,f}=\frac{1}{2}(800)(30)^2
=3.60\times 10^5\ \mathrm{J}.
$$

Therefore

$$
\Delta E_k
=3.60\times 10^5-1.60\times 10^5
=2.00\times 10^5\ \mathrm{J}.
$$

**What this example trains.** Do not square the change in speed. Kinetic energy
depends on the square of each speed.

## Example 6: Falling with Negligible Air Resistance

**Prompt.** A stone is dropped from rest through a height of $12\ \mathrm{m}$.
Use energy to find its speed just before impact, ignoring air resistance.

**Solution.**

The loss of gravitational potential energy becomes gain in kinetic energy:

$$
mgh=\frac{1}{2}mv^2.
$$

The mass cancels:

$$
v=\sqrt{2gh}.
$$

Substitute:

$$
v=\sqrt{2(9.81)(12)}
=15.3\ \mathrm{m\ s^{-1}}.
$$

**What this example trains.** Energy can find the speed without finding the
time of fall.

## Example 7: Mechanical Energy with Losses

**Prompt.** A $2.0\ \mathrm{kg}$ trolley descends a track with a vertical drop
of $5.0\ \mathrm{m}$. It starts from rest and reaches the bottom at
$8.0\ \mathrm{m\ s^{-1}}$. Find the energy transferred to internal energy and
sound, and find the percentage efficiency of the transfer to kinetic energy.

**Solution.**

Loss of gravitational potential energy:

$$
\Delta E_p=(2.0)(9.81)(5.0)=98.1\ \mathrm{J}.
$$

Gain in kinetic energy:

$$
E_k=\frac{1}{2}(2.0)(8.0)^2
=64.0\ \mathrm{J}.
$$

Energy transferred away from useful mechanical kinetic energy:

$$
98.1-64.0=34.1\ \mathrm{J}.
$$

Percentage efficiency for transfer to kinetic energy:

$$
\text{percentage efficiency}
=\frac{64.0}{98.1}\times 100\%
=65.2\%.
$$

**What this example trains.** Mechanical energy may decrease, but total energy
is still accounted for by other energy transfers.

## Example 8: Efficiency from Energy Input and Useful Output

**Prompt.** A motor receives $12.0\ \mathrm{kJ}$ of electrical energy and does
$7.5\ \mathrm{kJ}$ of useful work lifting a load. Calculate its efficiency and
the energy wasted.

**Solution.**

Efficiency is useful output divided by total input:

$$
\text{efficiency}
=\frac{7.5}{12.0}
=0.625.
$$

As a percentage,

$$
0.625\times 100\%=62.5\%.
$$

Energy not transferred usefully:

$$
12.0-7.5=4.5\ \mathrm{kJ}.
$$

**What this example trains.** Efficiency may be written as a fraction or a
percentage, but it must be based on matching energy or matching power values.

## Example 9: Power and $P=Fv$

**Prompt.** A car moves at a constant speed of $25\ \mathrm{m\ s^{-1}}$
against a total resistive force of $900\ \mathrm{N}$. Find the useful power
needed to maintain this speed. If the engine input power is $30\ \mathrm{kW}$,
find the efficiency.

**Solution.**

At constant speed, the driving force balances the resistive force, so the
useful driving force is $900\ \mathrm{N}$.

Using $P=Fv$,

$$
P=(900)(25)
=2.25\times 10^4\ \mathrm{W}
=22.5\ \mathrm{kW}.
$$

Efficiency using power values:

$$
\text{efficiency}
=\frac{22.5}{30.0}
=0.750=75.0\%.
$$

**What this example trains.** $P=Fv$ applies cleanly to steady motion when the
force is in the direction of the velocity.
