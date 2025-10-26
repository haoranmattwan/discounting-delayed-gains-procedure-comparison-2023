# Psychometric Validation of Behavioral Measurement Tools
### A Reproducible Analysis of Wan et al. (2023), *Behavioural Processes*

This repository contains the complete analysis scripts and materials for the peer-reviewed publication:

> Wan, H., Myerson, J., & Green, L. (2023). Individual differences in degree of discounting: Do different procedures and measures assess the same construct?. *Behavioural Processes*, *208*, 104864. https://doi.org/10.1016/j.beproc.2023.104864

**Note on Data:** The data for this study can be requested from me or from my coauthors, Leonard Green and Joel Myerson. 

---

## Project Objective

The goal of this project is to conduct a comprehensive psychometric comparison of the two most prominent procedures for measuring delay discounting: the **Adjusting-Amount (Adj-Amt)** procedure and the **Monetary Choice Questionnaire (MCQ)**. The primary objective is to determine whether both procedures reliably measure the same underlying psychological construct by assessing their reliability and convergent validity.

This analysis demonstrates a complete workflow, from processing raw experimental data into theoretical and atheoretical measures to applying a range of statistical models to evaluate the psychometric properties of the measurement tools.

## Repository Contents

| File / Folder | Description |
| :--- | :--- |
| **`/Analysis/`** | Contains the primary scripts that replicate all findings in the paper. |
| `analysis.qmd` | A Quarto document with the complete **R** workflow, using `glmmTMB` and `minpack.lm`. |
| `analysis.ipynb` | A Jupyter Notebook providing a **Python** translation of the analysis, using `statsmodels` and `lmfit`. |
| **`/Presentation/`** | A slide deck used to present the research findings at an academic conference. |
| **`/Figure/`** | All figures as they appear in the final publication. |

---

## Methodological Approach

This project showcases a comprehensive approach to psychometric validation, highlighting the following skills:

* **Complex Data Processing**: Implemented custom functions to score raw experimental data, including calculating Area under the Curve (atheoretical) and using a consistency-checking algorithm to estimate indifference points (`log k`) from choice data (theoretical).
* **Nonlinear Modeling**: Fit theoretical functions (hyperboloid and logistic growth) to aggregated group-level data to perform initial data validation checks.
* **Generalized Linear Mixed-Effects Models**: Used beta and binomial GLMMs to test for benchmark experimental effects while correctly modeling the non-normal, bounded nature of the outcome variables.
* **Psychometric Analysis**: Conducted a full suite of correlation analyses to establish **alternate-forms reliability** (within-procedure) and **convergent validity** (between-procedure), supplemented with a mixed-effects ANOVA to compare absolute differences in the measures.

---

## How to Reproduce This Analysis

To run these analyses, you will need the raw data file and the appropriate software environment as described below.

### R Environment (`/Analysis/analysis.qmd`)

* **Required Packages**: `readr`, `dplyr`, `tidyr`, `minpack.lm`, `glmmTMB`, `emmeans`, `psych`.
* **Installation**:
    ```R
    install.packages(c("readr", "dplyr", "tidyr", "minpack.lm", "glmmTMB", "emmeans", "psych"))
    ```

### Python Environment (`/Analysis/analysis.ipynb`)

* **Required Packages**: `pandas`, `numpy`, `scipy`, `lmfit`, `statsmodels`, `openpyxl`.
* **Installation**:
    ```bash
    pip install pandas numpy scipy lmfit statsmodels openpyxl
    ```