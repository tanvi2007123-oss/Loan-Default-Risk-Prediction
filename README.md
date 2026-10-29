Loan Default Risk Prediction

1. Project Overview

Loan Default Risk Prediction is a machine learning project that aims to identify loans that may be at risk of default. The project uses historical loan data to analyze borrower and loan characteristics and predict whether a loan is likely to be fully paid or charged off.

The project compares classification models, evaluates their performance, and identifies useful risk indicators to support credit-risk assessment.

2. Problem Statement

Loan defaults can cause significant financial losses for lenders. An effective risk assessment system can help identify potentially risky loans and support better-informed lending decisions.

This project develops a data-driven approach to predicting loan default using historical loan information and machine learning techniques.

3. Project Objectives

- Understand and analyze the loan dataset.
- Identify and handle missing values, duplicate records, and data quality issues.
- Perform Exploratory Data Analysis (EDA).
- Analyze relationships between loan characteristics and default outcomes.
- Conduct statistical tests to examine feature associations.
- Engineer relevant features and prevent data leakage.
- Build and compare machine learning classification models.
- Evaluate model performance using appropriate classification metrics.
- Identify important features and analyze prediction thresholds.
- Save the final trained model and generate test-set predictions when the test dataset is available.

4. Technologies and Libraries

Programming Language:Python

Development Environment: Jupyter Notebook / JupyterLab

Libraries Used:
- Pandas — data manipulation and analysis
- NumPy — numerical computations
- Matplotlib — data visualization
- Seaborn — statistical visualization
- Scikit-learn — preprocessing, model training, and evaluation
- SciPy — statistical hypothesis testing
- Statsmodels — multiple-testing adjustment
- Joblib — saving the trained model

5. Dataset Description

The project uses separate training and test datasets, with an optional sample submission file.

Expected input files:

- `loan_train.csv` — training data containing historical loan records and the target variable.
- `loan_test.csv` — test data used to generate predictions, if available.
- `loan_sample_submission.csv` — sample submission format, if provided.

The target column is `loan_status`.

The target is converted into a binary classification label:

- `0` — Fully Paid
- `1` — Charged Off

The exact dataset dimensions, feature names, and missing-value counts are examined during the data understanding stage.

Note:Place the required CSV files in the same directory as the notebook before running the project.

6. Project Workflow

Step 1: Data Understanding
Inspect dataset dimensions, column names, data types, summary statistics, and sample records.

Step 2: Data Cleaning
Identify missing values, duplicate records, and blank text values. Apply appropriate cleaning and preprocessing techniques.

Step 3: Target Preparation
Convert loan outcomes into binary labels for classification.

Step 4: Exploratory Data Analysis
Analyze numerical and categorical features, outcome distributions, correlations, and default rates. Use visualizations to identify patterns and potential risk indicators.

Step 5: Statistical Validation
Use the Mann–Whitney U test for numerical features and the Chi-square test for categorical features. Apply multiple-testing adjustment where appropriate.

Step 6: Feature Engineering and Leakage Prevention
Create date-derived features where possible and remove identifiers, unsuitable columns, and information that could reveal the loan outcome after origination.

Step 7: Feature Selection and Validation
Remove constant and high-cardinality features where appropriate. Use a chronological validation split when a reliable issue date is available; otherwise, use stratified sampling.

Step 8: Data Preprocessing
- Impute missing numerical values using the median.
- Scale numerical features.
- Impute missing categorical values using the most frequent value.
- Apply one-hot encoding to categorical features.

Preprocessing is integrated into machine learning pipelines.

Step 9: Model Training and Comparison
Train and compare three classification approaches:

1. Dummy Classifier — baseline model.
2. Logistic Regression — classification model with class balancing.
3. Random Forest Classifier — ensemble learning model with class balancing.

Step 10: Model Evaluation
Evaluate model performance using accuracy, precision, recall, F1-score, ROC-AUC, and PR-AUC. Use stratified cross-validation, classification reports, confusion matrices, and ROC and precision-recall curves where applicable.

Step 11: Model Interpretability
Examine Random Forest feature importance and permutation importance to understand which features contribute to predictive performance.

Step 12: Decision Threshold and Temporal Analysis
Analyze how different probability thresholds affect precision, recall, and F1-score. Examine monthly loan volumes and default rates when reliable date information is available.

Step 13: Final Model and Predictions
Select the model with the highest validation F1-score, refit the selected pipeline on the available labeled data, and save it as `loan_default_model.pkl`.

Generate test-set predictions and a submission CSV when the required test dataset is available.

7. Model Evaluation Metrics

| Metric | Purpose |

| Accuracy | Measures the proportion of correct predictions. |
| Precision | Measures how many predicted defaults are actual defaults. |
| Recall | Measures how many actual defaults are correctly identified. |
| F1-score | Balances precision and recall. |
| ROC-AUC | Measures the model's ability to distinguish between classes across thresholds. |
| PR-AUC | Evaluates the precision-recall trade-off, especially useful for imbalanced classes. |

The notebook uses validation F1-score to rank the candidate models, with other metrics providing additional insight into performance.

8. Installation and Setup

Install the required dependencies using pip:


pip install pandas numpy matplotlib seaborn scikit-learn scipy statsmodels joblib jupyter


9. How to Run the Project

1. Download or clone this GitHub repository.
2. Place the required CSV dataset files in the project directory.
3. Install the dependencies listed above.
4. Launch JupyterLab or Jupyter Notebook.
5. Open `loan default risk prediction(2).ipynb` or the renamed notebook file.
6. Run the cells sequentially from beginning to end.
7. Review the analysis, model evaluation results, visualizations, and generated artifacts.

Ensure the input file names match those specified in the notebook.

10. Expected Project Outputs

Depending on the available input files and successful notebook execution, the project produces:

- Data quality summaries and exploratory visualizations.
- Statistical test results.
- Model comparison and validation metrics.
- Classification reports and confusion matrices.
- ROC and precision-recall curves.
- Feature importance and permutation importance analyses.
- Decision threshold analysis.
- A serialized model pipeline: `loan_default_model.pkl`.
- Test-set prediction or submission CSV files, when applicable.

11. Business Applications

The model can support credit-risk assessment by helping lenders:

- Identify potentially high-risk loans for additional review.
- Prioritize manual application assessments.
- Examine factors associated with historical loan defaults.
- Monitor loan portfolio risk patterns.
- Support evidence-based lending decisions.

Predictions should be used as decision-support information rather than as the sole basis for approving or rejecting loan applications.

12. Limitations and Responsible Use

Model performance depends on the quality, representativeness, and availability of the training data. Historical patterns may change over time.

Before real-world deployment, the model requires further validation, fairness assessment, monitoring, and business review. Predictive associations do not necessarily establish causation.

13. Conclusion

This project implements an end-to-end machine learning workflow for loan default risk prediction, covering data understanding, data cleaning, exploratory analysis, statistical validation, feature engineering, leakage prevention, model comparison, evaluation, and interpretability.

The final model pipeline is saved for reproducibility, and test predictions can be generated when the necessary data is available. The project demonstrates how machine learning can support credit-risk analysis and more informed lending decisions.

14. Author

Name:Tanvi Ghatul

Project Title:Loan Default Risk Prediction

Tools: Python, JupyterLab, Pandas, NumPy, Matplotlib, Seaborn, and Scikit-learn