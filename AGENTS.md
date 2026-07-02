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
