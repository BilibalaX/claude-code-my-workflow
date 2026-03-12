---
paths:
  - "**/*.py"
  - "Figures/**/*.py"
  - "scripts/**/*.py"
---

# Python Code Standards

**Standard:** Senior data-engineering quality + research reproducibility.

---

## 1. Reproducibility

- Set randomness explicitly (`random.seed`, `numpy.random.seed`) when stochastic code is used
- Import dependencies at top of file
- Use repository-relative paths (`pathlib.Path`)
- Create output directories safely (`Path(...).mkdir(parents=True, exist_ok=True)`)

## 2. Function Design

- `snake_case` names
- Clear docstrings for non-trivial functions
- No hidden magic numbers (promote to constants/parameters)
- Return structured objects (`dict`, `dataclass`, `DataFrame`) with clear field names

## 3. Domain Correctness

- Ensure implementations match formulas/specifications in slides or manuscript
- Validate estimator assumptions and inference choices
- Document known package-specific pitfalls

## 4. Figure Quality

- Consistent project color palette and theme
- Explicit figure size and resolution
- Legible labels and legends in projected/printed output

## 5. Data Artifact Pattern

- Save heavy intermediate outputs as Parquet/Pickle for reuse in Quarto/docs
- Use descriptive filenames and stable folder conventions

## 6. Code Quality Checklist

```
[ ] Deterministic seed policy applied where needed
[ ] Relative paths only
[ ] Functions documented
[ ] Figures use project theme
[ ] Artifacts persisted (parquet/pickle) when needed
[ ] Comments explain WHY, not just WHAT
```
