# Diabetes Risk Analysis: Pima Indians Exploration 🩸💉

Explore the factors influencing diabetes risk with this comprehensive analysis of the Pima Indians Diabetes dataset. This project investigates various attributes related to diabetes risk and uses machine learning models to predict diabetes status.

## Introduction

This project focuses on analyzing a dataset of Pima Indians to understand the risk factors associated with diabetes. By examining various attributes such as glucose levels, BMI, insulin, and age, the analysis aims to uncover trends, correlations, and insights into diabetes risk.

## Dataset Description

The dataset comprises 768 rows and 9 columns, each representing different attributes related to diabetes risk. The columns in the dataset are:

1. **Pregnancies**: Number of pregnancies the individual has had.
2. **Glucose**: Plasma glucose concentration measured in a 2-hour oral glucose tolerance test.
3. **BloodPressure**: Diastolic blood pressure measurement (mm Hg).
4. **SkinThickness**: Triceps skin fold thickness (mm).
5. **Insulin**: 2-hour serum insulin (mu U/ml).
6. **BMI**: Body mass index, calculated as weight in kg/(height in meters)^2.
7. **DiabetesPedigreeFunction**: A function scoring the likelihood of diabetes based on family history.
8. **Age**: Age of the individual in years.
9. **Outcome**: Target variable, indicating whether the individual has diabetes (1) or not (0).

### Data Quality

- **Missing Values**: The dataset contains no missing values.
- **Duplicates**: The dataset contains no duplicate values.
- **RangeIndex**: The dataset includes 768 entries.
- **Data Types**: The dataset consists of 7 integer columns and 2 float columns.

## Analysis Steps

### Step 1 | Python Libraries

1.1 | Import Libraries

1.2 | Library configurations

### Step 2 | Preparing the Dataset

2.1 | Loading Data

2.2 | Data Information

2.3 | Missing Value Handling Strategies

2.4 | Duplicate Value Management Techniques

2.5 | Attribute Overview

### Step 3 | Data Preprocessing

3.1 | Columns Formatting

3.2 | Statistical Data Summary

3.3 | Individual Variable Summary

### Step 4 | Exploratory Data Analysis

4.1 | Individual Variables Analysis

4.2 | Pairs of Variables Insights

4.3 | Data Outlier Identification

4.4 | Handling Data Outliers

4.5 | Multiple Variables Examination

4.6 | Correlation Analysis

4.7 | Hypothesis Testing with Z-test

### Step 5 | Model Development & Evaluation

5.1 | Data Normalization

5.2 | Feature Selection

5.3 | Model Preparing

5.4 | KNeighborsClassifier

5.4.1 | Overfitting and Underfitting in KNN

5.4.2 | Hyperparameters Tuning Technique of Machine Learning

5.4.2.1 | Parameter Tuning KNN

5.4.3 | Confusion Matrix for KNN

5.5 | DecisionTreeClassifier

5.5.1 | Decision Tree Plot

5.5.2 | Parameter Tuning for Decision Tree

5.6 | Naïve Bayes

5.7 | RandomForestClassifier

5.7.1 | Parameter Tuning for Random Forest

5.8 | Support Vector Machine

5.8.1 | Parameter Tuning for SVM

5.9 | Best Model Result

![Best Model Result](diabetes_charts/Best%20Model%20Result.png)

## How to Use This Repository

1. **Clone the Repository**: `git clone https://github.com/yourusername/Diabetes-Risk-Analysis.git`
2. **Navigate to the Project Directory**: `cd Diabetes-Risk-Analysis`
3. **Explore the Data**: The dataset is available in the `diabetes_data` folder. Load and explore it using your preferred data analysis tools.
4. **Run the Analysis**: Use the provided Jupyter notebooks to perform analyses and visualize the findings.

## Contributing

Contributions are welcome! Please fork the repository and create a pull request with your changes. For major changes, please open an issue first to discuss what you would like to change.

## Contact

If you have any questions or suggestions, please feel free to contact me at [ms_jahid@yahoo.com].
