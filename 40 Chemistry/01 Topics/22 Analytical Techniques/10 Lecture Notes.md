---
title: "22 Analytical Techniques - Lecture Notes"
subject: Chemistry
syllabus: 9701
status: active
tags:
  - chemistry/9701/topic
  - chemistry/9701/as-level
  - chemistry/9701/analysis
---

# 22 Analytical Techniques - Lecture Notes

## Source Route

These notes follow the CAIE Chemistry 9701 AS Level subject content for topic 22, **Analytical techniques**:

- 22.1 Infrared spectroscopy
- 22.2 Mass spectrometry

They also connect topic 22 to AS practical analysis, where candidates record observations, use qualitative analysis notes, and interpret organic test results. Chromatography is included here only as supporting analysis literacy when data are provided; the formal thin-layer chromatography and gas / liquid chromatography outcomes are in A Level topic 37.

## Learning Scope

By the end of this topic you should be able to:

- analyse an infrared spectrum of a simple molecule to identify functional groups using the syllabus data section;
- analyse mass spectra in terms of $m/e$ values and isotopic abundances;
- calculate relative atomic mass from isotope abundance data or a mass spectrum;
- deduce molecular mass from the molecular ion peak;
- suggest simple fragment identities;
- use $[M+1]^+$ and $[M+2]^+$ peaks to infer carbon count and the presence of chlorine or bromine;
- combine spectral evidence with qualitative observations and reaction tests to support a structure.

## Evidence, Not Guesswork

Analytical chemistry works by narrowing possibilities. One piece of evidence rarely proves a complete structure. A strong answer combines:

- functional group evidence from infrared spectroscopy and chemical tests;
- molecular mass from the molecular ion peak;
- isotope evidence from relative peak heights;
- fragment evidence from mass spectra;
- qualitative observations such as precipitates, gas tests and colour changes;
- separation data, if the question provides chromatography results.

The best habit is to write "this evidence suggests..." and then check whether the rest of the data agree.

## Infrared Spectroscopy

Infrared spectroscopy identifies bonds by their absorption frequencies. In AS questions, use the Data section values rather than memorising a separate table.

| Bond | Functional groups containing the bond | Characteristic absorption range |
|---|---|---|
| $\ce{C-O}$ | hydroxy, ester | $1040-1300\ \mathrm{cm^{-1}}$ |
| $\ce{C=C}$ | aromatic compound, alkene | $1500-1680\ \mathrm{cm^{-1}}$ |
| $\ce{C=O}$ | amide | $1640-1690\ \mathrm{cm^{-1}}$ |
| $\ce{C=O}$ | carbonyl, carboxyl | $1670-1740\ \mathrm{cm^{-1}}$ |
| $\ce{C=O}$ | ester | $1710-1750\ \mathrm{cm^{-1}}$ |
| $\ce{C#N}$ | nitrile | $2200-2250\ \mathrm{cm^{-1}}$ |
| $\ce{C-H}$ | alkane | $2850-2950\ \mathrm{cm^{-1}}$ |
| $\ce{N-H}$ | amine, amide | $3300-3500\ \mathrm{cm^{-1}}$ |
| $\ce{O-H}$ | carboxyl | $2500-3000\ \mathrm{cm^{-1}}$ |
| $\ce{O-H}$ | hydroxy | $3200-3600\ \mathrm{cm^{-1}}$ |

### Interpreting an Infrared Spectrum

Use this routine:

1. Check for broad $\ce{O-H}$ absorption.
2. Check for $\ce{C=O}$ absorption.
3. Check for $\ce{C#N}$ or $\ce{N-H}$ if nitrogen is possible.
4. Compare the suggested functional groups with the formula, reactions and mass spectrum.

Examples:

- Broad $\ce{O-H}$ at $2500-3000\ \mathrm{cm^{-1}}$ plus $\ce{C=O}$ suggests a carboxylic acid.
- $\ce{C=O}$ in the ester range plus $\ce{C-O}$ suggests an ester.
- $\ce{C#N}$ near $2200-2250\ \mathrm{cm^{-1}}$ suggests a nitrile.
- Hydroxy $\ce{O-H}$ at $3200-3600\ \mathrm{cm^{-1}}$ without $\ce{C=O}$ suggests an alcohol, if the rest of the evidence fits.

## Mass Spectrometry

At AS Level, knowledge of the working of the mass spectrometer is not required. You need to interpret the data.

### $m/e$ Values

Mass spectra show peaks at $m/e$ values. For singly charged ions, $m/e$ is effectively the mass of the ion.

### Molecular Ion Peak

The molecular ion peak, $M^+$, gives the molecular mass of the molecule.

If a mass spectrum has a molecular ion peak at $m/e = 60$, the relative molecular mass is 60.

### Fragment Ions

Fragment peaks come from pieces of the molecule. You may be asked to suggest simple fragments.

Common AS-style fragments include:

| Fragment ion | $m/e$ |
|---|---|
| $\ce{CH3+}$ | 15 |
| $\ce{C2H5+}$ | 29 |
| $\ce{C3H7+}$ | 43 |
| $\ce{CH3CO+}$ | 43 |
| $\ce{C6H5+}$ | 77 |

Always check that the suggested fragment is chemically plausible for the molecule.

### Relative Atomic Mass from Isotopes

Use a weighted mean:

$$
A_r = \frac{\sum(\text{isotopic mass} \times \text{relative abundance})}{\sum(\text{relative abundance})}
$$

If abundances are percentages, the denominator is 100.

## $[M+1]^+$ Peaks and Carbon Count

The $[M+1]^+$ peak is mainly caused by the presence of carbon-13. The syllabus gives:

$$
n =
\frac{100 \times \text{abundance of } [M+1]^+ \text{ ion}}
{1.1 \times \text{abundance of } M^+ \text{ ion}}
$$

where $n$ is the number of carbon atoms.

Example: if $M^+$ has relative abundance 100 and $[M+1]^+$ has relative abundance 4.4:

$$
n = \frac{100 \times 4.4}{1.1 \times 100} = 4
$$

The compound contains four carbon atoms.

## $[M+2]^+$ Peaks: Chlorine and Bromine

The $[M+2]^+$ peak helps identify chlorine and bromine because they have significant isotopes two mass units apart.

Typical patterns:

| Element present | Pattern |
|---|---|
| one chlorine atom | $M : M+2 \approx 3 : 1$ |
| one bromine atom | $M : M+2 \approx 1 : 1$ |

This evidence is especially useful for halogenoalkanes. Combine it with the molecular ion peak and the structure.

## Qualitative Analysis as Evidence

AS practical assessment expects careful observations and conclusions. Important habits:

- treat unknowns with caution;
- use an appropriate quantity;
- add only the specified amount of reagent;
- record all observations, including "no change";
- use excess $\ce{NaOH(aq)}$ or $\ce{NH3(aq)}$ when precipitate solubility in excess is part of the test;
- identify gases shown by effervescence.

### Organic Analysis Tests

The practical assessment section names these organic analysis tests:

| Test | Positive result | Inference |
|---|---|---|
| Fehling's reagent | orange/red precipitate | aldehyde functional group |
| Tollens' reagent | silver mirror or black precipitate | aldehyde functional group |
| alkaline aqueous iodine | yellow precipitate | $\ce{CH3CO}$ or $\ce{CH3CH(OH)}$ group |
| acidified potassium manganate(VII) | purple to colourless | compound can be oxidised |

Topic 17 also uses 2,4-DNPH reagent to detect carbonyl compounds. A complete carbonyl analysis often uses 2,4-DNPH first, then Fehling's or Tollens' reagent to decide aldehyde or ketone.

### Gas Tests

Common gas tests from the qualitative analysis notes include:

| Gas | Test result |
|---|---|
| $\ce{NH3}$ | turns damp red litmus paper blue |
| $\ce{CO2}$ | gives a white precipitate with limewater |
| $\ce{H2}$ | pops with a lighted splint |
| $\ce{O2}$ | relights a glowing splint |

These tests often support functional group identification. For example, effervescence with a carbonate followed by $\ce{CO2}$ confirmation supports a carboxylic acid.

## Chromatography as Supporting Evidence

Chromatography separates components of a mixture. Formal CAIE 9701 learning outcomes for thin-layer chromatography and gas / liquid chromatography are in A Level topic 37, but AS-style data questions may still provide separation information.

If a question gives chromatography data:

- a pure substance normally gives one spot or one peak under the stated conditions;
- a mixture gives more than one spot or peak;
- matching spot positions or retention times can support identity when compared under the same conditions;
- for thin-layer chromatography, the $R_f$ value is:

$$
R_f = \frac{\text{distance moved by spot}}{\text{distance moved by solvent front}}
$$

Do not overclaim. Chromatography is strongest when compared with known standards under the same conditions.

## Combining Evidence to Deduce a Structure

A good structure-deduction answer follows this order:

1. Use the molecular ion peak to find molecular mass.
2. Use $[M+1]^+$ to estimate carbon count if the data are provided.
3. Use $[M+2]^+$ to check for chlorine or bromine.
4. Use infrared data to identify functional groups.
5. Use qualitative tests to confirm or rule out functional groups.
6. Use fragment peaks to support the carbon skeleton.
7. Check that the proposed structure fits every piece of evidence.

If two structures fit one piece of data, keep both until another clue separates them.

## Working Routine

- Start from the molecular ion peak for the molecular mass.
- Use the [M+1]+ peak to estimate the carbon count and the [M+2]+ peak to test for chlorine or bromine.
- Use infrared data to find functional groups, then confirm them with chemical tests.
- Combine every clue before proposing a structure.
## Common Mistakes

- Treating one infrared absorption as complete proof of a structure.
- Confusing the molecular ion peak with the base peak.
- Forgetting that $m/e$ values are not always whole molecules; many are fragments.
- Using the $[M+1]^+$ formula with percentages but mixing up numerator and denominator.
- Missing chlorine or bromine isotope patterns in $[M+2]^+$ peaks.
- Recording qualitative conclusions without the observation.
- Treating chromatography matching as proof without checking conditions or standards.

## Quick Self-Checks

1. Which infrared evidence suggests a carboxylic acid?
2. How do you find molecular mass from a mass spectrum?
3. What does a $3:1$ $M:M+2$ pattern suggest?
4. What does Fehling's reagent show when it gives an orange/red precipitate?
5. Why should "no change" be recorded in qualitative analysis?
6. What does an $R_f$ value compare?

## Connections

- [[40 Chemistry/01 Topics/17 Carbonyl Compounds/00 Overview|Carbonyl Compounds]]
- [[40 Chemistry/01 Topics/18 Carboxylic Acids and Derivatives/00 Overview|Carboxylic Acids and Derivatives]]
- [[40 Chemistry/01 Topics/19 Nitrogen Compounds/00 Overview|Nitrogen Compounds]]
- [[40 Chemistry/01 Topics/21 Organic Synthesis/00 Overview|Organic Synthesis]]
- [[40 Chemistry/02 Practical Skills/Qualitative Analysis/00 Overview|Qualitative Analysis]]
- [[40 Chemistry/04 Reference/Data and Periodic Table|Data and Periodic Table]]
