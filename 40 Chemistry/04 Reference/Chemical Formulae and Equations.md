---
title: Chemical Formulae and Equations
subject: Chemistry
syllabus: 9701
status: active
tags:
  - chemistry/9701
  - reference
---

# Chemical Formulae and Equations

Use this note as a compact reminder for writing formulae, equations, ionic equations, and calculation-friendly chemical notation in Obsidian.

## MathJax Notation

Use mhchem style where possible:

$$
\ce{2H2 + O2 -> 2H2O}
$$

The source syntax is `\ce{2H2 + O2 -> 2H2O}`.

If mhchem is not available, use plain LaTeX:

$$
\mathrm{2H_2 + O_2 \rightarrow 2H_2O}
$$

For a single formula, use either $\ce{H2O}$ or the fallback $\mathrm{H_2O}$.

## Formula Writing

- Use correct element symbols and subscripts: $\ce{MgCl2}$, $\ce{Al2O3}$, $\ce{NH4+}$.
- Use brackets for repeated polyatomic ions: $\ce{Ca(OH)2}$, $\ce{(NH4)2SO4}$.
- Keep charges visible in ionic work: $\ce{SO4^{2-}}$, $\ce{Fe^{3+}}$, $\ce{MnO4^-}$.
- State symbols are useful when precipitation, gas formation, or phase change matters: $\ce{(s)}$, $\ce{(l)}$, $\ce{(g)}$, $\ce{(aq)}$.

## Balancing Equations

Balance atoms first, then check charge if ions are present.

$$
\ce{CaCO3 + 2HCl -> CaCl2 + CO2 + H2O}
$$

For ionic equations, remove spectator ions:

$$
\ce{Ag+(aq) + Cl-(aq) -> AgCl(s)}
$$

For acid-base neutralisation:

$$
\ce{H+(aq) + OH-(aq) -> H2O(l)}
$$

## Redox Equations

- Assign oxidation numbers where useful.
- Separate oxidation and reduction half-equations.
- Balance atoms, oxygen with $\ce{H2O}$, hydrogen with $\ce{H+}$ in acidic conditions, then charge with electrons.
- Combine half-equations so electrons cancel.

Example in acidic solution:

$$
\ce{MnO4^- + 8H+ + 5Fe^{2+} -> Mn^{2+} + 5Fe^{3+} + 4H2O}
$$

## Practical Links

- [[40 Chemistry/02 Practical Skills/Measurement Observation and Calculation/00 Overview|Measurement, Observation and Calculation]]
- [[40 Chemistry/02 Practical Skills/Qualitative Analysis/00 Overview|Qualitative Analysis]]
- [[40 Chemistry/04 Reference/Mathematical Tools for Chemistry|Mathematical Tools for Chemistry]]
