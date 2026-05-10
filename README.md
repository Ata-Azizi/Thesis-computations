# Semi-Classical and Stochastic Methods: A Numerical Comparison

> **Thesis repository** — Numerical implementation and comparison of semi-classical (Coleman instanton) and stochastic approaches to quantum/statistical mechanics problems.

---

## Overview

This repository contains the numerical code and supporting material for a thesis that compares two distinct theoretical frameworks for studying quantum tunneling and related phenomena:

- **Semi-Classical (Coleman) Approach** — based on instanton calculus and saddle-point approximations as developed by Sidney Coleman, used to compute tunneling amplitudes and vacuum decay rates analytically and semi-analytically.
- **Stochastic Approach** — Monte Carlo or Langevin-type numerical simulations that capture the same physical phenomena through statistical sampling of path integrals or stochastic differential equations.

The central goal is to benchmark these two approaches against each other, studying where they agree and where they diverge, and to understand the regimes in which each is most effective.

---

## Repository Structure

```
semi-classical-and-stochastic-comparison-thesis/
│
├── COLEMAN/                  # Scripts and data for the semi-classical (instanton) calculations
├── STOCHASTIC/               # Scripts and data for the stochastic / Monte Carlo simulations
└── Numerical Codes.ipynb     # Main Jupyter notebook containing all numerical implementations,
                              #   plots, and comparative analysis
```

### `COLEMAN/`
Contains the semi-classical calculation pipeline. This includes instanton solutions to the Euclidean equations of motion, computation of one-loop fluctuation determinants, and evaluation of tunneling rates via the dilute instanton gas approximation.

### `STOCHASTIC/`
Contains the stochastic simulation pipeline. This typically includes Markov Chain Monte Carlo (MCMC) or Langevin dynamics simulations of the discretised path integral, convergence diagnostics, and autocorrelation analysis.

### `Numerical Codes.ipynb`
The primary notebook. It imports and exercises both pipelines side-by-side, produces comparative plots, and documents the results that appear in the thesis. Start here for a full walkthrough of the analysis.

---

## Background

### Coleman / Semi-Classical Method
In the semi-classical approximation, the Euclidean path integral is evaluated by expanding around classical solutions (instantons) that connect two minima of the potential. The leading contribution gives an exponential suppression $\sim e^{-S_E/\hbar}$, with the prefactor determined by the functional determinant of fluctuations around the instanton background.

### Stochastic Method
The path integral is discretised on a Euclidean time lattice and sampled numerically using Monte Carlo techniques. Physical observables (such as the ground-state energy splitting or correlation functions) are extracted from ensemble averages over many configurations.

### Why Compare Them?
The semi-classical method is highly efficient but relies on the weak-coupling / dilute-instanton approximation. The stochastic method is non-perturbative but computationally expensive. Comparing them across coupling regimes reveals the limitations of each and validates both methods in their regimes of validity.

---

## Getting Started

### Prerequisites

- Python 3.8+
- Jupyter Notebook or JupyterLab
- Standard scientific Python stack:

```bash
pip install numpy scipy matplotlib jupyter
```

Additional dependencies (if used inside the notebook):

```bash
pip install tqdm sympy
```

### Running the Notebook

```bash
git clone https://github.com/Ata-Azizi/semi-classical-and-stochastic-comparison-thesis.git
cd semi-classical-and-stochastic-comparison-thesis
jupyter notebook "Numerical Codes.ipynb"
```

---

## Results Summary

The notebook produces side-by-side comparisons of:

- **Tunneling amplitudes / energy splittings** computed via instantons vs. stochastic simulations
- **Convergence behaviour** of the stochastic estimators as a function of lattice spacing and ensemble size
- **Parameter scans** across coupling constants, showing the breakdown of the dilute-instanton approximation at strong coupling

Figures and tables from this notebook appear directly in the thesis.

---

## Citation

If you use or build upon this code, please cite the associated thesis:

```
Ata Azizi,
"A Numerical Comparison of Semi-Classical and Stochastic Methods [for Quantum Tunneling]",
Thesis, [Institution], [Year].
GitHub: https://github.com/Ata-Azizi/semi-classical-and-stochastic-comparison-thesis
```

*(Please update the institution and year fields as appropriate.)*

---

## License

This repository does not currently include an explicit license. All rights are reserved by the author unless otherwise stated. Please contact the author before reusing or redistributing any part of this work.

---

## Author

**Ata Azizi**
GitHub: [@Ata-Azizi](https://github.com/Ata-Azizi)
