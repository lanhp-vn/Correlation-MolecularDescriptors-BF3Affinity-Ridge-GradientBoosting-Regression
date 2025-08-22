## Correlating Molecular Descriptors with BF3 Affinity

### Overview
This project investigates how molecular descriptors correlate with Boron trifluoride (BF3) affinity and builds predictive models using Ridge Regression and Gradient Boosting Regression.

### Data
- Input: `BF3_Affinity_Dataset.csv`
- Target: `BF3_Affinity(kJ/mol)`
- Features: a mix of discrete (e.g., `MW`, `AMW`, `TPSA(Tot)`, `ALOGP`) and continuous descriptors (see notebook for full list).

### Descriptor–Target Correlation (absolute r)
- Discrete descriptors: mean 0.156, SD 0.090, max 0.411, min 0.0069
- Continuous descriptors: mean 0.115, SD 0.101, max 0.495, min 0.00024
- Overall max absolute correlation: 0.495

### Model Performance
Train/test split uses stratified shuffling over binned target values; cross-validation uses Repeated K-Fold (5 folds × 6 repeats, random_state=22).

- Ridge Regression
  - Test: R = 0.905, MAPE = 7.29%
  - Cross-validation: mean R = 0.930 ± 0.017; mean RMSE = 8.86 kJ/mol

- Gradient Boosting Regression
  - Test: R = 0.858, MAPE = 7.95%
  - Cross-validation: mean R = 0.911 ± 0.036; mean RMSE = 9.71 kJ/mol

**Takeaway**: Ridge shows slightly better generalization (higher CV R, lower CV RMSE) and lower test MAPE in this setup.

### Reproducibility
Open and run `code.ipynb`.
Dependencies: numpy, pandas, matplotlib, scikit-learn.

### Repository
Code and results are synchronized to `lanhp-vn/Correlation-MolecularDescriptors-BF3Affinity-Ridge-GradientBoosting-Regression` on GitHub. See the repo here: [GitHub repository](https://github.com/lanhp-vn/Correlation-MolecularDescriptors-BF3Affinity-Ridge-GradientBoosting-Regression).


