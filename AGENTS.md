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
