# Semi-Classical and Stochastic Methods: A Numerical Comparison

> **Thesis repository** — Numerical implementation and comparison of semi-classical (Coleman instanton) and stochastic approaches to vacuum decay.

---

## Overview

This repository contains the numerical code and supporting material for a thesis that compares two distinct theoretical frameworks for studying quantum tunneling and vacuum decay:

- **Semi-Classical (Coleman) Approach** — based on instanton calculus and saddle-point approximations as developed by Sidney Coleman, used to compute tunneling amplitudes and vacuum decay rates analytically and semi-analytically.
- **Stochastic Approach** — Numerical solution of a Schrödinger-like eigenvalue equation to extract the first non-zero eigenvalue and its corresponding eigenfunction, providing a direct spectral characterization of the system that can be compared against the semi-classical predictions.

The central goal is to benchmark these two approaches against each other, studying where they agree and where they diverge, and to understand the regimes in which each is most effective.

---

## Repository Structure

```
semi-classical-and-stochastic-comparison-thesis/
│
├── COLEMAN/                  # Scripts and data for the semi-classical (Coleman instanton) calculations
├── STOCHASTIC/               # Scripts and data for the stochastic simulations and results
    
```

git clone https://github.com/your-username/coleman-instanton-solvers.git
    cd coleman-instanton-solvers
    ```
2.  Install dependencies:
    ```bash
    pip install numpy scipy matplotlib
    ```
This repository contains a suite of Python tools for calculating **vacuum decay** and **instanton solutions** using both custom shooting methods and the `CosmoTransitions` package. It focuses on the **dimensionless Coleman potential**, providing solutions for both single-field and two-field (coupled) systems.

---

## 🌌 Project Overview: Coleman Potential Solver

In quantum field theory and cosmology, vacuum decay is described by the "bounce" solution. This project calculates the field profile $\hat{\phi}(\hat{r})$ and the Euclidean action $S_4$ for potentials of the form:

$$v(\hat{\phi}) = (\hat{\phi}^2 - 1)^2 + \kappa(\hat{\phi} - 1)$$

The code handles the transformation from dimensionful parameters $(\lambda, a, \epsilon)$ to the dimensionless $\kappa$ and solves the resulting Euler-Lagrange equations.

---

## 🛠 Features & Scripts

The repository is organized into three primary solvers:

### 1. `A1_Overshoot_Undershoot.py` (Custom Shooting)
*   **Method:** Implements a manual "Overshoot/Undershoot" shooting algorithm.
*   **Highlights:** 
    *   Finds stationary points and barrier tops.
    *   Solves the ODE $\hat{\phi}'' + \frac{3}{\hat{r}}\hat{\phi}' = \frac{dv}{d\hat{\phi}}$ using `scipy.integrate.solve_ivp`.
    *   Calculates the dimensionless action $S_4$ via integration.

### 2. `A2_SingleField_Instanton.py` (1D CosmoTransitions)
*   **Method:** Utilizes the `SingleFieldInstanton` class from the `CosmoTransitions` library.
*   **Highlights:** 
    *   Uses a robust analytic cubic solver to find vacua.
    *   High-precision bounce profile generation.
    *   Comparison of potential depth ($v_{TV}$ vs $v_{FV}$).

### 3. `B1_2D_PathDeformation.py` (2D CosmoTransitions)
*   **Method:** Implements a 2D coupled potential using `pathDeformation`.
*   **Potential Model:** 
    $$v(\hat{\phi}_1, \hat{\phi}_2) = v(\hat{\phi}_1) + \rho v(\hat{\phi}_2) + \gamma \hat{\phi}_1^2 \hat{\phi}_2^2$$
*   **Highlights:** 
    *   Automated scan of the 2D surface to find all local minima.
    *   Calculates the **Tunneling Path** between the closest metastable vacuum and the true vacuum.
    *   Plots 2D contour maps of the field trajectory.

---

## 🚀 Getting Started

### Prerequisites
*   Python 3.8+
*   NumPy, SciPy, Matplotlib
*   [CosmoTransitions](https://github.com/cloveras/CosmoTransitions)

### Installation
1.  Clone the repository:
    ```bash
    git clone https://github.com/your-username/coleman-instanton-solvers.git
    cd coleman-instanton-solvers
    ```
2.  Install dependencies:
    ```bash
    pip install numpy scipy matplotlib
    ```
    *Note: Ensure `cosmoTransitions` is in your Python path.*

---

## 📊 Visualizations

The scripts generate two types of plotsThis repository contains a suite of Python tools for calculating **vacuum decay** and **instanton solutions** using both custom shooting methods and the `CosmoTransitions` package. It focuses on the **dimensionless Coleman potential**, providing solutions for both single-field and two-field (coupled) systems.

---

## 🌌 Project Overview: Coleman Potential Solver

In quantum field theory and cosmology, vacuum decay is described by the "bounce" solution. This project calculates the field profile $\hat{\phi}(\hat{r})$ and the Euclidean action $S_4$ for potentials of the form:

$$v(\hat{\phi}) = (\hat{\phi}^2 - 1)^2 + \kappa(\hat{\phi} - 1)$$

The code handles the transformation from dimensionful parameters $(\lambda, a, \epsilon)$ to the dimensionless $\kappa$ and solves the resulting Euler-Lagrange equations.

---

## 🛠 Features & Scripts

The repository is organized into three primary solvers:

### 1. `A1_Overshoot_Undershoot.py` (Custom Shooting)
*   **Method:** Implements a manual "Overshoot/Undershoot" shooting algorithm.
*   **Highlights:** 
    *   Finds stationary points and barrier tops.
    *   Solves the ODE $\hat{\phi}'' + \frac{3}{\hat{r}}\hat{\phi}' = \frac{dv}{d\hat{\phi}}$ using `scipy.integrate.solve_ivp`.
    *   Calculates the dimensionless action $S_4$ via integration.

### 2. `A2_SingleField_Instanton.py` (1D CosmoTransitions)
*   **Method:** Utilizes the `SingleFieldInstanton` class from the `CosmoTransitions` library.
*   **Highlights:** 
    *   Uses a robust analytic cubic solver to find vacua.
    *   High-precision bounce profile generation.
    *   Comparison of potential depth ($v_{TV}$ vs $v_{FV}$).

### 3. `B1_2D_PathDeformation.py` (2D CosmoTransitions)
*   **Method:** Implements a 2D coupled potential using `pathDeformation`.
*   **Potential Model:** 
    $$v(\hat{\phi}_1, \hat{\phi}_2) = v(\hat{\phi}_1) + \rho v(\hat{\phi}_2) + \gamma \hat{\phi}_1^2 \hat{\phi}_2^2$$
*   **Highlights:** 
    *   Automated scan of the 2D surface to find all local minima.
    *   Calculates the **Tunneling Path** between the closest metastable vacuum and the true vacuum.
    *   Plots 2D contour maps of the field trajectory.

---

## 🚀 Getting Started

### Prerequisites
*   Python 3.8+
*   NumPy, SciPy, Matplotlib
*   [CosmoTransitions](https://github.com/cloveras/CosmoTransitions)

### Installation
1.  Clone the repository:
    ```bash
    git clone https://github.com/your-username/coleman-instanton-solvers.git
    cd coleman-instanton-solvers
    ```
2.  Install dependencies:
    ```bash
    pip install numpy scipy matplotlib
    ```
    *Note: Ensure `cosmoTransitions` is in your Python path.*

---

## 📊 Visualizations

The scripts generate two types of plots:
1.  **Field Profiles:** The evolution of $\hat{\phi}$ as a function of the dimensionless radius $\hat{r}$.
2.  **Potential LandscapesThis repository contains a suite of Python tools for calculating **vacuum decay** and **instanton solutions** using both custom shooting methods and the `CosmoTransitions` package. It focuses on the **dimensionless Coleman potential**, providing solutions for both single-field and two-field (coupled) systems.

---

## 🌌 Project Overview: Coleman Potential Solver

In quantum field theory and cosmology, vacuum decay is described by the "bounce" solution. This project calculates the field profile $\hat{\phi}(\hat{r})$ and the Euclidean action $S_4$ for potentials of the form:

$$v(\hat{\phi}) = (\hat{\phi}^2 - 1)^2 + \kappa(\hat{\phi} - 1)$$

The code handles the transformation from dimensionful parameters $(\lambda, a, \epsilon)$ to the dimensionless $\kappa$ and solves the resulting Euler-Lagrange equations.

---

## 🛠 Features & Scripts

The repository is organized into three primary solvers:

### 1. `A1_Overshoot_Undershoot.py` (Custom Shooting)
*   **Method:** Implements a manual "Overshoot/Undershoot" shooting algorithm.
*   **Highlights:** 
    *   Finds stationary points and barrier tops.
    *   Solves the ODE $\hat{\phi}'' + \frac{3}{\hat{r}}\hat{\phi}' = \frac{dv}{d\hat{\phi}}$ using `scipy.integrate.solve_ivp`.
    *   Calculates the dimensionless action $S_4$ via integration.

### 2. `A2_SingleField_Instanton.py` (1D CosmoTransitions)
*   **Method:** Utilizes the `SingleFieldInstanton` class from the `CosmoTransitions` library.
*   **Highlights:** 
    *   Uses a robust analytic cubic solver to find vacua.
    *   High-precision bounce profile generation.
    *   Comparison of potential depth ($v_{TV}$ vs $v_{FV}$).

### 3. `B1_2D_PathDeformation.py` (2D CosmoTransitions)
*   **Method:** Implements a 2D coupled potential using `pathDeformation`.
*   **Potential Model:** 
    $$v(\hat{\phi}_1, \hat{\phi}_2) = v(\hat{\phi}_1) + \rho v(\hat{\phi}_2) + \gamma \hat{\phi}_1^2 \hat{\phi}_2^2$$
*   **Highlights:** 
    *   Automated scan of the 2D surface to find all local minima.
    *   Calculates the **Tunneling Path** between the closest metastable vacuum and the true vacuum.
    *   Plots 2D contour maps of the field trajectory.

---

## 🚀 Getting Started

### Prerequisites
*   Python 3.8+
*   NumPy, SciPy, Matplotlib
*   [CosmoTransitions](https://github.com/cloveras/CosmoTransitions)

### Installation
1.  Clone the repository:
    ```bash
    git clone https://github.com/your-username/coleman-instanton-solvers.git
    cd coleman-instanton-solvers
    ```
2.  Install dependencies:
    ```bash
    pip install numpy scipy matplotlib
    ```
    *Note: Ensure `cosmoTransitions` is in your Python path.*

---

## 📊 Visualizations

The scripts generate two types of plots:
1.  **Field Profiles:** The evolution of $\hat{\phi}$ as a function of the dimensionless radius $\hat{r}$.
2.  **Potential Landscapes:** 
    *   **1D:** Energy levels of the True Vacuum (TV), False Vacuum (FV), and Barrier Top.
    *   **2This repository contains a suite of Python tools for calculating **vacuum decay** and **instanton solutions** using both custom shooting methods and the `CosmoTransitions` package. It focuses on the **dimensionless Coleman potential**, providing solutions for both single-field and two-field (coupled) systems.

---

## 🌌 Project Overview: Coleman Potential Solver

In quantum field theory and cosmology, vacuum decay is described by the "bounce" solution. This project calculates the field profile $\hat{\phi}(\hat{r})$ and the Euclidean action $S_4$ for potentials of the form:

$$v(\hat{\phi}) = (\hat{\phi}^2 - 1)^2 + \kappa(\hat{\phi} - 1)$$

The code handles the transformation from dimensionful parameters $(\lambda, a, \epsilon)$ to the dimensionless $\kappa$ and solves the resulting Euler-Lagrange equations.

---

## 🛠 Features & Scripts

The repository is organized into three primary solvers:

### 1. `A1_Overshoot_Undershoot.py` (Custom Shooting)
*   **Method:** Implements a manual "Overshoot/Undershoot" shooting algorithm.
*   **Highlights:** 
    *   Finds stationary points and barrier tops.
    *   Solves the ODE $\hat{\phi}'' + \frac{3}{\hat{r}}\hat{\phi}' = \frac{dv}{d\hat{\phi}}$ using `scipy.integrate.solve_ivp`.
    *   Calculates the dimensionless action $S_4$ via integration.

### 2. `A2_SingleField_Instanton.py` (1D CosmoTransitions)
*   **Method:** Utilizes the `SingleFieldInstanton` class from the `CosmoTransitions` library.
*   **Highlights:** 
    *   Uses a robust analytic cubic solver to find vacua.
    *   High-precision bounce profile generation.
    *   Comparison of potential depth ($v_{TV}$ vs $v_{FV}$).

### 3. `B1_2D_PathDeformation.py` (2D CosmoTransitions)
*   **Method:** Implements a 2D coupled potential using `pathDeformation`.
*   **Potential Model:** 
    $$v(\hat{\phi}_1, \hat{\phi}_2) = v(\hat{\phi}_1) + \rho v(\hat{\phi}_2) + \gamma \hat{\phi}_1^2 \hat{\phi}_2^2$$
*   **Highlights:** 
    *   Automated scan of the 2D surface to find all local minima.
    *   Calculates the **Tunneling Path** between the closest metastable vacuum and the true vacuum.
    *   Plots 2D contour maps of the field trajectory.

---

## 🚀 Getting Started

### Prerequisites
*   Python 3.8+
*   NumPy, SciPy, Matplotlib
*   [CosmoTransitions](https://github.com/cloveras/CosmoTransitions)

### Installation
1.  Clone the repository:
    ```bash
    git clone https://github.com/your-username/coleman-instanton-solvers.git
    cd coleman-instanton-solvers
    ```
2.  Install dependencies:
    ```bash
    pip install numpy scipy matplotlib
    ```
    *Note: Ensure `cosmoTransitions` is in your Python path.*

---

## 📊 Visualizations

The scripts generate two types of plots:
1.  **Field Profiles:** The evolution of $\hat{\phi}$ as a function of the dimensionless radius $\hat{r}$.
2.  **Potential Landscapes:** 
    *   **1D:** Energy levels of the True Vacuum (TV), False Vacuum (FV), and Barrier Top.
    *   **2D:** Contour plots showing the path the fields take during the transition.

---

## 📝 Usage Example
To run the 2D path deformation solver:This repository contains a suite of Python tools for calculating **vacuum decay** and **instanton solutions** using both custom shooting methods and the `CosmoTransitions` package. It focuses on the **dimensionless Coleman potential**, providing solutions for both single-field and two-field (coupled) systems.

---

## 🌌 Project Overview: Coleman Potential Solver

In quantum field theory and cosmology, vacuum decay is described by the "bounce" solution. This project calculates the field profile $\hat{\phi}(\hat{r})$ and the Euclidean action $S_4$ for potentials of the form:

$$v(\hat{\phi}) = (\hat{\phi}^2 - 1)^2 + \kappa(\hat{\phi} - 1)$$

The code handles the transformation from dimensionful parameters $(\lambda, a, \epsilon)$ to the dimensionless $\kappa$ and solves the resulting Euler-Lagrange equations.

---

## 🛠 Features & Scripts

The repository is organized into three primary solvers:

### 1. `A1_Overshoot_Undershoot.py` (Custom Shooting)
*   **Method:** Implements a manual "Overshoot/Undershoot" shooting algorithm.
*   **Highlights:** 
    *   Finds stationary points and barrier tops.
    *   Solves the ODE $\hat{\phi}'' + \frac{3}{\hat{r}}\hat{\phi}' = \frac{dv}{d\hat{\phi}}$ using `scipy.integrate.solve_ivp`.
    *   Calculates the dimensionless action $S_4$ via integration.

### 2. `A2_SingleField_Instanton.py` (1D CosmoTransitions)
*   **Method:** Utilizes the `SingleFieldInstanton` class from the `CosmoTransitions` library.
*   **Highlights:** 
    *   Uses a robust analytic cubic solver to find vacua.
    *   High-precision bounce profile generation.
    *   Comparison of potential depth ($v_{TV}$ vs $v_{FV}$).

### 3. `B1_2D_PathDeformation.py` (2D CosmoTransitions)
*   **Method:** Implements a 2D coupled potential using `pathDeformation`.
*   **Potential Model:** 
    $$v(\hat{\phi}_1, \hat{\phi}_2) = v(\hat{\phi}_1) + \rho v(\hat{\phi}_2) + \gamma \hat{\phi}_1^2 \hat{\phi}_2^2$$
*   **Highlights:** 
    *   Automated scan of the 2D surface to find all local minima.
    *   Calculates the **Tunneling Path** between the closest metastable vacuum and the true vacuum.
    *   Plots 2D contour maps of the field trajectory.

---

## 🚀 Getting Started

### Prerequisites
*   Python 3.8+
*   NumPy, SciPy, Matplotlib
*   [CosmoTransitions](https://github.com/cloveras/CosmoTransitions)

### Installation
1.  Clone the repository:
    ```bash
    git clone https://github.com/your-username/coleman-instanton-solvers.git
    cd coleman-instanton-solvers
    ```
2.  Install dependencies:
    ```bash
    pip install numpy scipy matplotlib
    ```
    *Note: Ensure `cosmoTransitions` is in your Python path.*

---

## 📊 Visualizations

The scripts generate two types of plots:
1.  **Field Profiles:** The evolution of $\hat{\phi}$ as a function of the dimensionless radius $\hat{r}$.
2.  **Potential Landscapes:** 
    *   **1D:** Energy levels of the True Vacuum (TV), False Vacuum (FV), and Barrier Top.
    *   **2D:** Contour plots showing the path the fields take during the transition.

---

## 📝 Usage Example
To run the 2D path deformation solver:
```bash
python B1_2D_PathDeformation.py

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
