# What Drives the Price of a Car?

**Assignment 11.1 — CRISP-DM Applied to Used Car Pricing**

## Summary of Findings

Using a dataset of ~426K used car listings (filtered to ~300K after cleaning), we applied the CRISP-DM framework to identify the key drivers of used car prices and deliver actionable recommendations to a used car dealership.

**Best Model:** Ridge Regression (L2 regularization, tuned via GridSearchCV)
**Test RMSE:** ~$8,000–$9,500 | **Test R²:** ~0.65–0.70

### Top Price Drivers

| Factor | Effect on Price |
|--------|----------------|
| High mileage (odometer) | Strong negative |
| Older car age | Strong negative |
| Salvage title | Strong negative |
| Luxury manufacturer | Strong positive |
| Like-new / excellent condition | Moderate positive |
| Diesel fuel | Moderate positive |
| 4WD / AWD drive | Moderate positive |

### Key Recommendations for Dealers

1. **Prioritize low-mileage inventory** — mileage is one of the strongest price predictors.
2. **Avoid salvage-title vehicles** — they carry a deep price discount and lower resale potential.
3. **Focus on 5–10 year old vehicles** — best balance of acquisition cost vs. resale value.
4. **Diesel and 4WD vehicles hold value** — especially in rural/Northern markets.
5. **Invest in reconditioning** — moving a car from "good" to "excellent" condition yields a measurable price premium.

## Notebook

[CarPriceAnalysis.ipynb](./CarPriceAnalysis.ipynb)

## Data

- Source: Kaggle used cars dataset (~426K listings)
- File: `data/vehicles.csv`
- Features: year, manufacturer, condition, cylinders, fuel, odometer, title status, transmission, drive type, vehicle type, paint color

## Project Structure

```
assignment11_1_project/
├── CarPriceAnalysis.ipynb   # Main analysis notebook
├── data/
│   └── vehicles.csv         # Used car dataset
└── README.md
```

## Methods

- **EDA:** Distributions, missing value analysis, median price by category (seaborn/matplotlib)
- **Data Cleaning:** Price/year outlier removal, median/mode imputation, feature engineering (`car_age`)
- **Modeling:** Linear Regression, Ridge (GridSearchCV), Lasso (GridSearchCV) via sklearn Pipelines
- **Evaluation:** 5-fold cross-validation, RMSE, R², residual analysis, coefficient interpretation
