---
title: Mathematical Tools and Formulae
subject: Mathematics
syllabus:
  - 9709
  - 9231
status: draft
tags:
  - mathematics/reference
---

# Mathematical Tools and Formulae

This reference collects reusable mathematical tools from CAIE 9709 and 9231. Formulae are written in LaTeX for Obsidian rendering.

## Algebra

- Complete the square: $ax^2 + bx + c = a(x-h)^2 + k$.
- Discriminant: $b^2 - 4ac$.
- Factor theorem: if $f(a)=0$, then $(x-a)$ is a factor of $f(x)$.
- Remainder theorem: the remainder on division by $(x-a)$ is $f(a)$.

## Functions

- Composite functions require the range of the inner function to lie within the domain of the outer function.
- An inverse function exists on a domain where the function is one-one.
- Graph transformations should be checked with test points and domain/range changes.

## Calculus

- Product rule: $\frac{d}{dx}(uv)=u\frac{dv}{dx}+v\frac{du}{dx}$.
- Quotient rule: $\frac{d}{dx}\left(\frac{u}{v}\right)=\frac{v\frac{du}{dx}-u\frac{dv}{dx}}{v^2}$.
- Chain rule: $\frac{dy}{dx}=\frac{dy}{du}\frac{du}{dx}$.
- Definite integral as area or accumulated change: $\int_a^b f(x)\,dx$.
- Integration by parts: $\int u\,dv = uv - \int v\,du$.

## Vectors and Matrices

- Scalar product: $\mathbf{a}\cdot\mathbf{b}=|\mathbf{a}||\mathbf{b}|\cos\theta$.
- Vector equation of a line: $\mathbf{r}=\mathbf{a}+\lambda\mathbf{b}$.
- Plane forms include $ax+by+cz=d$ and $\mathbf{r}\cdot\mathbf{n}=p$.
- Matrix product order matters; $AB$ usually represents applying $B$ first and then $A$.
- A non-singular matrix has an inverse; a singular matrix does not.

## Probability and Statistics

- Expected value for a discrete random variable: $E(X)=\sum xP(X=x)$.
- Variance: $\operatorname{Var}(X)=E(X^2)-[E(X)]^2$.
- For a continuous random variable, probabilities are areas: $P(a<X<b)=\int_a^b f(x)\,dx$.
- Standardisation for a normal variable: $Z=\frac{X-\mu}{\sigma}$.

## How to Use This Reference

Use this file as a quick reminder only. The relevant topic note should contain the assumptions, method conditions, examples, and traps.
