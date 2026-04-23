# ACC102-2468347-Yihan
# Home Equity Loan Default Prediction – ACC102 Mini Project (Track 2)

## 1. Problem & User
This project builds a binary classification model to predict whether a borrower will default on a home equity loan. The target users are bank loan officers and credit risk analysts who need a fast, data-driven tool to support lending decisions and reduce financial losses from defaults.

## 2. Data
- **Source**: HMEQ dataset from Kaggle (https://www.kaggle.com/datasets/ajay1735/hmeq-data)
- **Access Date**: 16 April 2026
- **Size**: 5,960 rows, 13 variables
- **Target**: `BAD` (1 = default, 0 = no default; 20% default rate)
- **Key fields**: LOAN, MORTDUE, VALUE, REASON, JOB, YOJ, DEROG, DELINQ, CLAGE, NINQ, CLNO, DEBTINC

## 3. Methods
- **Preprocessing**: Median imputation for numeric columns, mode imputation for categorical columns, one-hot encoding for REASON and JOB
- **Feature Engineering**:
  - `loan_to_value` = LOAN / VALUE
  - `credit_usage` = LOAN / CLAGE
  - `total_derog_delinq` = DEROG + DELINQ
  - `inquiry_per_account` = NINQ / CLNO
  - `debt_burden` = DEBTINC * LOAN / 10000
- **Models**: Logistic Regression (baseline) vs. Decision Tree (max_depth=5)
- **Evaluation**: Accuracy, Precision, Recall, F1-Score, ROC AUC

## 4. Key Findings
- Decision Tree outperforms Logistic Regression across all metrics
- Decision Tree Recall for default class: 70% (vs. Logistic Regression 33%)
- Most important features: `DEBTINC` and `total_derog_delinq`
- Hyperparameter tuning (GridSearchCV with scoring="recall") achieved 70.8% cross-validated recall

## 5. How to Run
1. Clone this repository
2. Install dependencies: `pip install -r requirements.txt`
3. Run the Jupyter Notebook: `acc102_modifiedfinally.ipynb`

## 6. Product Link / Demo
- **GitHub Repository**: [Insert your repo link here]
- **Demo Video**: [Insert Mediasite link here]

## 7. Limitations & Next Steps
- **Limitations**: No temporal information in dataset; only two simple models tested; correlation does not imply causation
- **Next Steps**: Test ensemble methods (Random Forest, XGBoost); add cost-benefit analysis for threshold tuning; collect more granular borrower data

## Author
[Yihan.Tang] – [2468347] – ACC102 Mini Assignment, Track 2
