# Psychometric Validation of Behavioral Measurement Tools
### A Reproducible Analysis of Wan et al. (2023), *Behavioural Processes*

This repository contains the complete analysis scripts and materials for the peer-reviewed publication:

> Wan, H., Myerson, J., & Green, L. (2023). Individual differences in degree of discounting: Do different procedures and measures assess the same construct?. *Behavioural Processes*, *208*, 104864. https://doi.org/10.1016/j.beproc.2023.104864

**Note on Data:** The data for this study can be requested from me or from my coauthors, Drs. Leonard Green and Joel Myerson. 

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
| **`/Presentation/`** | Contain slides and a poster that were presented at meetings and SQAB. |
| **`/Figure/`** | All figures as they appear in the final publication. |

---

## Methodological Approach

The analysis employs a multi-step psychometric validation workflow to compare the two measurement procedures:

* **Data Processing**: Custom functions were implemented to score raw experimental data from both procedures. This included calculating an atheoretical measure (Area under the Curve or choice proportion) and a theoretical measure (`log k`), which was estimated using a consistency-checking algorithm for the choice-based data.
* **Data Validation**: As an initial quality check, theoretical functions (hyperboloid and logistic growth) were fit to aggregated group-level data to confirm that the behavioral data followed established patterns.
* **Mixed-Effects Modeling**: Beta and binomial generalized linear mixed-effects models (GLMMs) were used to test for benchmark experimental effects (e.g., the "amount effect") while correctly accounting for the non-normal, bounded nature of the outcome variables and the repeated-measures data structure.
* **Reliability and Validity Analysis**: A comprehensive suite of correlation analyses was conducted to establish **alternate-forms reliability** (within-procedure) and **convergent validity** (between-procedure). Finally, a mixed-effects ANOVA was used to compare the absolute differences in the measures produced by each procedure.

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