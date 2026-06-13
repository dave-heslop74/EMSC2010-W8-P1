# EMSC2010 – Week 8 Practical 1: Bayesian Regression

This repository contains the template Jupyter notebooks for **Week 8 Practical 1** of *EMSC2010: Data Science for Earth System Scientists* at the Australian National University.

The session introduces **Bayesian polynomial regression** using the `bambi` package, covering model fitting, prediction, and model selection, before applying these tools to a real-world prediction problem.

---

## Notebooks

### Notebook 1 – Straight-Line Regression with Bambi (`NB1`)

**Dataset:** Downstream river grain size measurements (the same dataset used in Week 8 Lectorial 1).

This notebook introduces `bambi` as a high-level interface for Bayesian regression in `PyMC`. Students fit a first-order (straight-line) polynomial model to the grain size data, inspect the automatically generated priors, and use `arviz` to examine the sampled posterior distributions of the intercept and gradient. The notebook then demonstrates how to use the fitted model to make predictions, distinguishing between:

- the **95% HDI (mean)** band — the probability envelope for the *mean* grain size at a given distance, and
- the **95% HDI (predictive)** band — the probability envelope for a *new individual observation* of grain size at a given distance.

**Key concepts:** Bayesian linear regression, `bambi` model syntax, posterior distributions, credible intervals vs. predictive intervals

**Libraries:** `numpy`, `matplotlib`, `pandas`, `bambi`, `arviz`

---

### Notebook 2 – Model Selection with Higher-Order Polynomials (`NB2`)

**Dataset:** Copper concentration with distance along a mine adit.

This notebook extends the regression approach to higher-order polynomials. Since the copper concentration data does not follow a simple straight line, students fit linear, quadratic, cubic, and quartic models using `bambi`, after first **scaling** the predictor variable (mean 0, standard deviation 1) to avoid numerical issues with large powers of $x$. The four models are then compared using `arviz`'s model selection criteria to identify the most parsimonious model — one that neither underfits nor overfits the data. The selected (quadratic) model is then used to generate mean and predictive HDI bands, as in NB1.

**Key concepts:** Polynomial regression, predictor scaling, model comparison/selection criteria, parsimony, avoiding overfitting

**Libraries:** `numpy`, `matplotlib`, `pandas`, `bambi`, `arviz`

---

### Notebook 3 – Challenge: Olympic 100 m Sprint Times (`NB3`)

**Dataset:** Historical winning times for the Olympic men's and women's 100 m finals.

This is an open-ended challenge notebook addressing the question: *in what year might the women's Olympic 100 m champion run faster than the men's?* Students are provided with the historical data and an initial visualisation, and are asked to fit straight-line models to both datasets and use them to make a probabilistic prediction about future performance — extending the regression and prediction skills developed in NB1 and NB2 to a two-sample comparison problem.

A **solution notebook** (`EMSC2010_W8_P1_NB3_SOLUTION.ipynb`) is provided.

**Key concepts:** Independent application of Bayesian regression, posterior predictive sampling, probabilistic comparison of two groups, extrapolation and its limitations

**Libraries:** `numpy`, `matplotlib`, `pandas`, `bambi`, `arviz`

---

## Getting Started

This is a **template repository**. To begin working on the notebooks:

1. Click **"Use this template"** at the top of this page to create a copy of the repository in your own GitHub account.
2. Open any notebook from your copy of the repository and click the **"Open in Colab"** badge at the top of the notebook to launch it in Google Colab.
3. Before submitting, replace the `uXXXXXXX` placeholder in the filename with your ANU student UID.

> **Note:** `bambi` is not pre-installed in Google Colab. Each notebook that uses it begins with `!pip install bambi` to install it into the Colab environment.

---

## Repository Structure

```
EMSC2010-W8-P1/
├── EMSC2010_W8_P1_NB1_uXXXXXXX.ipynb    # Straight-line regression with bambi
├── EMSC2010_W8_P1_NB2_uXXXXXXX.ipynb    # Model selection with higher-order polynomials
├── EMSC2010_W8_P1_NB3_uXXXXXXX.ipynb    # Challenge: Olympic 100 m sprint times
├── EMSC2010_W8_P1_NB3_SOLUTION.ipynb    # NB3 solution for reference
├── LICENSE
└── README.md
```

---

## Course Information

| | |
|---|---|
| **Course** | EMSC2010 – Data Science for Earth System Scientists |
| **Institution** | Australian National University (ANU) |
| **Week** | 8 |
| **Session** | Practical 1 |
| **Topic** | Bayesian Regression |

---

## License

This repository is released under the [MIT License](LICENSE).
