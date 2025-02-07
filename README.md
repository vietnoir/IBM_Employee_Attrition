# IBM Employee Attrition Analysis
This repository contains the IBM Data Science Capstone project, focusing on Employee Attrition Analysis. The project explores key factors contributing to employee attrition and utilizes machine learning models to predict employee churn.

## Project Overview
Employee attrition, or churn, refers to the reduction in a company’s workforce due to resignations, retirements, or layoffs. High attrition rates can be costly for organizations due to recruitment, training, and productivity losses.

This project leverages the IBM HR Analytics Employee Attrition & Performance dataset to analyze patterns in employee attrition and build predictive models.

## Repository Structure
- ANALYZING EMPLOYEE ATTRITION.pdf: Business presentation summarizing key findings and potential business impact
- Attrition.ipynb: Main analysis performed in Google Colab
- README.md: Project documentation (this file)

## Dataset
The dataset used in this project is IBM HR Analytics Employee Attrition & Performance, available on [Kaggle](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset). It consists of 1470 employees and 35 attributes, including demographic and job-related features.

### Key Features:
- Demographics: Age, Gender, Marital Status, Education Field
- Job Information: Job Role, Department, Job Satisfaction, Monthly Income
- Work Environment: Work-Life Balance, Overtime, Distance From Home
- Performance Metrics: Performance Rating, Training, Years With Current Manager
- Target Variable: Attrition (Yes/No)

## Key Research Questions
- What demographic or job-related factors are correlated with attrition?
- Can machine learning models effectively predict employee attrition?
- What actionable insights can be derived to help reduce attrition?

## Data Preprocessing & Feature Engineering
- Dropped uninformative variables: EmployeeNumber, EmployeeCount, Over18, StandardHours.
- Handled categorical variables: Encoded using one-hot encoding and binary encoding.
- Feature Scaling: Applied StandardScaler for numerical features.
- Class Imbalance Handling: Used SMOTE, Borderline-SMOTE, and ADASYN to balance the dataset.

## Machine Learning Models
To predict employee attrition, multiple machine learning techniques were implemented and evaluated:
- Logistic Regression
  -  Weighted logistic regression with class balancing
  - Decision threshold optimization for better recall
- Random Forest
  - Hyperparameter tuning using GridSearchCV
  - Resampling techniques (SMOTE, ADASYN, Borderline-SMOTE)
- Gradient Boosting Models
  - CatBoost: Handles categorical variables natively, provides high accuracy
  - XGBoost: Best performing model with highest recall and AUC
  - LightGBM: Efficient and scalable boosting algorithm

## Model Evaluation
- Performance Metrics: Precision, Recall, F1-Score, ROC-AUC
- Trade-off Analysis: Prioritizing recall to minimize false negatives
- Hyperparameter Tuning: Grid search and random search optimization

### Final Model Selection:
XGBoost was selected as the final model due to its highest recall and AUC, ensuring maximum identification of employees at risk of attrition.

## SHAP Analysis - Feature Importance
SHAP (SHapley Additive exPlanations) was used to interpret the most impactful features:

|  Rank | Feature | Impact on Attrition |
|----------|----------|----------|
| 1    | Overtime |High overtime increases attrition |
| 2    | Monthly Income | Lower salaries lead to higher attrition |
| 3    | Stock Option Level | No stock options correlate with attrition |
| 4    | Years With Current Manager |Shorter tenure increases attrition risk |
| 5    | Age | Younger employees are more likely to leave |
| 6    | Work Environment Satisfaction | Poor work environment drives attrition |
| 7    | Relationship Satisfaction | Low satisfaction contributes to turnover |

## Key Insights & Business Recommendations
- Improve Work-Life Balance: Employees working overtime are at a higher risk of attrition.
- Compensation Adjustments: Employees with lower salaries tend to leave. Salary increments or performance-based incentives could help retain top talent.
- Stock Options as Retention Strategy: Providing stock options to employees may increase retention.
- Manager-Employee Relationships: Employees with shorter tenures under managers are more likely to leave. Leadership training and mentorship programs can improve retention.
- Satisfaction & Work Culture: Companies should focus on improving work environment satisfaction and fostering strong workplace relationships.
