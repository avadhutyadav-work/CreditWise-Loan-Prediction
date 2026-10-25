# CreditWise Loan System

## Problem Statement

SecureTrust Bank is a mid-sized financial company that offers personal and home loans to customers in urban and rural regions of India. Every day, hundreds of customers apply for loans through online and branch applications.

Currently, the bank uses a manual verification process to evaluate loan applications. Employees review income proofs, employment details, credit history, and other documents. This process is time-consuming and can lead to biased or inconsistent decisions.

The bank faces two major challenges:

1. **Good applicants may be rejected**, resulting in lost business.
2. **High-risk applicants may be approved**, potentially causing financial losses.

To address these challenges, the bank plans to introduce an intelligent loan approval system powered by Machine Learning. The system will analyze applicant information and predict whether a loan should be **Approved** or **Rejected** before final human verification.

The goal of this project is to develop a Machine Learning model using historical loan application data. The model should learn patterns from previous applications and help the bank make loan decisions that are faster, more consistent, and data-driven. Final decisions should still include appropriate human review.

## Project Objective

Build a classification model that predicts the loan approval outcome using applicant, financial, employment, and credit-related information.

- **Target column:** `Loan_Approved`
- **Target values:** `1 = Approved`, `0 = Rejected`
- **Problem type:** Supervised Machine Learning — Binary Classification

## Dataset Description

Each row in the dataset represents one loan applicant. The dataset contains personal, financial, employment, and credit-related attributes.

| Column | Description |
|---|---|
| `Applicant_ID` | Unique applicant identifier |
| `Applicant_Income` | Monthly income of the applicant |
| `Coapplicant_Income` | Monthly income of the co-applicant |
| `Employment_Status` | Employment type: Salaried, Self-Employed, or Business |
| `Age` | Applicant's age |
| `Marital_Status` | Marital status: Married or Single |
| `Dependents` | Number of dependents |
| `Credit_Score` | Credit bureau score |
| `Existing_Loans` | Number of loans currently running |
| `DTI_Ratio` | Debt-to-income ratio |
| `Savings` | Applicant's savings balance |
| `Collateral_Value` | Value of the collateral provided |
| `Loan_Amount` | Amount of loan requested |
| `Loan_Term` | Loan duration in months |
| `Loan_Purpose` | Purpose: Home, Education, Personal, or Business |
| `Property_Area` | Property location: Urban, Semi-Urban, or Rural |
| `Education_Level` | Education level: Graduate, Postgraduate, or Undergraduate |
| `Gender` | Applicant's gender |
| `Employer_Category` | Employer category: Government, Private, or Self |
| `Loan_Approved` | Target variable: `1` for Approved, `0` for Rejected |

## Suggested Project Workflow

1. Load the dataset and inspect its rows, columns, and data types.
2. Check for missing values, duplicate records, inconsistent categories, and outliers.
3. Perform exploratory data analysis (EDA) to understand applicant characteristics and approval patterns.
4. Prepare the features: handle missing data, encode categorical columns, and scale numerical features when appropriate.
5. Separate the input features (`X`) from the target (`y`). Exclude `Applicant_ID` from model training because it is an identifier rather than a meaningful applicant attribute.
6. Split the data into training and testing sets, using stratification when appropriate.
7. Train and compare suitable classification models, such as Logistic Regression, Decision Tree, Random Forest, and K-Nearest Neighbors.
8. Evaluate performance using a confusion matrix, precision, recall, F1-score, and ROC-AUC where appropriate. Pay particular attention to false approvals and false rejections.
9. Document the model's limitations, check for potential bias, and keep human review in the final decision process.

## Important Considerations

- Do not use the target column `Loan_Approved` as an input feature.
- Fit preprocessing steps only on the training data, ideally through a Scikit-learn pipeline, to avoid data leakage.
- Accuracy alone may not be sufficient for evaluating a loan approval model; review precision, recall, and the costs of different types of errors.
- Loan decisions can significantly affect people's lives. A model should be assessed for fairness, explainability, privacy, and compliance with applicable regulations before real-world use.
- This project is intended for learning and decision support, not for making unreviewed real-world lending decisions.
