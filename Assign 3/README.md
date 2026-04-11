# Assign 3 — COMPAS Fairness Analysis
## Project Overview
This project examines fairness issues in the COMPAS recidivism risk dataset. The goal is to evaluate whether the model’s predictions and risk scores show disparities across demographic groups, especially by race and sex.

The analysis focuses on several fairness-related perspectives:
- selection disparity using AIR and Marginal Effect (ME)
- score disparity using Standardized Mean Difference (SMD)
- intersectional subgroup analysis (race × sex)
- error-rate disparity using FPR and FNR
- statistical significance using a two-proportion z-test
- visualization of FPR and FNR by race

The notebook begins by loading the ProPublica COMPAS dataset from an online CSV source and confirms that the raw dataset contains 7,214 rows and 53 columns. It also previews the first 10 rows before moving into preprocessing and feature engineering.  [oai_citation:1‡GitHub](https://raw.githubusercontent.com/lionling427/Responsible-ML-individual-assign1/main/Assign%203/assign1.ipynb)

## Dataset
Source dataset:
- ProPublica COMPAS two-year recidivism dataset

Main variables used in the analysis include:
- `race`
- `sex`
- `decile_score`
- `high_risk`
- `two_year_recid`

## Project Structure
```text
Assign 3/
├── assign1.ipynb
└── README.md

## Key Findings

The analysis suggests that fairness disparities are visible from multiple angles rather than from a single metric alone.
	•	Some racial groups show lower or higher selection rates relative to the Caucasian reference group.
	•	Error rates are unevenly distributed across groups, meaning the model makes different kinds of mistakes for different populations.
	•	Score distributions also differ across groups, although score differences alone do not automatically prove unfairness.
	•	Intersectional analysis shows that subgroup-level disparities can be stronger than race-only or sex-only analysis.

Overall, the notebook shows why fairness should be evaluated using outcome-based, error-based, and score-based metrics together instead of relying on only one measure.
