---
title: Rigid Bodies and Variable Forces Worked Examples
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/02 Mechanics/06 Rigid Bodies and Variable Forces/00 Overview|Rigid Bodies and Variable Forces]]"
status: active
tags:
  - mathematics/mechanics
  - worked-examples
---

# Rigid Bodies and Variable Forces Worked Examples

These examples model the 9231 route through rigid-body equilibrium, centre of
mass, sliding and toppling, work by variable forces, and separable
variable-force motion. Take $g=10\ \mathrm{m\ s^{-2}}$ where needed.

## Source Route

- CAIE Further Mathematics 9231 section 3.2: equilibrium of a rigid body,
  moments, centre of mass, composite bodies, sliding, and toppling.
- CAIE Further Mathematics 9231 section 3.5: linear motion under a variable
  force using separable differential equations, including $a=v\,dv/dx$.

## Example 1: Beam Reactions by Moments

**Prompt.** A uniform beam $AB$ has length $6\ \mathrm{m}$ and weight
$120\ \mathrm{N}$. It is supported at both ends. A $180\ \mathrm{N}$ load acts
$2\ \mathrm{m}$ from $A$. Find the support reactions.

**Solution.**

Let the reactions at $A$ and $B$ be $R_A$ and $R_B$. Taking moments about $A$,

$$
6R_B=120(3)+180(2).
$$

Thus

$$
R_B=120\ \mathrm{N}.
$$

Vertical equilibrium gives

$$
R_A+R_B=120+180,
$$

so

$$
R_A=180\ \mathrm{N}.
$$

**Check.** Taking moments about $B$ gives the same value for $R_A$.

## Example 2: Centre of Mass of a Composite Lamina

**Prompt.** A uniform lamina is made from a $4\ \mathrm{m}$ by
$2\ \mathrm{m}$ rectangle with lower-left corner at the origin, and a
$2\ \mathrm{m}$ by $3\ \mathrm{m}$ rectangle placed above its left half. Find
the centre of mass.

**Solution.**

Use areas as masses. The first rectangle has area $8$ and centre $(2,1)$. The
second rectangle has area $6$ and centre $(1,3.5)$.

Therefore

$$
\bar x=\frac{8(2)+6(1)}{8+6}=\frac{11}{7},
$$

and

$$
\bar y=\frac{8(1)+6(3.5)}{14}=\frac{29}{14}.
$$

The centre of mass is

$$
\left(\frac{11}{7},\frac{29}{14}\right).
$$

**Check.** The point lies left of the wide rectangle's centre because extra
area was added on the left.

## Example 3: Sliding or Toppling First

**Prompt.** A rectangular block has weight $400\ \mathrm{N}$, base width
$1.0\ \mathrm{m}$, and height $2.0\ \mathrm{m}$. A horizontal force $P$ is
applied at height $1.5\ \mathrm{m}$. The coefficient of friction is $0.30$.
Decide whether the block slides or topples first.

**Solution.**

Sliding begins when

$$
P=\mu R=0.30(400)=120\ \mathrm{N}.
$$

Toppling about the lower edge begins when

$$
P(1.5)=400(0.5).
$$

Thus

$$
P=133\ \mathrm{N}\quad \text{to 3 s.f.}
$$

Since $120<133$, the block slides first.

**Check.** The limiting friction is reached before the toppling moment is
large enough.

## Example 4: Work Done by a Variable Force

**Prompt.** A force $F=3x^2+2$ acts in the direction of motion from $x=0$ to
$x=4$. Find the work done. If it acts on a $2\ \mathrm{kg}$ particle initially
at rest on a smooth horizontal line, find the speed at $x=4$.

**Solution.**

Work is

$$
W=\int_0^4(3x^2+2)\,dx.
$$

So

$$
W=\left[x^3+2x\right]_0^4=72\ \mathrm{J}.
$$

Using work-energy,

$$
\frac12(2)v^2=72.
$$

Thus

$$
v=8.49\ \mathrm{m\ s^{-1}}\quad \text{to 3 s.f.}
$$

**Check.** Work is measured in joules, so it can be equated to a change in
kinetic energy.

## Example 5: Force Given as a Function of Time

**Prompt.** A $3\ \mathrm{kg}$ particle has initial velocity
$2\ \mathrm{m\ s^{-1}}$. It moves under a force $F=12-3t$ in the direction of
motion. Find its velocity at time $t$.

**Solution.**

Newton's second law gives

$$
3\frac{dv}{dt}=12-3t.
$$

So

$$
\frac{dv}{dt}=4-t.
$$

Integrate:

$$
v=4t-\frac12t^2+C.
$$

Using $v=2$ when $t=0$ gives $C=2$, so

$$
v=2+4t-\frac12t^2.
$$

**Check.** The force becomes zero at $t=4$, but the velocity need not be zero
then.

## Example 6: Force Given as a Function of Displacement

**Prompt.** A $2\ \mathrm{kg}$ particle moves on a line under force $F=8x$.
At $x=0$, its speed is $3\ \mathrm{m\ s^{-1}}$. Find its speed at $x=2$.

**Solution.**

Use $a=v\,dv/dx$:

$$
2v\frac{dv}{dx}=8x.
$$

Separate variables:

$$
v\,dv=4x\,dx.
$$

Integrate from $x=0$, $v=3$ to $x=2$, $v=V$:

$$
\int_3^V v\,dv=\int_0^2 4x\,dx.
$$

Thus

$$
\frac12(V^2-9)=8.
$$

So

$$
V=5\ \mathrm{m\ s^{-1}}.
$$

**Check.** The force does positive work, so the speed increases.

## Example 7: Velocity-Dependent Resistance

**Prompt.** A particle of mass $2\ \mathrm{kg}$ moves in a straight line with
resistance $4v\ \mathrm{N}$ opposite to the motion. Its initial speed is
$12\ \mathrm{m\ s^{-1}}$. Find $v(t)$.

**Solution.**

Taking the direction of motion as positive,

$$
2\frac{dv}{dt}=-4v.
$$

So

$$
\frac{1}{v}\,dv=-2\,dt.
$$

Integrate:

$$
\ln v=-2t+C.
$$

Using $v(0)=12$,

$$
v=12e^{-2t}.
$$

**Check.** The speed decays towards zero but does not become negative in this
model.

## Example 8: Stopping Distance under a Position-Dependent Force

**Prompt.** A $2\ \mathrm{kg}$ particle starts from rest at $x=0$ and moves
under force $F=10-2x$. Find where it next comes to rest.

**Solution.**

Use $a=v\,dv/dx$:

$$
2v\frac{dv}{dx}=10-2x.
$$

Separate and integrate:

$$
v\,dv=(5-x)\,dx.
$$

From $x=0$, $v=0$ to position $x$,

$$
\frac12v^2=5x-\frac12x^2.
$$

Thus

$$
v^2=10x-x^2.
$$

The particle is next at rest when $v=0$ and $x\ne0$:

$$
10x-x^2=0.
$$

So

$$
x=10\ \mathrm{m}.
$$

**Check.** The force becomes negative after $x=5$, so it can slow the particle
to rest.
