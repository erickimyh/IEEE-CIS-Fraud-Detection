# IEEE-CIS Fraud Detection

This notebook builds a fraud detection model on transaction data from the Kaggle competition https://www.kaggle.com/competitions/ieee-fraud-detection. Key parts of our implemention include

- feature engineering by aggregating transaction data by a synthetic user ID
- dimension reduction by clustering redundant features using Spearman correlation
- exploratory data analysis for finding identifying features and fradulent patterns across users

A key difference with other notebooks from this competition is that we ensure our model can only see features that could be computed "in real time". For instance, aggregations are computed cumulatively, and encodings only see the training set.

Using XGBoost, we achieve a ROC-AUC score of 0.942 on a public test set and 0.913 on a private test set. Given the class imbalance (only ~3.5% of transactions were fradulent), we acknowledge that ROC-AUC is not the most practical metric for fraud. As a future step, we aim to optimize for more practical metrics, such as PR-AUC or dollar-weighted metrics.