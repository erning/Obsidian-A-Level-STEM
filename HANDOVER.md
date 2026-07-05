# HANDOVER: Replace Template Study Materials with Real Content

This document is the execution plan for completing this vault's study
materials. It is written for implementing agents. Read it fully before
editing anything, and read `AGENTS.md` first: every rule there applies to
this work and is not repeated here.

## 1. Mission

An audit on 2026-07-06 found that 52 of the 53 topic packs contain
template-filler files instead of real study materials. The mission is to
replace every template file with complete, accurate, self-contained
content, verified against the official CAIE sources under `assets/`.

The vault's own `README.md` promises this study loop per topic:
lecture notes → worked examples → practice problems → solutions → review
checklist. Today the middle three steps are empty shells in 52 topics.
After this work, every step must be real.

## 2. Exact Scope

For each of the 52 topic packs listed in the progress table (section 9),
rewrite these four files:

| File | Current state | Fingerprint of template text |
|---|---|---|
| `20 Worked Examples.md` | Generic 5-step "solution" repeated per syllabus bullet | `Name the relevant concept from` |
| `30 Key Practice Problems.md` | Prompts like "Use this idea in a complete solution: <bullet>" | `Use this idea in a complete solution` |
| `31 Key Practice Solutions.md` | Generic marking advice, no actual solutions | `A strong solution should show how this idea fits` |
| `80 Review Checklist.md` | Topic-specific lists but a stock closing block | `I can explain the purpose of` |

When a topic is finished, none of the four fingerprint strings may remain
in its folder. This is the mechanical completion check.

Out of scope: `00 Overview.md` and both lecture notes are real content and
must not be rewritten. However, while working through a topic's syllabus
outcomes you must cross-check the English lecture note for coverage gaps or
factual errors (see section 5, step 2). Fix small, certain errors in place;
log anything larger in section 10 instead of rewriting.

## 3. Reference Standard

`20 Mathematics/01 Pure Mathematics/01 Algebra and Functions/` is the one
completed pack. Before writing anything, read its four files. They define
the target:

- `20 Worked Examples.md` — 10 examples, each with a descriptive title
  (e.g. "Discriminant as a Tangency Condition"), a concrete prompt with
  actual numbers/functions, a worked solution showing reasoning and method
  choice, and a check.
- `30 Key Practice Problems.md` — 25 original problems grouped into themed
  sections (A. Quadratics, B. Functions, …, E. Mixed Review). Concrete
  problems, no answers anywhere in the file.
- `31 Key Practice Solutions.md` — mirrors the problem numbering exactly;
  full working, final answers, checks where useful.
- `80 Review Checklist.md` — checklist items tied to the actual skills
  exercised by the examples and problems, not stock phrases.

## 4. Sources of Truth

Verify scope, terminology, and notation against these local files. Do not
write from memory when a source can be checked.

Syllabus PDFs (small, authoritative for scope — primary source):

- `assets/syllabus/9702 - Physics/CAIE Physics 9702 Syllabus 2025-2027.pdf`
- `assets/syllabus/9709 - Mathematics/CAIE Mathematics 9709 Syllabus 2026-2027.pdf`
- `assets/syllabus/9231 - Further Mathematics/CAIE Further Mathematics 9231 Syllabus 2026-2027.pdf`

Use these current editions as primary. The 2028-2030 editions sit alongside
them; consult them only if a section reference from a note does not match.

Coursebooks (large, use for terminology, notation, and difficulty
calibration; read specific pages with the Read tool's `pages` parameter):

- `assets/course-books/9702 - Physics/9702 - Physics Coursebook.pdf`
- `assets/course-books/9709 - Mathematics/` — Pure Mathematics 1, Pure
  Mathematics 2 and 3, Mechanics, Probability and Statistics 1 and 2
- `assets/course-books/9231 - Further Mathematics/` — Coursebook plus
  Hodder FP1/FP2

Each topic's `00 Overview.md` has a "Source Alignment" section giving the
exact syllabus section numbers and the coursebook chapter. Start there; it
saves searching the PDFs.

The frontmatter `syllabus:` field tells you the level: math topics marked
`[9709, 9231]` must include Further Mathematics depth where the topic spans
both syllabuses, with the 9231-only material clearly identifiable (a
dedicated section or labelled problems), so a 9709-only pass through the
topic is still coherent.

## 5. Per-Topic Workflow

Work one topic at a time, in this order:

1. **Scope.** Read the topic's `00 Overview.md` and `10 Lecture Notes.md`.
   Read the matching syllabus sections in the PDF. List the learning
   outcomes the materials must cover.
2. **Coverage check.** Compare the lecture note against those outcomes.
   Fix small, certain errors directly. Log missing subtopics or doubtful
   claims in section 10 of this file; do not rewrite the lecture note.
3. **Worked examples.** Write 6-10 examples (10 for broad topics, 6-7 for
   narrow ones such as `14 Temperature`). Each example: descriptive title,
   concrete prompt, full reasoning that models method selection, and an
   explicit check (units/signs/limits for physics; conditions/domain/
   verification for math). Together the examples must touch every major
   outcome from step 1.
4. **Practice problems.** Write 15-25 original problems in themed sections
   ending with a Mixed Review section. Cover the same outcomes at graded
   difficulty: routine, standard, and a few stretch problems. Physics
   problems use realistic values and SI units. No answers in this file.
5. **Solutions.** Write `31 Key Practice Solutions.md` mirroring the
   problem numbering exactly: complete working, final answers (exact form
   for math where natural; correct significant figures and units for
   physics), and checks where useful.
6. **Numeric verification.** Verify every numeric or algebraic final
   answer with `.venv/bin/python` (sympy for algebra/calculus, numpy/scipy
   for numerics). Write throwaway scripts in a temp directory, never in
   the repo. Do not commit or skip this step: wrong answers in a
   solutions file are worse than no file.
7. **Checklist refresh.** Update `80 Review Checklist.md`: keep whatever
   items are genuinely topic-specific and accurate, replace the stock
   "Ready to Move On When" block with criteria tied to the skills the new
   examples and problems actually exercise.
8. **Quality gates.** Run the checks in section 6.
9. **Mark progress.** Set `status: active` in the frontmatter of the four
   rewritten files, tick the topic's row in the progress table below, and
   commit (section 7).

## 6. Quality Gates (per topic, before committing)

- `git diff --check` passes.
- Grep the topic folder for the four fingerprint strings (section 2):
  zero hits.
- No formula-like code spans: nothing like `` `\frac...` `` — all math in
  `$...$` or `$$...$$`.
- English files contain no em dashes (—) and no curly quotes (“ ”).
- `\times` is always followed by a space or `\` in LaTeX (`\times 10^{3}`,
  not `\times10^{3}`).
- Problem numbering in `30` and `31` matches one-to-one.
- Every numeric/algebraic answer in `31` was checked by script (step 6).
- Frontmatter, `parent:` links, and tags preserved from the existing files.
- Internal wikilinks resolve (paths are exact, including `00 Overview`).

## 7. Batching, Commits, and Handoff Mechanics

- One commit per topic, conventional commit in English, e.g.
  `docs(physics): write real worked examples and practice set for oscillations`.
  Include the progress-table tick and any lecture-note micro-fixes for that
  topic in the same commit.
- Suggested batch size per agent session: 3-5 topics from the same section
  (amortizes syllabus reading, keeps context manageable). The batch column
  in the progress table gives a default grouping; it is a suggestion, not a
  lock. Never split one topic across sessions.
- Before starting a batch, `git pull` (if a remote exists) and re-read the
  progress table: another agent may have advanced it. Claim a batch by
  working it; the table plus `status: active` frontmatter is the ledger.
- Do not commit anything under `assets/` (gitignored), `.venv/`, or
  scratch scripts.

Kick-off prompt template for an implementing agent:

> Read `HANDOVER.md` and `AGENTS.md` at the repo root of
> `/Users/erning/projects/A-Level-STEM`. Implement batch <ID> following the
> per-topic workflow and quality gates exactly. One commit per topic.
> Update the progress table as you go.

## 8. Content Calibration Notes

- Difficulty target: CAIE A-Level (and Further, where marked). Calibrate
  against coursebook exercises, not against university-level treatments.
- Problems must be original, not copied from coursebooks or past papers.
  Model the *style* of CAIE questions (multi-part, contextual for physics
  and statistics, structured "show that" chains for pure math).
- Physics: carry data with realistic magnitudes; give constants used
  (e.g. $g = 9.81\ \mathrm{m\ s^{-2}}$); require explicit unit handling.
- Statistics: state distributions and assumptions; include interpretation
  in context, not just computation.
- Experimental Thinking packs (2): examples and problems are about
  uncertainty arithmetic, tabulation, graph linearization, and experiment
  design critique, matching the two lecture notes' scope. Same file
  structure applies.
- English throughout; no Chinese companions for examples/problems/solutions
  (per `AGENTS.md`, Chinese is only for lecture-note companions).
- New diagrams are optional. If a problem genuinely needs a figure,
  generate an SVG into `assets/generated/<subject>/` following existing
  naming, and embed it; otherwise describe the setup in words.

## 9. Progress Table

Status: `[ ]` pending, `[x]` done (committed). 52 topics.

### Physics 9702 — Topics (batches P1-P5)

- [x] P1 · `10 Physics/01 Topics/01 Physical Quantities and Units`
- [x] P1 · `10 Physics/01 Topics/02 Kinematics`
- [x] P1 · `10 Physics/01 Topics/03 Dynamics`
- [x] P1 · `10 Physics/01 Topics/04 Forces Density and Pressure`
- [x] P1 · `10 Physics/01 Topics/05 Work Energy and Power`
- [x] P2 · `10 Physics/01 Topics/06 Deformation of Solids`
- [x] P2 · `10 Physics/01 Topics/07 Waves`
- [x] P2 · `10 Physics/01 Topics/08 Superposition`
- [x] P2 · `10 Physics/01 Topics/09 Electricity`
- [x] P2 · `10 Physics/01 Topics/10 DC Circuits`
- [x] P3 · `10 Physics/01 Topics/11 Particle Physics`
- [x] P3 · `10 Physics/01 Topics/12 Motion in a Circle`
- [x] P3 · `10 Physics/01 Topics/13 Gravitational Fields`
- [x] P3 · `10 Physics/01 Topics/14 Temperature`
- [x] P3 · `10 Physics/01 Topics/15 Ideal Gases`
- [x] P4 · `10 Physics/01 Topics/16 Thermodynamics`
- [x] P4 · `10 Physics/01 Topics/17 Oscillations`
- [x] P4 · `10 Physics/01 Topics/18 Electric Fields`
- [x] P4 · `10 Physics/01 Topics/19 Capacitance`
- [x] P4 · `10 Physics/01 Topics/20 Magnetic Fields`
- [x] P5 · `10 Physics/01 Topics/21 Alternating Currents`
- [x] P5 · `10 Physics/01 Topics/22 Quantum Physics`
- [x] P5 · `10 Physics/01 Topics/23 Nuclear Physics`
- [x] P5 · `10 Physics/01 Topics/24 Medical Physics`
- [x] P5 · `10 Physics/01 Topics/25 Astronomy and Cosmology`

### Physics 9702 — Experimental Thinking (batch P6)

- [x] P6 · `10 Physics/02 Experimental Thinking/Measurement and Data Presentation`
- [x] P6 · `10 Physics/02 Experimental Thinking/Experimental Design and Data Analysis`

### Mathematics — Pure (batches M1-M3; 01 Algebra and Functions already done)

- [x] M1 · `20 Mathematics/01 Pure Mathematics/02 Coordinate Geometry and Graphs`
- [x] M1 · `20 Mathematics/01 Pure Mathematics/03 Trigonometry and Circular Measure`
- [x] M1 · `20 Mathematics/01 Pure Mathematics/04 Sequences Series and Binomial Expansions`
- [x] M1 · `20 Mathematics/01 Pure Mathematics/05 Differentiation`
- [x] M2 · `20 Mathematics/01 Pure Mathematics/06 Integration`
- [x] M2 · `20 Mathematics/01 Pure Mathematics/07 Logarithms Exponentials and Numerical Methods`
- [x] M2 · `20 Mathematics/01 Pure Mathematics/08 Vectors`
- [x] M2 · `20 Mathematics/01 Pure Mathematics/09 Complex Numbers`
- [x] M3 · `20 Mathematics/01 Pure Mathematics/10 Matrices and Transformations`
- [x] M3 · `20 Mathematics/01 Pure Mathematics/11 Proof and Mathematical Induction`
- [x] M3 · `20 Mathematics/01 Pure Mathematics/12 Polar Coordinates and Parametric Curves`
- [x] M3 · `20 Mathematics/01 Pure Mathematics/13 Further Calculus and Differential Equations`

### Mathematics — Mechanics (batches M4-M5)

- [x] M4 · `20 Mathematics/02 Mechanics/01 Forces and Equilibrium`
- [ ] M4 · `20 Mathematics/02 Mechanics/02 Kinematics and Newtonian Motion`
- [ ] M4 · `20 Mathematics/02 Mechanics/03 Momentum Collisions and Impulse`
- [ ] M5 · `20 Mathematics/02 Mechanics/04 Work Energy Power and Elasticity`
- [ ] M5 · `20 Mathematics/02 Mechanics/05 Projectiles and Circular Motion`
- [ ] M5 · `20 Mathematics/02 Mechanics/06 Rigid Bodies and Variable Forces`

### Mathematics — Probability and Statistics (batches M6-M7)

- [ ] M6 · `20 Mathematics/03 Probability and Statistics/01 Data Representation and Summary`
- [ ] M6 · `20 Mathematics/03 Probability and Statistics/02 Counting and Probability`
- [ ] M6 · `20 Mathematics/03 Probability and Statistics/03 Discrete Random Variables`
- [ ] M6 · `20 Mathematics/03 Probability and Statistics/04 Normal and Poisson Distributions`
- [ ] M7 · `20 Mathematics/03 Probability and Statistics/05 Continuous Random Variables`
- [ ] M7 · `20 Mathematics/03 Probability and Statistics/06 Sampling Estimation and Hypothesis Tests`
- [ ] M7 · `20 Mathematics/03 Probability and Statistics/07 Chi Squared Nonparametric and PGF`

## 10. Lecture-Note Gaps Found During Implementation

Log entries here as `- <topic path>: <gap or doubt, one line>`. Fix only
small, certain errors in place; leave rewrites for a separate decision.

(none yet)

## 11. Done Definition (whole mission)

- All 52 rows in section 9 ticked.
- `grep -r` over `10 Physics` and `20 Mathematics` for each of the four
  fingerprint strings returns zero hits.
- Section 10 reviewed by the vault owner; remaining gaps either fixed or
  explicitly accepted.
- This file can then be deleted or archived in a final
  `docs: complete study material packs` commit.
