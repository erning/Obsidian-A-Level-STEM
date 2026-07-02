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

- Maintain `00 Reference/Terminology Glossary.md` as the shared glossary for
  CAIE A Level English terms and mainland China Chinese terminology.
- In introductions, explanations, summaries, and teaching notes, prefer the
  Chinese professional terms from the glossary.
- When a term may be ambiguous, or when first introducing a CAIE-specific
  term, write `中文术语（English term）`.
- Keep original English in homework, source question text, quoted textbook
  wording, syllabus/coursebook titles, PDF titles, filenames, link targets,
  formulas, code, paths, commands, and identifiers.
- Obsidian filenames stay English; visible link text may use Chinese aliases.
