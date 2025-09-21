# Individual Differences in Degree of Discounting: A Comparison of Two Procedures

This repository contains the analysis scripts and presentation materials for the peer-reviewed publication:

> Wan, H., Myerson, J., & Green, L. (2023). Individual differences in degree of discounting: Do different procedures and measures assess the same construct?. *Behavioural Processes*, *208*, 104864. https://doi.org/10.1016/j.beproc.2023.104864

---

## Project Overview

This study provides a comprehensive comparison of the two most prominent procedures for measuring delay discounting: the Adjusting-Amount (Adj-Amt) procedure and the Monetary Choice Questionnaire (MCQ). The primary goal was to determine whether both procedures reliably measure the same underlying psychological construct.

The analysis involves a multi-step workflow, starting with complex data processing to derive theoretical (e.g., `log k`) and atheoretical (e.g., Area under the Curve) measures of discounting for each participant. Subsequently, a diverse range of statistical methods, including nonlinear regression, generalized linear mixed models (beta and binomial), correlation analyses, and ANOVA, were employed to test the reliability and validity of the procedures.

The data can be requested from me or from my coauthors, Cyrus Kirkman and Tim Hackenberg.

## Repository Structure

The project materials are organized into the following folders:

* **/Analysis**: Contains the primary analysis scripts that replicate the findings in the paper.
    * `analysis.qmd`: A Quarto document with the complete **R** code for the entire workflow. It demonstrates data processing, model fitting (`minpack.lm`, `glmmTMB`), and statistical testing.
    * `analysis.ipynb`: A Jupyter Notebook providing a direct **Python** translation of the R analysis, using `pandas` for data manipulation and `lmfit` and `statsmodels` for statistical modeling and inference.

* **/Presentation**: Contains a slide deck or poster used to present the findings of this research at an academic conference.

* **`/Figure`**: Contains the figures as they appear in the final publication.

---

## Methodology Snapshot

This project showcases a versatile approach to data analysis, including:

* **Complex Data Processing**: Custom R and Python functions to score participant-level data from raw experimental outputs, including calculating Area under the Curve and scoring the MCQ to estimate indifference points.
* **Nonlinear Modeling**: Fitting hyperboloid and logistic growth functions to group-level data.
* **Generalized Linear Models**: Using beta and binomial GLMs to test for the "amount effect" while accounting for the non-normal distribution of the dependent variables.
* **Inferential Statistics**: Comprehensive correlation analyses to establish within-procedure reliability and between-procedure validity, supplemented with ANOVA to compare absolute differences in discounting rates.

---

## Software and Execution

To run the analyses, you will need the appropriate software environment and the raw data file.

### R Environment (`/Analysis/analysis.qmd`)

* **Required Packages**: `readr`, `dplyr`, `tidyr`, `minpack.lm`, `glmmTMB`, `multcomp`, `emmeans`, `psych`.
* **Installation**:
    ```R
    install.packages(c("readr", "dplyr", "tidyr", "minpack.lm", "glmmTMB", "multcomp", "emmeans", "psych"))
    ```

### Python Environment (`/Analysis/analysis.ipynb`)

* **Required Packages**: `pandas`, `numpy`, `scipy`, `lmfit`, `statsmodels`.
* **Installation**:
    ```bash
    pip install pandas numpy scipy lmfit statsmodels
    ```