Credit Card Default Prediction -- Machine Learning Project
Project Overview
This project uses machine learning classification algorithms to predict
whether a credit-card customer is likely to default on their payment in
the following month.
The project follows a structured machine learning workflow, beginning
with data loading and exploratory analysis and ending with model
training and evaluation.
Target variable: `default payment next month`
`0` -- No default
`1` -- Default
Project Objectives
Explore and understand the credit-card dataset.
Prepare the data for machine learning.
Identify and cap outliers using the Interquartile Range (IQR)
method.
Encode categorical predictor variables.
Apply feature selection using `SelectKBest`.
Standardize numerical features using `StandardScaler`.
Train and compare multiple classification algorithms.
Evaluate model performance using classification metrics.
Machine Learning Workflow
The Jupyter Notebook covers the following stages:
Import libraries -- Import Pandas, NumPy, Matplotlib, Seaborn,
and the required Scikit-learn modules.
Load the dataset -- Read the `creditcard.csv` file and check the
dataset structure.
Statistical analysis -- Inspect data types, descriptive
statistics, and target-class distribution.
Handle missing values -- Remove records with a missing target
and fill missing numerical predictor values using the median.
Handle duplicates -- Identify and remove duplicate rows.
Outlier treatment -- Apply IQR-based capping to numerical
predictor columns, excluding the ID and target columns.
Categorical encoding -- Apply One-Hot Encoding to the
categorical predictor columns `SEX`, `EDUCATION`, and `MARRIAGE`.
Separate features and target -- Create independent variables
(`X`) and the dependent variable (`y`).
Data visualization -- Explore target distribution, age, credit
limit, default rates, and selected feature correlations.
Train-test split -- Split the data into training and testing
sets using an 80:20 ratio and stratification.
Feature scaling -- Apply `StandardScaler` to numerical predictor
features.
Feature selection -- Use `SelectKBest` with the ANOVA F-test
(`f_classif`) to select the top 20 transformed features.
Model building -- Train four classification algorithms.
Model evaluation -- Compare model metrics and inspect the
classification report and confusion matrix.
Algorithms Used
The notebook trains and compares these classification algorithms:
Logistic Regression
Decision Tree Classifier
Random Forest Classifier
K-Nearest Neighbours (KNN)
Evaluation Metrics
The models are compared using:
---
Metric                              Purpose
---
Accuracy                            Measures the overall proportion of
correct predictions.
Precision                           Measures how many predicted default
cases are actual defaults.
Recall                              Measures how many actual default
cases are correctly identified.
F1-score                            Balances precision and recall.
ROC-AUC                             Measures the model's ability to
distinguish between the two classes
across classification thresholds.
The notebook selects the model with the highest F1-score as its
best-performing model. Since this dataset is a classification problem
and the classes may be imbalanced, recall for the default class (`1`)
should also be considered when interpreting results.
Technologies and Libraries
Python
Jupyter Notebook
Pandas
NumPy
Matplotlib
Seaborn
Scikit-learn
Project Files
``` text
Credit-Card-Default-Prediction/
│
├── credit_card_default_ml_project_student_ready.ipynb
├── creditcard.csv
└── README.md
```
The dataset file is required to run the notebook and is not included in
this project structure unless you add it separately.
Installation and Setup
1. Clone the repository
``` bash
git clone <your-repository-url>
cd <repository-folder>
```
Replace the placeholders with your GitHub repository URL and folder
name.
2. Install the required libraries
``` bash
pip install numpy pandas matplotlib seaborn scikit-learn jupyter
```
3. Add the dataset
Place the dataset file named `creditcard.csv` in the same directory as
the Jupyter Notebook.
The notebook includes a small header check to accommodate some copies of
the dataset that contain an extra header row and an unnamed index
column.
4. Launch Jupyter Notebook
``` bash
jupyter notebook
```
Open `credit_card_default_ml_project_student_ready.ipynb` and run the
cells in order.
Data Preparation and Leakage Note
The notebook uses a train-test split before fitting the encoding,
scaling, and feature-selection steps. These transformations are included
in a Scikit-learn pipeline so they are learned from the training data
and then applied to the test data.
For a stricter evaluation workflow: fit outlier-capping thresholds
using only the training data and apply those same thresholds to the test
data. The current notebook performs IQR capping before the train-test
split, so the outlier boundaries are calculated using the full dataset.
This can introduce information leakage into evaluation.
Results
The notebook generates a model comparison table containing Accuracy,
Precision, Recall, F1-score, and ROC-AUC. It also displays:
The best-performing model based on F1-score.
A classification report.
A confusion matrix.
Run the notebook to generate the actual scores. No performance values
are stated here because they depend on the dataset used and the
execution results.
Disclaimer
This project is intended for educational and learning purposes. It
should not be used to make real-world credit or lending decisions
without appropriate validation, fairness assessment, explainability,
privacy safeguards, and regulatory review.
Author
[Your Name]
Machine Learning Project -- Credit Card Default Prediction
