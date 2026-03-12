---
name: data-analysis
description: End-to-end Python data analysis workflow from exploration through modeling to publication-ready tables and figures
argument-hint: "[dataset path or analysis goal]"
allowed-tools: ["Read", "Grep", "Glob", "Write", "Edit", "Bash", "Task"]
---

# Data Analysis Workflow (Python)

Run an end-to-end analysis in Python and produce reproducible outputs.

## Constraints

- Follow `.claude/rules/python-code-conventions.md`
- Save scripts to `scripts/python/`
- Save outputs to `output/`
- Persist reusable data artifacts with `to_parquet()` / `to_pickle()` when relevant
- Run `python-reviewer` before finalizing

## Steps

1. **Setup**
   - Create script with header (purpose, inputs, outputs)
   - Import required libraries (`pandas`, `numpy`, `statsmodels`/`linearmodels`, plotting libs)
   - Set seed for stochastic workflows

2. **EDA**
   - Summary stats, missingness checks, distribution and relationship plots

3. **Modeling**
   - Implement user-specified model(s)
   - Use appropriate standard errors/clustering
   - Compare baseline vs extended specifications

4. **Publication-ready outputs**
   - Export tables (`.tex` and/or `.html`)
   - Export figures with explicit dimensions/resolution

5. **Persist + review**
   - Save intermediate artifacts for downstream Quarto/docs use
   - Invoke python-reviewer and address critical/high findings

## Output expectation

- `scripts/python/<analysis_name>.py`
- `output/tables/*`
- `output/figures/*`
- Optional serialized artifacts (`.parquet` / `.pkl`)
