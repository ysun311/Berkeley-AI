# Bank Marketing Classification — Comparing Classifiers

## Business Problem

A Portuguese bank ran phone-based marketing campaigns trying to get clients to subscribe to a term deposit. The goal is to predict whether a client will subscribe (`y = yes`) based on their profile and the economic context at the time of the call.

This is a binary classification problem with an imbalanced target (~11% positive rate).

## Dataset

UCI Machine Learning Repository — [Bank Marketing Dataset](https://archive.ics.uci.edu/ml/datasets/Bank+Marketing)

41,188 records, 20 input features. I used a subset of 6 features covering three categories:

| Category | Features Used |
|---|---|
| Client profile | `age`, `job` |
| Call info | `duration`, `campaign` |
| Economic context | `euribor3m`, `emp.var.rate` |

## Models Compared

- Logistic Regression (with L2 regularization, GridSearchCV on C)
- K-Nearest Neighbors (GridSearchCV on k)
- Decision Tree (GridSearchCV on max_depth and min_samples_leaf)
- SVM (GridSearchCV on C and kernel — trained on 5k subsample due to compute constraints)

## Evaluation Metric

**ROC-AUC** — chosen because accuracy is misleading on imbalanced data. A model that always predicts "no" gets 89% accuracy but is completely useless. AUC measures how well the model ranks subscribers vs. non-subscribers across all possible thresholds.

## Key Findings

- **Call duration** is the strongest single predictor — longer calls correlate with successful subscriptions. That said, duration is only known *after* the call, so it's not useful for pre-call targeting.
- **Euribor 3M rate** (market interest rate) is inversely associated with subscription — clients subscribe more when rates are low and a locked-in deposit looks more attractive.
- **Job type** carries some signal — retired clients and students convert at higher rates than admin or blue-collar workers.
- Logistic Regression and SVM performed best on AUC. Decision Tree was competitive. KNN lagged behind.

## Recommendations

- Time campaigns during low interest rate environments when conversion rates are naturally higher
- Train call center staff for longer, more engaged conversations — call duration is strongly linked to conversion
- Segment targeting toward retired clients and students who show higher subscription rates

## Notebook

[notebook_17_1.ipynb](notebook_17_1.ipynb)
