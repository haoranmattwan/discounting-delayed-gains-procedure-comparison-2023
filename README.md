# Do delay-discounting procedures measure the same construct?

[![DOI](https://img.shields.io/badge/DOI-10.1016%2Fj.beproc.2023.104864-1f6f78)](https://doi.org/10.1016/j.beproc.2023.104864)
[![License: MIT](https://img.shields.io/badge/Code-MIT-5b6573.svg)](LICENSE)

Open analysis companion to:

> Wan, H., Myerson, J., & Green, L. (2023). Individual differences in degree of discounting: Do different procedures and measures assess the same construct? *Behavioural Processes, 208*, 104864. https://doi.org/10.1016/j.beproc.2023.104864

## Overview

Delay discounting is measured with several procedures, but results can only be compared confidently if those procedures capture the same individual-difference construct. This study compares two widely used approaches:

- the **Adjusting-Amount procedure (Adj-Amt)**, which estimates subjective values across delays; and
- the **Monetary Choice Questionnaire (MCQ)**, which infers discounting from choices between immediate and delayed rewards.

The analyses use data from **393 adults** recruited through Prolific (*n* = 150) and Amazon Mechanical Turk (*n* = 243). They evaluate established amount effects, stability across reward magnitudes, convergence between theoretical and atheoretical scoring methods, and convergence between procedures.

## Main result

The two procedures show strong convergent validity: the published between-procedure correlations range from **.74 to .82** across samples, reward amounts, and scoring approaches. At the same time, systematic differences in estimated discounting indicate that Adj-Amt and MCQ scores should not be assumed to be numerically interchangeable.

This distinction matters for cumulative research: the procedures appear to capture a common individual-difference construct, while still retaining method-specific properties.

### Interpretive scope

The evidence is specific to delayed monetary gains, the reward amounts studied, and two online convenience samples. Convergent correlations establish shared variance; they do not by themselves establish score equivalence, causal validity, or generalization to losses, nonmonetary outcomes, or other populations.

## Reproduce the analyses

Participant-level data are not included in this repository. To reproduce the analyses, request the analysis-ready data from the study authors and save the authorized file as `Analysis/AdjAmt_MCQ.csv`. Then run either the R or Python workflow from the `Analysis` directory.

### R

The R environment is recorded in [`renv.lock`](renv.lock).

```r
install.packages("renv")
renv::restore()
```

```bash
cd Analysis
quarto render analysis_R.qmd
```

### Python

The Python environment is recorded in [`requirements.txt`](requirements.txt).

```bash
python -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
cd Analysis
quarto render analysis_Py.ipynb --execute
```

Pre-rendered reports are provided for readers who do not need to rerun the code:

- [R analysis](Analysis/analysis_R.html)
- [Python analysis](Analysis/analysis_Py.html)

The streamlined workflows use nonlinear least squares for Adj-Amt estimates and a consistency-scoring algorithm for MCQ estimates. The publication used Stan for the corresponding point estimates, so small numerical differences are expected. These files are transparent companion implementations, not byte-for-byte reconstructions of the original computational environment.

## Repository guide

| Path | Contents |
| --- | --- |
| [`Analysis/analysis_R.qmd`](Analysis/analysis_R.qmd) | Primary, annotated R workflow |
| [`Analysis/analysis_Py.ipynb`](Analysis/analysis_Py.ipynb) | Parallel Python implementation |
| [`Analysis/DATA_DICTIONARY.md`](Analysis/DATA_DICTIONARY.md) | Expected data structure, variables, and coding |
| [`Figure/`](Figure/) | Figures reported in the publication |
| [`Presentation/`](Presentation/) | Selected scholarly presentations and poster |
| [`renv.lock`](renv.lock) | R package versions |
| [`requirements.txt`](requirements.txt) | Python package versions |

## Open-science status

This repository makes the analysis logic, computational environments, rendered aggregate outputs, figures, and citation metadata inspectable. The R and Python implementations provide two routes through the same research questions, which helps expose software-specific assumptions.

Participant-level data are **not uploaded to or distributed through this repository**. The analysis-ready file is available from the study authors on request, subject to the original consent, institutional review requirements, and any applicable data-use terms. The [data dictionary](Analysis/DATA_DICTIONARY.md) documents the expected structure for authorized recipients.

Open science requires explicit boundaries as well as accessible materials. The repository therefore distinguishes public research outputs from local manuscript drafts, peer-review correspondence, and administrative records.

## Citation

If this repository contributes to a publication, cite the peer-reviewed article above. GitHub and compatible reference managers can also read [`CITATION.cff`](CITATION.cff).

## Contributing

Corrections and reproducibility reports are welcome. Please read [`CONTRIBUTING.md`](CONTRIBUTING.md) before opening an issue or proposing a change.

## License

Analysis code and repository documentation are available under the [MIT License](LICENSE). Participant-level data are not distributed under this license. The published article, figures, and presentation materials may be subject to separate copyright conditions.
