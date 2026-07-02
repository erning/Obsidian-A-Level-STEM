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
- Do not organise learning materials around exam technique, paper structure,
  or AS/A Level separation unless the user explicitly asks. The default goal is
  conceptual self-study and long-term fluency.
