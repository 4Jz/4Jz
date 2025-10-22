# Handoff Document for G2pp_doc Repository

**Date:** 2025-10-22
**Current Branch:** `claude/create-formula-project-011CULwcmN2sAWYHL93H9GBu`
**Target Repository:** https://github.com/4Jz/G2pp_doc.git

## Project Overview

A Quarto-based documentation project for mathematical formulas, specifically for the G2++ interest rate model. The project uses:
- **Quarto** with **Jupyter engine** (Python)
- **SymPy** for symbolic mathematics
- **HTML-only output** (no PDF)

## Current Status

✅ **Completed:**
1. Created complete Quarto project structure
2. Implemented G2++ interest rate model documentation with:
   - Core SDE equations
   - Zero-coupon bond pricing formulas
   - SymPy symbolic verification
   - Variance calculations
   - Limit behavior analysis
   - Numerical examples
3. All files committed to `claude/create-formula-project-011CULwcmN2sAWYHL93H9GBu` branch in 4Jz/4Jz repo
4. User manually copied files to G2pp_doc repository via Codespaces

## File Structure

```
.
├── .gitignore              # Python, Jupyter, Quarto ignores
├── _quarto.yml             # Quarto configuration (HTML output, navbar)
├── styles.css              # Custom CSS for formula boxes
├── requirements.txt        # Python dependencies (needs jupyter-cache added)
├── README.md               # Project documentation and setup instructions
├── index.qmd               # Home page
└── g2pp_model.qmd          # G2++ model documentation (MAIN CONTENT)
```

## Key Files Content Summary

### `_quarto.yml`
- Website project type with navigation
- HTML output with cosmo theme
- Code tools enabled
- Freeze and cache enabled for performance

### `g2pp_model.qmd` - Main Content
Contains:
1. **Model Equations:**
   - State variable SDEs: dx(t) and dy(t)
   - Short rate formula: r(t) = x(t) + y(t) + φ(t)
   - Bond price formula with B functions

2. **SymPy Implementation:**
   - B_x(τ) and B_y(τ) functions
   - Variance calculations via integration
   - Limit behavior verification
   - Derivative calculations
   - Numerical examples with parameters: a=0.1, b=0.2, σ=0.01, η=0.015, ρ=0.5

### `requirements.txt` - Current
```
sympy>=1.12
numpy>=1.24.0
matplotlib>=3.7.0
jupyter>=1.0.0
```

**NOTE:** User discovered `jupyter-cache>=0.6.0` is also needed - should be added.

## Known Issues / Pending Items

1. **Missing dependency:** `jupyter-cache` should be added to `requirements.txt`
2. **Repository setup:** Files are in G2pp_doc but new session should connect directly to it

## Instructions for New Session

### 1. Session Setup
- Start new Claude Code for Web session
- Connect to repository: `https://github.com/4Jz/G2pp_doc.git`
- This will give direct push access to G2pp_doc

### 2. First Actions in New Session
```bash
# Check current state
git status
git log --oneline -5

# View project structure
ls -la

# Verify all 7 files exist:
# .gitignore, _quarto.yml, styles.css, requirements.txt,
# README.md, index.qmd, g2pp_model.qmd
```

### 3. Recommended First Task
Add `jupyter-cache` to requirements.txt:
```bash
echo "jupyter-cache>=0.6.0" >> requirements.txt
git add requirements.txt
git commit -m "Add jupyter-cache dependency"
git push
```

### 4. Testing the Project
```bash
# Install dependencies
pip install -r requirements.txt

# Render and preview
quarto preview
```

## User Context

**User has:**
- GitHub web interface and Android app
- GitHub Codespaces running for G2pp_doc
- Successfully set up the initial project files

**User wants:**
- Ability to request changes to .qmd files
- Claude to directly edit and push changes to G2pp_doc
- Pragmatic workflow for iterative documentation updates

**User's technical level:**
- Familiar with git basics
- Using Quarto with Python/SymPy
- Prefers explicit, step-by-step instructions

## Future Work Suggestions

Potential additions to discuss with user:
1. Additional interest rate models (Hull-White, CIR, Vasicek)
2. Bond option pricing formulas
3. Calibration examples
4. Model comparisons
5. Visualization with matplotlib
6. Interactive plots

## Git Branch Strategy

**Current:** All work on `claude/create-formula-project-011CULwcmN2sAWYHL93H9GBu` branch in 4Jz/4Jz

**New Session:** Should work on `main` or create feature branches in G2pp_doc directly

## Important Notes

- Project uses **Jupyter engine**, NOT knitr (user's original request was clarified)
- Only HTML output configured (no PDF as requested)
- User confirmed they want "core model equations" with "example calculations"
- User is satisfied with the current G2++ implementation

---

**Session End Time:** 2025-10-22
**Status:** Ready for handoff to new session with G2pp_doc access
