# Local Python Environment

- Normal reading in Obsidian does not require Python.
- Use the project-local `.venv/` environment only when generating or
  regenerating solution sketches, checking numerical work, or creating math
  diagrams for question notes.
- PDF processing may also use the project-local `.venv/` when it requires
  Python packages.
- Do not commit `.venv/`.
- Preferred packages are `numpy`, `matplotlib`, `scipy`, `scienceplots`, and
  `sympy`.
- For Matplotlib scripts, set `MPLBACKEND=Agg` and
  `MPLCONFIGDIR=.venv/matplotlib-cache`.

# Terminology and Language

- Notes under `10 Physics/` and `20 Mathematics/` are English-first.
- Use standard CAIE syllabus and coursebook wording for topic names,
  headings, explanations, and internal link aliases.
- Do not translate technical wording from Chinese into English by guesswork.
  If a term, topic title, or definition is uncertain, check the relevant
  syllabus or coursebook under `assets/` before editing.
- Chinese may be used for separate supporting explanations or bilingual lookup
  material when explicitly requested, but it should not be the main language of
  subject notes.
- Maintain `80 References/Terminology Reference.md` as the English-to-mainland
  Chinese terminology lookup. It is a reference, not the language model for the
  main notes.
- Keep original English in homework, source question text, quoted textbook
  wording, syllabus/coursebook titles, PDF titles, filenames, link targets,
  formulas, code, paths, commands, and identifiers.
- Obsidian filenames stay English. Visible link text should normally use the
  same English topic names unless a Chinese alias is intentionally needed.

# Study Material Structure

- Convert substantial topic notes into folders when formal learning materials
  are generated. Use this default layout:
  - `00 Overview.md`
  - `10 Lecture Notes.md`
  - `10 Lecture Notes.zh-CN.md` when a Chinese companion is requested
  - `20 Worked Examples.md`
  - `30 Key Practice Problems.md`
  - `31 Key Practice Solutions.md`
  - `80 Review Checklist.md`
- Keep filenames English and URL-friendly. Chinese companion notes may use a
  `.zh-CN.md` suffix, but the basename should remain English.
- `00 Overview.md` should explain the core idea, source alignment, what to
  learn, how to study, practice directions, links to generated materials,
  connections to nearby topics, and common traps.
- `10 Lecture Notes.md` is the main subject note. Write it in English, using
  standard CAIE syllabus and coursebook terms. It should teach the topic
  directly, not merely list bullet points.
- `10 Lecture Notes.zh-CN.md` is a fast-reading Chinese explanation of the
  same topic, not a line-by-line translation. Use natural mainland Chinese
  mathematical or physics terminology. Include English terms only when they
  genuinely remove ambiguity.
- `20 Worked Examples.md` should contain representative solved examples with
  reasoning, not just final answers. Use examples to model method selection,
  diagram interpretation, algebraic structure, units, and checks.
- `30 Key Practice Problems.md` should contain focused practice prompts in
  English. Keep answers out of this file so it can be used for active recall.
- `31 Key Practice Solutions.md` should mirror the practice file and include
  clear working, final answers, and checks where useful.
- `80 Review Checklist.md` should be a compact self-test: ideas to recall,
  skills to perform, common errors to avoid, and signs that the topic is ready
  to connect with later material.
- Write all mathematical and physics formulae in LaTeX, using `$...$` for
  inline formulae and `$$...$$` for displayed formulae. Do not put formulae in
  code spans unless the text is literally code.
- Use SVG as the default format for generated diagrams, graphs, coordinate
  plots, force diagrams, statistical charts, and other line/text-based figures.
  Use PNG only for genuinely raster material such as photographs, scans,
  pixel-style images, dense heatmaps, or figures that render unreliably as SVG.
- Do not organise learning materials around exam technique, paper structure,
  or AS/A Level separation unless the user explicitly asks. The default goal is
  conceptual self-study and long-term fluency.

# Lecture Notes Writing Standard

- Before writing or rewriting lecture notes, verify the relevant scope and
  terminology from the local syllabus and coursebook files under `assets/`.
  Do not rely on memory, Chinese-to-English translation, or the previous draft
  when the official source can be checked.
- Rewrite old template-like notes as real self-study lessons. Avoid generic
  filler such as "treat this as a working skill" repeated under headings.
  The note should explain the topic in a way a motivated self-learner can read
  from start to finish.
- Preserve existing frontmatter, parent links, Obsidian wikilinks, and useful
  generated figures when rewriting. If a visual guide exists, include it near
  the beginning and explain what it is for.
- The English lecture note is the canonical version. It should use standard
  CAIE English terms, include the source route, define core quantities or
  objects, explain conditions and assumptions, show derivations where they
  matter, and include small examples or checks that make the method concrete.
- The English note should usually include sections for the learning scope,
  core ideas, representations or methods, worked-thinking routines, common
  mistakes, quick self-checks, and connections to nearby notes. Adapt the
  exact headings to the topic rather than forcing a rigid template.
- The Chinese companion note is written after the English note. It should
  match the English note's content and order closely enough for cross-reading,
  but it should read like natural mainland Chinese explanation, not translated
  English. Its purpose is quick understanding and review.
- In Chinese lecture notes, use standard mainland Chinese subject terminology.
  Include the English term in parentheses only when it prevents ambiguity or
  when the English term is the standard label students will see in source
  material.
- Do not add boilerplate disclaimers such as "this Chinese note accompanies
  the English note". Start directly with the topic.
- Keep homework prompts, original source questions, quoted material, and
  formal problem statements in English unless the user explicitly asks for a
  translation.
- Keep formulae in LaTeX in both English and Chinese notes. Do not write
  formulae in code spans. Use clear SI units and carry signs, directions, and
  assumptions explicitly in physics notes.
- For mathematics and physics notes, prefer explanatory prose, compact tables,
  derivations, diagrams, and short worked examples over long bullet lists.
  Bullets are fine for checklists, routines, conditions, and common mistakes.
- After editing lecture notes, run at least these checks when practical:
  `git diff --check`, a search for formula-like code spans, and a check that
  embedded local figures exist. For English notes, also check for accidental
  em dashes or curly quotes. For Chinese notes, check common LaTeX spacing
  issues such as `\times10`.
