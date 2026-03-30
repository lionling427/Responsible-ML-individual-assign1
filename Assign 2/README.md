# Responsible ML – COMPAS Analysis

This project analyzes a recidivism prediction model using multiple explainability techniques and evaluates its fairness and governance implications.

##  Methods Used

- Logistic Regression (interpretable baseline)
- Gradient Boosted Trees (black-box model)

## Explainability Techniques

- SHAP (global + local explanations)
- LIME (local explanations)
- Counterfactual explanations (DiCE)

## Key Findings

- The model is primarily driven by:
    - `priors_count`
    - `age`
- Race-related features appear in explanations → potential bias risk
- Counterfactuals sometimes require changing **immutable features (race, sex)** → unrealistic

## Governance Implications

- Model may rely on sensitive attributes or proxies
- Explainability alone does NOT guarantee fairness
- Required measures:
    - Proxy audits
    - Fairness monitoring
    - Feature constraints for immutable attributes
    - Human oversight

## Project Structure

```
Assign 2/
├── assign2.ipynb          # Main analysis (SHAP, LIME, counterfactuals)
├── README.md              # Summary of methods, findings, and governance implications
└── RML group assign 2.pdf # Assignment instructions
```