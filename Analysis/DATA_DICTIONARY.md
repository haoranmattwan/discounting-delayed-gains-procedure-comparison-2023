# Data dictionary

## Data access

Participant-level data are not included in this repository. The analysis-ready file is available from the study authors on request, subject to the original consent, institutional review requirements, and applicable data-use terms.

After receiving authorized access, save the file as `Analysis/AdjAmt_MCQ.csv`. The R and Python workflows expect that path and filename.

## Expected dataset

`AdjAmt_MCQ.csv` contains 15,720 rows from 393 participants: 150 recruited through Prolific and 243 through Amazon Mechanical Turk. Each participant contributes 40 task-level observations across the Adjusting-Amount (`aa`) and Monetary Choice Questionnaire (`mcq`) procedures.

The analysis-ready file contains no names, email addresses, worker IDs, or other direct identifiers. It does contain age and coded demographic characteristics and must be handled as participant-level research data.

## Variables

| Variable | Description | Coding or units |
| --- | --- | --- |
| unnamed first column | Legacy row index | Integer; remove after import |
| `provider` | Recruitment platform | `Prolific` or `MTurk` |
| `id` | Study-specific participant identifier | Integer; unique across this combined file |
| `procedure` | Discounting procedure | `aa` = Adjusting-Amount; `mcq` = Monetary Choice Questionnaire |
| `amt` | Procedure-specific delayed-reward category | See amount table below |
| `age` | Participant age | Years |
| `sex` | Gender coding used in the archived dataset | `0` = male; `1` = female; `NA` = missing |
| `edu` | Education | `0` = below college; `1` = college or above; `NA` = missing |
| `eth` | Ethnicity | `0` = Hispanic or Latino; `1` = not Hispanic or Latino; `NA` = missing |
| `race` | Race | `0` = not White; `1` = White; `NA` = missing |
| `value` | Observed response | Adj-Amt: relative subjective value; MCQ: `0` = smaller-immediate choice, `1` = larger-delayed choice |
| `iv` | Procedure-specific independent variable | Adj-Amt: delay in days; MCQ: question-level *k* value |

## Amount coding

The meaning of `amt` depends on `procedure`.

| `amt` | Adjusting-Amount (`aa`) | MCQ (`mcq`) |
| --- | --- | --- |
| `1` | $30 | $25–$35 |
| `2` | $80 | $50–$60 |
| `3` | $500 | $75–$85 |

The cross-procedure comparisons use the common amount labels defined in the analysis code: Adj-Amt `amt = 1` with MCQ `amt = 1` (labeled $30), and Adj-Amt `amt = 2` with MCQ `amt = 3` (labeled $80).

## Missing values

Missing demographic values are represented by the string `NA`. Task variables required by the supplied analyses are complete. The R workflow imports `NA` as missing by default; the Python workflow imports it as `NaN`.

## Terms of use

The repository's MIT License applies to code and documentation, not to participant-level data. Access or reuse terms must be confirmed with the study authors. Authorized users remain responsible for complying with the original consent language, institutional review requirements, and applicable data-use terms. Derived public outputs should avoid combinations of demographic fields that could increase re-identification risk.

When reporting results, cite the associated article:

> Wan, H., Myerson, J., & Green, L. (2023). Individual differences in degree of discounting: Do different procedures and measures assess the same construct? *Behavioural Processes, 208*, 104864. https://doi.org/10.1016/j.beproc.2023.104864
