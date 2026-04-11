## Responsible ML – Assignment 4: Robustness, Fairness, and Model Evaluation

### Objectives

The analysis focuses on three main components:

- Distribution Drift: Check whether training and testing data come from the same distribution  
- Generalization: Evaluate model performance on unseen data and detect overfitting  
- Robustness and Fairness: Assess model stability under perturbations and across subgroups  

---

### Dataset

The dataset includes:

- Demographic variables: age, sex, race  
- Criminal history: priors_count, charge degree  
- Target variable: two_year_recid  

Data is filtered to ensure valid observations and consistency with the COMPAS analysis framework.

---

### Models

Two models are implemented:

- Logistic Regression  
- Gradient Boosted Tree  

These models are used to compare interpretability and predictive performance.

---

### Evaluation Methods

#### 1. Distribution Drift

Drift between training and testing data is evaluated using:

- PSI (Population Stability Index)  
- KS test (Kolmogorov–Smirnov test)  
- MMD (Maximum Mean Discrepancy)  

Result: No significant drift is observed, indicating stable data distribution.

---

#### 2. Generalization

Train and test performance are compared using:

- Accuracy  
- AUC  
- Brier Score  
- Log Loss  

Result: Logistic Regression shows minimal performance gap and generalizes well. Gradient Boosted Tree shows a larger gap, indicating potential overfitting.

---

#### 3. Feature Importance and Spurious Correlation

Permutation importance and counterfactual swap tests are used to evaluate feature influence.

Result:  
- priors_count and age are consistently important features  
- Some features (e.g., race and sex) affect predictions when altered, suggesting possible proxy effects  

---

#### 4. Slice-Based Evaluation

Model performance is evaluated across subgroups:

- Race  
- Gender  
- Age groups  
- Charge type  

Metrics include accuracy, AUC, FPR, and FNR.

Result:  
- Certain subgroups show high FPR or FNR despite reasonable overall accuracy  
- Small subgroups exhibit unstable metrics due to limited sample size  

This indicates that aggregate performance may mask subgroup-level risks.

---

#### 5. Stress Testing and Sensitivity Analysis

Model robustness is evaluated by applying perturbations to key features (e.g., priors_count).

Metrics include:

- Mean predicted probability  
- Share of high-risk classifications  
- Sensitivity index  

Result: Predictions change significantly under perturbation, indicating that both models are sensitive and not fully robust.

---

### Key Findings

- No evidence of distribution drift  
- Logistic Regression generalizes better than Gradient Boosted Tree  
- Both models are sensitive to input changes  
- Subgroup analysis reveals fairness risks  
- Accuracy alone is insufficient for evaluating responsible ML  

---

### Conclusion

This analysis shows that a model can perform well overall while still exhibiting issues in fairness and robustness. Responsible machine learning requires evaluation beyond standard performance metrics, including subgroup analysis and stress testing.

---

### Tools and Libraries

- Python  
- pandas, numpy  
- scikit-learn  
- scipy  
- matplotlib  

---

## Project Structure
Assign4/
│── assign4.ipynb
│── README.md