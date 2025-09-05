Credit Default Prediction – Programming for Data Analysis CA2

Author: Akash Sachin Nikam (DBS – MSc Data Analytics)
Module: B9DA108 – Programming for Data Analysis
Lecturer: Alexander Victor

Project Overview

This project investigates credit card default behavior using the well-known UCI “Default of Credit Card Clients” dataset. The objective was to explore data patterns, build predictive models, and evaluate their effectiveness in forecasting default risk. Early identification of high-risk clients is critical for financial institutions in managing lending risk, reducing losses, and improving profitability.

The project was developed in Python (Jupyter Notebook) and covers data cleaning, exploratory analysis, statistical modeling, and performance evaluation.

Dataset

Source: UCI Machine Learning Repository – Default of Credit Card Clients

Rows: 30,000

Columns: 25 features + 1 target (default payment next month)

Target: Binary (1 = default, 0 = non-default)

Class distribution: ~22% defaults, 78% non-defaults (imbalanced dataset)

Features

Demographics: Age, Gender, Education, Marital Status

Financial: Credit limit, past bill amounts, past payments

Repayment history: PAY_0 to PAY_6 (most predictive of default)

Methodology

Data Preprocessing

Fixed header issues, renamed target variable as default

Dropped ID column

Verified no missing values

Addressed class imbalance with class_weight='balanced'

Exploratory Data Analysis

Histograms: credit limit, age, distribution of defaults

Boxplots: outliers in bill and payment amounts

Countplots: default rates by gender, education, marital status

Correlation heatmap: strong correlation between repayment history (PAY_0–PAY_6) and default

Modeling

Logistic Regression (plain & weighted)

Decision Tree Classifier

Random Forest Classifier

Training on 80% of data, testing on 20%

Metrics: Accuracy, Precision, Recall, F1-score

Visualizations: Confusion matrices and classification reports

Results
Model	Accuracy	Recall (Defaulters)	Precision	Notes
Logistic Regression (plain)	78%	0%	–	Failed to capture defaults
Weighted Logistic Regression	56%	73%	Low	High sensitivity, low accuracy
Decision Tree	73%	40%	–	Balanced trade-off
Random Forest	81.5%	34%	65%	Best overall performance

Key insights:

Repayment history (PAY_0) is the strongest predictor.

Lower credit limits and higher outstanding bills/payments increase risk.

Demographic variables are weaker predictors compared to behavioral features.

Results Folder

Screenshots of:

Default distribution plots

Correlation heatmap

Confusion matrices

Model performance graphs

Discussion

Random Forest achieved the best overall balance of accuracy and precision, making it the most practical for real-world credit scoring.

Logistic Regression struggled with imbalance unless weighted.

Decision Trees provided interpretability but slightly weaker results.

Limitation: recall for defaulters remained modest (~34%), meaning many defaults went undetected.

Improvements: use boosting methods (XGBoost, LightGBM), hyperparameter tuning, and integration of external behavioral/economic factors.

Academic Artefacts

Final Report: reports/CA2_programming_Final_report.pdf

Presentation Slides: reports/CA2_programming_final_ppt.pptx

How to Run

Clone/download this repo.

Open notebooks/CA2_project_code.ipynb in Jupyter/VS Code.

Install dependencies:

pip install pandas numpy matplotlib seaborn scikit-learn


Run cells step by step (preprocessing → EDA → models → evaluation).

Visual outputs and plots will be saved in results/.

Contact

Akash Sachin Nikam – MSc Data Analytics, Dublin Business School
Email: aakashn3118@gmail.com
