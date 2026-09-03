# 🏦 Loan Scoring Model

A machine learning project for credit risk assessment and lending decision support, built on the Home Credit dataset.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Dataset](#dataset)
- [Project Pipeline](#project-pipeline)
- [Models & Results](#models--results)
- [Recommendation](#recommendation)
- [File Structure](#file-structure)
- [Getting Started](#getting-started)
- [Requirements](#requirements)

---

## Overview

The primary objective of this project was to develop a robust **scoring model** to assist in lending decisions. The pipeline covers:

- Thorough data analysis and cleaning across multiple financial data sources
- Feature engineering and selection to extract predictive signals
- Addressing dataset class imbalance for reliable model training
- Training and evaluating three classification models
- Recommending the best model for production deployment

---

## Dataset

This project uses the [Home Credit Default Risk](https://www.kaggle.com/competitions/home-credit-default-risk) dataset. The following files are used:

| File | Description |
|---|---|
| `application_train.xls` | Main training set with loan application data and target variable |
| `application_test.xls` | Test set for generating final predictions |
| `bureau.xls` | Client's previous credits from other financial institutions |
| `bureau_balance.xls` | Monthly balances of previous credits in the Credit Bureau |
| `credit_card_balance.xls` | Monthly credit card balance snapshots |
| `installments_payments.xls` | Repayment history for previously disbursed credits |
| `POS_CASH_balance.xls` | Monthly balance snapshots of POS and cash loans |
| `previous_application.xls` | All previous loan applications at Home Credit |
| `HomeCredit_columns_description.xls` | Descriptions of all columns across files |
| `sample_submission.xls` | Sample submission file in the correct format |

---

## Project Pipeline

```
Raw Data (10 files)
      │
      ▼
Data Cleaning & Preprocessing
  - Handling missing values
  - Encoding categorical variables
  - Merging supplementary tables
      │
      ▼
Feature Engineering & Selection
  - Aggregating bureau & balance data
  - Creating interaction features
  - Dropping low-variance / redundant features
      │
      ▼
Imbalance Handling
  - Addressing class imbalance (default vs. non-default)
      │
      ▼
Model Training
  ├── Random Forest Classifier
  ├── Logistic Regression
  └── Decision Tree Classifier
      │
      ▼
Evaluation (AUC ROC)
      │
      ▼
Recommendation → Decision Tree Classifier ✅
```

---

## Models & Results

Three classification models were trained and evaluated using **AUC ROC** as the primary metric:

| Model | AUC ROC | Notes |
|---|---|---|
| 🌲 **Decision Tree Classifier** | ⭐ Highest | Best accuracy & interpretability |
| 🌳 Random Forest Classifier | High | Strong performance, less interpretable |
| 📈 Logistic Regression | Competitive | Good baseline, linear assumptions |

All models were trained after feature enhancement and imbalance correction, yielding **remarkable AUC ROC scores** across the board.

---

## Recommendation

> ✅ **Implement the Decision Tree Classifier.**

The Decision Tree Classifier is recommended for production due to:

- **Greater accuracy** — achieved the highest AUC ROC among all models tested
- **Interpretability** — decision paths can be visualized and explained to stakeholders and regulators
- **Practical suitability** — transparent rules make it easy to justify individual lending decisions

This makes it the best choice for determining whether to lend money to specific borrowers.

---

## File Structure

```
loan-scoring-model/
│
├── data/
│   ├── application_train.xls
│   ├── application_test.xls
│   ├── bureau.xls
│   ├── bureau_balance.xls
│   ├── credit_card_balance.xls
│   ├── installments_payments.xls
│   ├── POS_CASH_balance.xls
│   ├── previous_application.xls
│   ├── HomeCredit_columns_description.xls
│   └── sample_submission.xls
│
├── notebooks/
│   └── scoring_model.ipynb       # Full analysis and model training
│
├── outputs/
│   └── scoring_model.html        # Rendered HTML report of the full project
│
└── README.md
```

---

## Getting Started

1. **Clone the repository**
   ```bash
   git clone https://github.com/JJY-DS/loan-scoring-model.git
   cd loan-scoring-model
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Place the dataset files** in the `data/` directory (see [Dataset](#dataset) above).

4. **Run the notebook**
   ```bash
   jupyter notebook notebooks/scoring_model.ipynb
   ```

---

## Requirements

```
pandas
numpy
scikit-learn
matplotlib
seaborn
imbalanced-learn
jupyter
```

Install with:
```bash
pip install pandas numpy scikit-learn matplotlib seaborn imbalanced-learn jupyter
```

---

## License

This project is licensed under the **MIT License** — free to use, copy, modify, and distribute with attribution.

```
MIT License

Copyright (c) 2026 [Your Name]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

> Dataset sourced from the [Home Credit Default Risk Kaggle Competition](https://www.kaggle.com/competitions/home-credit-default-risk).# Loan-Scoring-Model-
A machine learning project for credit risk assessment and lending decision support, built on the Home Credit dataset.
