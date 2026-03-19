## Predicting Emergency Hospital Admissions using Machine Learning
### Project Overview
This project develops a machine learning classification model to predict whether a hospital admission is likely to be an emergency case using patient-level healthcare data. The goal is to support early identification of high-risk patients and improve resource planning in emergency departments (EDs).

### Problem Statement
Emergency department overcrowding is a major challenge in healthcare systems, including Atlantic Canada, leading to long wait times and strained resources. This project addresses the problem of:

  ***Predicting emergency admissions using available patient and clinical data.***

A reliable model can help hospitals:
- Anticipate emergency demand
- Improve triage prioritization
- Optimize staffing and bed allocation

### Dataset
Initial dataset: Canadian Community Health Survey (CCHS) (Statistics Canada)
***Challenges***:
- Significant effort required to interpret and align the Data dictionary with variable names
Due to these limitations, the project transitioned to a:

Final dataset: Synthetic healthcare dataset (Kaggle). https://www.kaggle.com/datasets/prasad22/healthcare-dataset/data
- Pros: Easier to process and model
- Limitation: Lacked critical clinical features influencing admissions

#### Key Features:
Age, Gender
Blood Type
Medical Condition
Insurance Provider
Billing Amount
Medication
Test Results
Admission Date

#### Target Variable:
EmergencyFlag (engineered from Admission Type)

Key Insight: Data quality and feature relevance significantly impact model performance.

### Data Processing
Removed duplicates and irrelevant fields
Converted date variables to datetime
Created engineered features:
- EmergencyFlag (target variable)
- age_range
- admission_month
Handled categorical variables using encoding
Addressed class imbalance SMOTE

### Exploratory Data Analysis (EDA)
Distribution of numerical and categorical variables
Relationship between features and the target variable
Age-based patterns and monthly admission trends

### Machine Learning Approach
This was treated as a binary classification problem.

A structured ML pipeline was implemented for:
•	Preprocessing using ColumnTransformer
•	Model training using ImbPipeline

Models Evaluated:
•	Logistic Regression
•	Decision Tree
•	Random Forest
•	Support Vector Machine (SVM)
•	k-Nearest Neighbors (kNN)
•	Gradient Boosting
•	AdaBoost
•	XGBoost

### Evaluation Metrics
Due to class imbalance, focus was placed on:
•	F1 Score
•	Recall (Emergency class)
•	ROC-AUC
•	Accuracy (secondary)

### Results
•	The Decision Tree Model performed best on test, achieving a high recall of 0.91, F1 of 0.48
•	However, ROC-AUC ≈ 0.50, indicating weak class separation due to limited feature quality.

### Limitations
•	The dataset lacked key clinical predictors such as:
  -	Triage scores
  - Prior ED visits
  - Patient history
•	Synthetic dataset does not fully reflect real-world healthcare complexity
•	Model performance constrained by feature relevance

### Future Improvements
•	Incorporate more informative clinical data (triage levels, patient history, prior ED visits)


