# Assignment 20.1 — Netflix Member Retention: Initial EDA & Baseline Model

## Project Overview

This project investigates what drives Netflix member retention. Specifically, the research question is:

> **Which member behaviors and household attributes most strongly predict Netflix retention (subscription tenure / lower churn risk)?**

The dataset is a simulated, synthetic dataset of 7,500 member records created for academic purposes. It does not contain any real Netflix member data.

## Repository Structure

```
assignment20_1_project/
├── data/
│   └── netflix_retention_simulated.csv   # Synthetic dataset (7,500 records)
├── notebook_20_1.ipynb                   # Main analysis notebook
└── README.md
```

## Data Description

The dataset contains 17 columns across three categories:

| Category | Features |
|---|---|
| Streaming behavior | `view_hours_30d`, `titles_started`, `titles_completed`, `titles_abandoned`, `completion_rate` |
| Engagement | `active_days_30d`, `thumbs_up`, `my_list_saves`, `device_mix`, `num_devices` |
| Demographics | `region`, `num_profiles`, `num_kids`, `kids_content_hours` |
| Target | `churned` (1 = churned, 0 = retained), `tenure_months` |

Overall churn rate in the dataset: **~14%**

## Summary of Findings

From the initial EDA and baseline logistic regression model:

- **Active days** is the strongest predictor of retention — members who open the app consistently are significantly less likely to churn
- **Completion rate** (titles completed / titles started) is the second strongest signal; members who finish what they start churn less
- **Mobile-only users** churn at a higher rate compared to multi-device users
- **Households with kids** show lower churn rates, and the effect increases with more children in the household
- The baseline logistic regression achieved a **test ROC-AUC of ~0.85**, providing a solid foundation for comparison in Module 24

## Methodology

1. **Data Cleaning** — checked for missing values, duplicates, and logical constraint violations (e.g., completed ≤ started); identified and reviewed outliers in viewing hours
2. **EDA** — visualized churn rates by region, device mix, kids in household; distribution comparisons between retained vs. churned members; correlation heatmap
3. **Feature Engineering** — derived `has_kids`, `is_mobile_only`, `is_multi_device`, `activity_rate`, `hours_per_active_day`, `social_engagement`; one-hot encoded region
4. **Baseline Model** — Logistic Regression with StandardScaler; 70/15/15 train/val/test split; evaluated using ROC-AUC

## Evaluation Metric

**ROC-AUC** was chosen as the primary metric because:
- The target is binary (churned / retained) and the classes are imbalanced (~14% churn)
- We care about how well the model *ranks* churn risk across members, not just raw accuracy
- AUC is threshold-agnostic, making it easier to compare models in Module 24

## Next Steps

Module 24 will expand on this baseline by:
- Adding 3 additional models (Ridge Logistic Regression, Random Forest, Gradient Boosting)
- Tuning hyperparameters via GridSearchCV
- Producing segment-level insights and non-technical recommendations

## Notebook

[notebook_20_1.ipynb](notebook_20_1.ipynb)
