---
title: Forces and Equilibrium Worked Examples
subject: Mathematics
syllabus:
  - 9709
  - 9231
parent: "[[20 Mathematics/02 Mechanics/01 Forces and Equilibrium/00 Overview|Forces and Equilibrium]]"
status: active
tags:
  - mathematics/mechanics
  - worked-examples
---

# Forces and Equilibrium Worked Examples

These examples model the syllabus route through force diagrams, resolving
forces, friction, limiting equilibrium, moments, centre of mass, and rigid-body
equilibrium. Take $g=9.8\ \mathrm{m\ s^{-2}}$ where a mass is given.

## Source Route

- CAIE Mathematics 9709 section 4.1: particle equilibrium, components and
  resultants, smooth and rough contacts, limiting friction, coefficient of
  friction, and Newton's third law.
- CAIE Further Mathematics 9231 section 3.2: moments of coplanar forces,
  centre of mass, rigid-body equilibrium, sliding, and toppling.

## Example 1: Resolving Forces at a Ring

**Prompt.** A light ring carries a vertical load of $30\ \mathrm{N}$. It is
held by a string making $40^\circ$ above the horizontal to the right and by a
horizontal string to the left. Find the tensions in the two strings.

**Solution.**

Let $T$ be the tension in the sloping string and $H$ the tension in the
horizontal string. Resolve vertically:

$$
T\sin40^\circ=30.
$$

Hence

$$
T=\frac{30}{\sin40^\circ}=46.7\ \mathrm{N}\quad \text{to 3 s.f.}
$$

Resolve horizontally:

$$
H=T\cos40^\circ.
$$

Therefore

$$
H=46.7\cos40^\circ=35.8\ \mathrm{N}\quad \text{to 3 s.f.}
$$

**Check.** The sloping string supplies all the upward component, while the
horizontal string balances its sideways component. Both tensions are positive,
so the assumed directions are consistent.

## Example 2: Smooth Inclined Plane

**Prompt.** A particle of mass $5\ \mathrm{kg}$ rests on a smooth plane
inclined at $25^\circ$ to the horizontal. It is held by a light string parallel
to the plane. Find the tension and the normal contact force.

**Solution.**

Choose axes parallel and perpendicular to the plane. The component of weight
down the plane is

$$
mg\sin25^\circ.
$$

Equilibrium parallel to the plane gives

$$
T=5g\sin25^\circ=20.7\ \mathrm{N}\quad \text{to 3 s.f.}
$$

The component of weight into the plane is

$$
mg\cos25^\circ.
$$

Since the plane is smooth,

$$
R=5g\cos25^\circ=44.4\ \mathrm{N}\quad \text{to 3 s.f.}
$$

**Check.** If the angle were $0^\circ$, the down-plane component would be
zero and the normal contact force would be $mg$, so the component choices have
the correct limiting behaviour.

## Example 3: Pulling a Rough Horizontal Crate

**Prompt.** A crate of mass $12\ \mathrm{kg}$ is pulled by a force
$P\ \mathrm{N}$ at $20^\circ$ above the horizontal. The coefficient of friction
between the crate and the floor is $0.35$. Find $P$ when the crate is about to
move to the right.

**Solution.**

At limiting equilibrium,

$$
F=\mu R.
$$

The upward component of the pull reduces the normal contact force, so vertical
equilibrium gives

$$
R+P\sin20^\circ=12g,
$$

or

$$
R=12g-P\sin20^\circ.
$$

Friction acts to the left. Horizontal equilibrium gives

$$
P\cos20^\circ=\mu R.
$$

Substitute for $R$:

$$
P\cos20^\circ=0.35(12g-P\sin20^\circ).
$$

Hence

$$
P(\cos20^\circ+0.35\sin20^\circ)=0.35(12g),
$$

so

$$
P=38.9\ \mathrm{N}\quad \text{to 3 s.f.}
$$

**Check.** The answer is less than $\mu mg=41.2\ \mathrm{N}$ because the
upward pull reduces $R$.

## Example 4: Least Coefficient on a Rough Incline

**Prompt.** A particle rests on a rough plane inclined at $30^\circ$ to the
horizontal. Find the least coefficient of friction needed to keep the particle
in equilibrium.

**Solution.**

For the least coefficient, the particle is just about to slide down the plane,
so friction acts up the plane and is limiting.

Resolve parallel to the plane:

$$
F=mg\sin30^\circ.
$$

Resolve perpendicular to the plane:

$$
R=mg\cos30^\circ.
$$

At limiting equilibrium,

$$
F=\mu R.
$$

Therefore

$$
mg\sin30^\circ=\mu mg\cos30^\circ,
$$

so

$$
\mu=\tan30^\circ=0.577\quad \text{to 3 s.f.}
$$

**Check.** The mass cancels, as it should: on a simple rough plane the least
coefficient depends only on the angle.

## Example 5: The Third Force for Equilibrium

**Prompt.** Two forces of $50\ \mathrm{N}$ east and $80\ \mathrm{N}$ north act
on a particle. Find the third force needed for equilibrium.

**Solution.**

The resultant of the two given forces has components

$$
(50,80).
$$

Its magnitude is

$$
\sqrt{50^2+80^2}=94.3\ \mathrm{N}\quad \text{to 3 s.f.}
$$

The angle it makes north of east is

$$
\tan^{-1}\frac{80}{50}=58.0^\circ.
$$

For equilibrium, the third force must be equal and opposite to this resultant.
It has magnitude

$$
94.3\ \mathrm{N}
$$

and acts $58.0^\circ$ south of west.

**Check.** Adding the third force gives zero horizontal component and zero
vertical component.

## Example 6: Moments for a Supported Beam

**Prompt.** A uniform horizontal beam $AB$ is $4\ \mathrm{m}$ long and has
weight $120\ \mathrm{N}$. It is hinged at $A$ and supported by a vertical
reaction at $B$. A load of $200\ \mathrm{N}$ acts $3\ \mathrm{m}$ from $A$.
Find the reaction at $B$ and the vertical reaction at $A$.

**Solution.**

Take moments about $A$ to remove the reaction at $A$. The weight of the
uniform beam acts at its midpoint, $2\ \mathrm{m}$ from $A$.

$$
4R_B=120(2)+200(3).
$$

Thus

$$
R_B=\frac{840}{4}=210\ \mathrm{N}.
$$

Vertical force equilibrium gives

$$
R_A+R_B=120+200.
$$

So

$$
R_A=320-210=110\ \mathrm{N}.
$$

**Check.** Taking moments about $B$ gives
$4R_A=120(2)+200(1)=440$, so $R_A=110\ \mathrm{N}$.

## Example 7: Centre of Mass of a Simple Composite Lamina

**Prompt.** A uniform lamina is made from three identical square plates of
side $2\ \mathrm{m}$. Their centres are at $(1,1)$, $(3,1)$, and $(1,3)$.
Find the centre of mass of the lamina.

**Solution.**

The three square plates have equal mass, so the centre of mass is the average
of their centre coordinates:

$$
\bar x=\frac{1+3+1}{3}=\frac53,
$$

and

$$
\bar y=\frac{1+1+3}{3}=\frac53.
$$

Therefore the centre of mass is

$$
\left(\frac53,\frac53\right)\ \mathrm{m}.
$$

**Check.** The answer lies inside the L-shaped region and is closer to the
inside corner than to either far arm, which matches the symmetry of the
arrangement.

## Example 8: Sliding Before Toppling or Toppling Before Sliding

**Prompt.** A rectangular block of weight $200\ \mathrm{N}$ stands on a rough
horizontal surface. Its base width is $0.60\ \mathrm{m}$ and its height is
$1.20\ \mathrm{m}$. A horizontal force $P$ is applied at height
$0.90\ \mathrm{m}$. The coefficient of friction is $0.40$. Decide whether the
block slides or topples first as $P$ is increased.

**Solution.**

The sliding threshold is

$$
P=\mu R=0.40(200)=80\ \mathrm{N}.
$$

For toppling, take moments about the lower edge on the side toward which the
block would topple. The weight acts through the centre, with horizontal
distance $0.30\ \mathrm{m}$ from this edge.

At the toppling threshold,

$$
P(0.90)=200(0.30).
$$

Hence

$$
P=\frac{60}{0.90}=66.7\ \mathrm{N}\quad \text{to 3 s.f.}
$$

Since

$$
66.7<80,
$$

the block topples before it slides.

**Check.** The roughness is large enough to prevent sliding up to
$66.7\ \mathrm{N}$, so the toppling calculation is physically relevant.
