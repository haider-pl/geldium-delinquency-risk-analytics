# Modeling and validation notes

- **Case study:** 500 rows, 80 delinquent (16%).
- **Split:** stratified 75/25 (375 train, 125 holdout; 20 positive holdout examples).
- **Candidates:** prior-probability baseline, logistic regression, decision tree, random forest, histogram gradient boosting, MLP.
- **Preprocessing:** median numerical imputation, most-frequent categorical imputation, standardization, one-hot encoding, and payment-history feature engineering.
- **Model selection:** 5-fold cross-validated average precision on training data; the holdout is for reporting, not choosing a winner.
- **Main caveat:** weak predictive signal, small holdout, poor calibration and uncertain subgroup fairness. Do not deploy.
- **Reproducibility:** supplied historical figures and CSV outputs may represent different notebook runs. Re-run the notebook with a fixed environment and compare its new outputs before publishing exact claims.
- **Temporal leakage:** validate that all six payment-month features precede the target delinquency period.
- **Privacy:** customer-level risk scores are for case-study evaluation only and should not be used for operational decisions.
