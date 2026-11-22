# Advanced Structural Theory — Lecture Note

[![Build lecture notes](https://github.com/Gauss963/Advanced-Structural-Theory/actions/workflows/build.yml/badge.svg)](https://github.com/Gauss963/Advanced-Structural-Theory/actions/workflows/build.yml)
[![Latest release](https://img.shields.io/github/v/release/Gauss963/Advanced-Structural-Theory)](https://github.com/Gauss963/Advanced-Structural-Theory/releases/latest)

These are the LaTeX lecture notes for **Advanced Structural Theory** at National Taiwan University. The notes cover matrix structural analysis of framed structures. They start with the basic equations, build up the direct stiffness method and the FRAME21 program, and end with energy principles and the flexibility method.

- **Author:** Chun-Yu Ke
- **Typeset in LaTeX by:** Gauss Chang

## Download

📄 **[Download the latest PDF (main.pdf)](https://github.com/Gauss963/Advanced-Structural-Theory/releases/latest/download/main.pdf)**

- [All releases](https://github.com/Gauss963/Advanced-Structural-Theory/releases): each version tag has a PDF attached.
- [`main.pdf`](main.pdf) in this repository: CI rebuilds it on every push to `main`, so it may include changes that are newer than the latest release.

## Contents

| Ch. | Title |
| --: | :---- |
| 1 | Introduction |
| 2 | Definitions and Concepts |
| 3 | Basic Equations: Equilibrium, Compatibility, and Constitutive Equations |
| 4 | Axial Element |
| 5 | Direct Stiffness Method |
| 6 | Programming for FRAME21 |
| 7 | 3D Beam-Column Element: Strength of Materials Approach |
| 8 | Coordinate Transformation, Contragredient Principle, and Congruent Transformation |
| 9 | Solution of Linear Algebraic Equations |
| 10 | Equivalent Nodal Loads; Self-straining Problems |
| 11 | Principle of Virtual Displacements |
| 12 | Principle of Virtual Displacements in Framework Analysis |
| 13 | Special Analysis Procedures |
| 14 | Element Flexibility Matrix |
| 15 | Principle of Virtual Forces |
| 16 | Flexibility Method |

## Repository layout

```
.
├── main.tex                # Preamble, title page, and chapter includes
├── chapter1.tex … chapter16.tex
├── figures/                # TikZ / PGFPlots source for every figure (one .tex per figure)
├── logo.pdf                # Title-page logo
├── main.pdf                # Compiled notes (updated automatically by CI)
└── .github/workflows/build.yml
```

All figures are drawn in TikZ, so the whole document builds from source with no external image files except the logo.

## Building locally

The notes compile with [Tectonic](https://tectonic-typesetting.github.io/), which downloads the LaTeX packages it needs on first use:

```bash
tectonic main.tex
```

A standard TeX Live distribution works too (run `pdflatex main.tex` twice so that the table of contents and cross-references resolve).

## Continuous integration and releases

The [`Build lecture notes`](.github/workflows/build.yml) workflow uses Tectonic 0.17.0 to build the PDF:

- **Push to `main`:** builds the PDF, uploads it as a workflow artifact, and commits the updated `main.pdf` back to `main`.
- **Push a version tag (`vX.Y.Z`):** builds the PDF and publishes a GitHub Release with `main.pdf` attached.

To publish a new version:

```bash
git tag -a v1.0.1 -m "v1.0.1"
git push origin v1.0.1
```
