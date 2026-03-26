# Assignment 24.1 — Netflix Member Retention: Final Capstone

## Research Question

> **Which member behaviors and household attributes most strongly predict Netflix retention, and how much does each factor contribute?**

## Project Summary

This capstone analyzes simulated Netflix member data to identify the key drivers of member retention and churn. Using a synthetic dataset of 7,500 member records (no real Netflix data), I built and compared four machine learning models, tuned hyperparameters via GridSearchCV, and translated findings into actionable product recommendations.

## Repository Structure

```
assignment24_1_project/
├── notebook_24_1.ipynb        # Final analysis notebook
└── README.md

assignment20_1_project/        # Module 20 initial report (data lives here)
├── data/
│   └── netflix_retention_simulated.csv
├── notebook_20_1.ipynb
└── README.md
```

## Data

Synthetic dataset with 7,500 records and 17 features across three categories:
- **Streaming behavior:** viewing hours, titles started/completed/abandoned, completion rate
- **Engagement:** active days, devices used, thumbs-up, My List saves
- **Demographics:** region, profiles per account, number of kids, kids content hours
- **Target:** `churned` (binary — 1 = churned, 0 = retained)

Churn rate: ~14%

## Models Compared

| Model | Notes |
|---|---|
| Logistic Regression | Baseline from Module 20 |
| Ridge Logistic Regression | L2 regularization; C tuned via GridSearchCV |
| Random Forest | n_estimators, max_depth, min_samples_leaf tuned via GridSearchCV |
| Gradient Boosting | n_estimators, learning_rate, max_depth tuned via GridSearchCV |

All models evaluated using **ROC-AUC** on a held-out validation set, with final evaluation on a separate test set.

## Key Findings

1. **Active days is the strongest retention signal** — members who open the app consistently are far less likely to churn. The drop in churn rate from the lowest to highest active-days quartile is dramatic.

2. **Completion rate outperforms raw viewing hours** — a member who finishes what they start retains better than one who watches more but abandons most content. Content-match quality matters.

3. **Mobile-only users are highest churn risk** — single-device users, especially mobile-only, show meaningfully higher churn rates than multi-device users.

4. **Households with kids churn less** — kids content engagement is associated with stronger retention, and the effect grows with more children in the household.

## Recommendations

| Finding | Action |
|---|---|
| Low active days predicts churn | Re-engagement campaigns for members with fewer than 7 active days in a month |
| High abandonment rate = higher churn | Improve recommendation relevance; surface content matched to user attention span |
| Mobile-only = higher risk | Encourage TV/desktop experience; highlight features better on large screen |
| Kids households retain longer | Invest in kids content variety; family mode onboarding for new accounts |

## Evaluation Metric

**ROC-AUC** was selected because:
- The target is imbalanced (~14% churn) — accuracy alone is misleading
- We care about ranking churn risk across members, not just a binary cutoff
- AUC is stable and threshold-agnostic, making cross-model comparison clean

## Notebooks

- [Module 20.1 — EDA & Baseline](../assignment20_1_project/notebook_20_1.ipynb)
- [Module 24.1 — Final Models & Findings](notebook_24_1.ipynb)
