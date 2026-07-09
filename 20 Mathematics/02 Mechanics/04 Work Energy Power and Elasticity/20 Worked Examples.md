---
title: Work, Energy, Power and Elasticity Worked Examples
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[Work, Energy, Power and Elasticity](00%20Overview.md)"
status: active
tags:
  - mathematics/mechanics
  - worked-examples
---

# Work, Energy, Power and Elasticity Worked Examples

These examples model the syllabus route through work, kinetic energy,
gravitational potential energy, power, Hooke's law, and elastic potential
energy. Take $g=10\ \mathrm{m\ s^{-2}}$ unless a question states otherwise.

## Source Route

- CAIE Mathematics 9709 section 4.5: work done by a constant force, kinetic
  energy, gravitational potential energy, conservation of energy, average
  power, and $P=Fv$.
- CAIE Further Mathematics 9231 section 3.4: Hooke's law, modulus of
  elasticity, elastic potential energy, and elastic systems solved using force
  and energy.

## Example 1: Work Done by an Angled Force

**Prompt.** A force of $50\ \mathrm{N}$ acts at $30^\circ$ to the direction of
motion while its point of application moves $12\ \mathrm{m}$. Find the work
done by the force.

**Solution.**

Use the component of the force in the direction of motion:

$$
W=Fd\cos\theta.
$$

Hence

$$
W=50(12)\cos30^\circ=520\ \mathrm{J}\quad \text{to 3 s.f.}
$$

**Check.** The work is less than $50(12)=600\ \mathrm{J}$ because the full
force is not in the direction of motion.

## Example 2: Conservation of Mechanical Energy

**Prompt.** A particle is released from rest and slides down a smooth track,
dropping vertically by $5\ \mathrm{m}$. Find its speed at the lower point.

**Solution.**

The track is smooth, so mechanical energy is conserved. Loss of gravitational
potential energy equals gain in kinetic energy:

$$
mgh=\frac12mv^2.
$$

Cancel $m$:

$$
10(5)=\frac12v^2.
$$

Thus

$$
v=10\ \mathrm{m\ s^{-1}}.
$$

**Check.** The answer depends on vertical drop, not on the shape of the smooth
track.

## Example 3: Energy with Friction

**Prompt.** A $4\ \mathrm{kg}$ particle starts from rest and slides
$6\ \mathrm{m}$ down a rough plane inclined at $30^\circ$ to the horizontal.
The coefficient of friction is $0.20$. Find its speed after $6\ \mathrm{m}$.

**Solution.**

The work done by gravity down the plane is

$$
4g\sin30^\circ(6)=120\ \mathrm{J}.
$$

The normal contact force is $4g\cos30^\circ$, so the frictional force is

$$
0.20(4g\cos30^\circ).
$$

The work done against friction is

$$
0.20(4g\cos30^\circ)(6)=41.6\ \mathrm{J}\quad \text{to 3 s.f.}
$$

The gain in kinetic energy is therefore

$$
120-41.6=78.4\ \mathrm{J}.
$$

So

$$
\frac12(4)v^2=78.4.
$$

Hence

$$
v=6.26\ \mathrm{m\ s^{-1}}\quad \text{to 3 s.f.}
$$

**Check.** Friction reduces the speed below the smooth-plane value.

## Example 4: Power from Force and Velocity

**Prompt.** A car moves at constant speed $20\ \mathrm{m\ s^{-1}}$ against a
resistance of $500\ \mathrm{N}$. Find the power needed to maintain this speed.

**Solution.**

At constant speed, the driving force equals the resistance:

$$
F=500\ \mathrm{N}.
$$

Use

$$
P=Fv.
$$

Therefore

$$
P=500(20)=10000\ \mathrm{W}=10.0\ \mathrm{kW}.
$$

**Check.** The answer is a rate of doing work, so the unit is watts, not
joules.

## Example 5: Average Power When Lifting

**Prompt.** A lift raises a $60\ \mathrm{kg}$ load through
$4\ \mathrm{m}$ in $10\ \mathrm{s}$ at steady speed. Find the average power
used to raise the load, ignoring losses.

**Solution.**

The gain in gravitational potential energy is

$$
mgh=60(10)(4)=2400\ \mathrm{J}.
$$

Average power is

$$
\frac{\text{work done}}{\text{time taken}}
=\frac{2400}{10}=240\ \mathrm{W}.
$$

**Check.** Because the speed is steady, there is no change in kinetic energy.

## Example 6: Hooke's Law and Elastic Energy

**Prompt.** An elastic string has natural length $2\ \mathrm{m}$ and modulus
of elasticity $80\ \mathrm{N}$. It is stretched by $0.50\ \mathrm{m}$. Find
the tension and the elastic potential energy stored.

**Solution.**

Hooke's law gives

$$
T=\frac{\lambda x}{l}
=\frac{80(0.50)}{2}=20\ \mathrm{N}.
$$

Elastic potential energy is

$$
E=\frac{\lambda x^2}{2l}.
$$

Hence

$$
E=\frac{80(0.50)^2}{2(2)}=5\ \mathrm{J}.
$$

**Check.** The extension is $0.50\ \mathrm{m}$, not the current length
$2.50\ \mathrm{m}$.

## Example 7: Equilibrium Extension of an Elastic String

**Prompt.** A $0.5\ \mathrm{kg}$ particle hangs at rest from a vertical
elastic string of natural length $1\ \mathrm{m}$ and modulus
$20\ \mathrm{N}$. Find the extension and the elastic potential energy.

**Solution.**

At equilibrium, tension balances weight:

$$
T=mg=0.5(10)=5\ \mathrm{N}.
$$

Hooke's law gives

$$
5=\frac{20x}{1}.
$$

So

$$
x=0.25\ \mathrm{m}.
$$

The elastic potential energy is

$$
E=\frac{20(0.25)^2}{2(1)}=0.625\ \mathrm{J}.
$$

**Check.** The elastic energy is not $mgx$ at equilibrium; it is the area
under the tension-extension graph.

## Example 8: Elastic Energy Converted to Kinetic Energy

**Prompt.** A $2\ \mathrm{kg}$ particle is attached to an elastic string of
natural length $1\ \mathrm{m}$ and modulus $50\ \mathrm{N}$ on a smooth
horizontal surface. The string is extended by $0.30\ \mathrm{m}$ and the
particle is released from rest. Find its speed when the string reaches its
natural length.

**Solution.**

The initial elastic potential energy is

$$
E=\frac{50(0.30)^2}{2(1)}=2.25\ \mathrm{J}.
$$

At the natural length the elastic energy is zero, so this becomes kinetic
energy:

$$
\frac12(2)v^2=2.25.
$$

Thus

$$
v=1.50\ \mathrm{m\ s^{-1}}.
$$

**Check.** The surface is smooth and horizontal, so no gravitational or
frictional work term is needed.
