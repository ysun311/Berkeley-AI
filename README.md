# Giselle Sun — Berkeley AI/ML Portfolio

Hi, I'm Giselle. I'm a Product Manager at Netflix focused on streaming quality, app reliability, device lifecycle and AI-driven decision platforms. This repository is my portfolio for the **UC Berkeley Professional Certificate in Machine Learning and Artificial Intelligence** — built jointly by Berkeley's College of Engineering and Haas School of Business.

Five projects across regression, classification, ensemble methods, and feature engineering. Each one ends with a business translation, because models that nobody acts on don't matter.

---

## Capstone — Predicting Netflix Member Retention

**[Capstone: Netflix Retention & Churn](./Capstone_Netflix_Retention_Churn_Classification_Regression)**

Built and compared four ML models on a synthetic dataset of 7,500 streaming-member records to identify the strongest drivers of retention.

> *Note: Dataset is synthetic. It does not contain any real Netflix member data.*

- **Models:** Logistic Regression, Ridge Logistic Regression, Random Forest, Gradient Boosting
- **Tuning:** GridSearchCV across all four
- **Metric:** ROC-AUC (chosen because target is imbalanced at ~14% churn)
- **Headline insight:** Completion rate (titles finished ÷ titles started) predicts retention *better* than raw viewing hours — content-match quality outperforms content volume
- **Other findings:** active days is the single strongest signal; mobile-only users have meaningfully higher churn risk; kids-in-household reduces churn

Findings translated into four product recommendations: re-engagement campaigns for low-activity members, recommendation-relevance work for high-abandonment users, multi-device adoption pushes for mobile-only members, and kids-content investment for family accounts.

---

## Other Projects

| # | Project | Problem | Approach | Headline Result |
|---|---|---|---|---|
| 04 | [Netflix Retention — Baseline](./Capstone_Netflix_Retention_Baseline_Analysis) | Same dataset, EDA + baseline | Logistic Regression, feature engineering | Test ROC-AUC ~0.85; identified active days + completion rate as top features |
| 03 | [Bank Marketing Classification](./Bank_Marketing_Classification) | UCI Portuguese bank dataset (41K records, ~11% positive). Will the client subscribe? | Logistic Regression, KNN, Decision Tree, SVM compared via GridSearchCV | Logistic Regression and SVM tied for best AUC; call duration and Euribor rate were strongest signals |
| 02 | [Used Car Pricing — CRISP-DM](./Used_Car_Pricing_Regression) | Kaggle dataset (~426K listings, ~300K after cleaning). What drives used-car prices? | CRISP-DM framework; Ridge Regression with L2 regularization, GridSearchCV | Test RMSE ~$8K-$9.5K, R² ~0.65-0.70; mileage, age, and salvage status dominate |
| 01 | [Coupon Acceptance EDA](./Coupon_Acceptance_EDA) | UCI Mechanical Turk driving scenarios (12,684 records). Which contextual factors drive coupon acceptance? | EDA + behavioral segmentation | Frequent bar-goers 2.5x more likely to accept bar coupons; carryout coupons outperform dine-in by a wide margin |

---

## Skills Demonstrated

- **Modeling:** logistic regression, ridge regression, k-nearest neighbors, decision trees, SVMs, random forests, gradient boosting
- **Pipeline:** train/val/test splits, feature engineering, hyperparameter tuning via GridSearchCV, regularization
- **Evaluation:** ROC-AUC for imbalanced classification, RMSE/R² for regression, threshold-agnostic comparison
- **Tools:** Python, pandas, scikit-learn, NumPy, matplotlib, seaborn, Jupyter, Git
- **Methodology:** CRISP-DM, EDA-first approach, business translation as a non-negotiable last step

---

## About Me

PM at Netflix since 2022, formerly at American Airlines (Pricing Strategy → Revenue Insights → Ancillary Product). Chemical Engineering degree from UT Austin, three years as a process engineer, then an MBA from Northwestern Kellogg.

I treat AI as a tool, not a destination. Most of my best work has been turning fragmented data into trusted workflows, then evolving those workflows into intelligent decision platforms.

→ [LinkedIn](https://www.linkedin.com/in/yiqi-giselle-sun/)
