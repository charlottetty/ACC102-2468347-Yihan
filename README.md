# ACC102-2468347-Yihan
# Home Equity Loan Default Prediction – ACC102 Mini Project (Track 2)

## Project Overview
This project builds a binary classification model to predict whether a borrower will default on a home equity loan. The model helps financial institutions reduce credit risk by identifying high-risk applicants before loan approval.

## Problem Statement
- **Goal**: Predict `BAD` (1 = default, 0 = no default)
- **Business Value**: Reduce default losses, enable risk-based pricing, support automated underwriting.

## Dataset
- **Source**: HMEQ dataset from Kaggle (Home Equity)
- **Access Date**: [Insert Date]
- **Size**: 5,960 rows, 13 variables
- **Target**: `BAD` (20% default rate)

## Methods & Workflow
1. **Data Preprocessing**: Median imputation for numeric columns, mode imputation for categorical columns
2. **Feature Engineering**:
   - `loan_to_value` = LOAN / VALUE
   - `credit_usage` = LOAN / CLAGE
   - `total_derog_delinq` = DEROG + DELINQ
   - `inquiry_per_account` = NINQ / CLNO
   - `debt_burden` = DEBTINC * LOAN / 10000
3. **Modeling**: Logistic Regression (baseline) vs. Decision Tree (max_depth=5)
4. **Evaluation**: Accuracy, Precision, Recall, F1-Score, ROC AUC

## Results
| Model | Accuracy | Precision (class 1) | Recall (class 1) | F1-Score |
|-------|----------|---------------------|------------------|-----------|
| Logistic Regression | 0.84 | 0.70 | 0.33 | 0.45 |
| Decision Tree | 0.89 | 0.73 | 0.70 | 0.71 |

**Decision Tree** is the better model for identifying defaulters (higher Recall and F1-Score).

## How to Run
1. Clone this repository
2. Install dependencies: `pip install -r requirements.txt`
3. Run the Jupyter Notebook: `acc102_modifiedfinally.ipynb`

## Author
[Yihan.Tang] – [2468347] – ACC102 Mini Assignment, Track 2
