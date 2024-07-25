# Loan Status Analysis: Exploring Approval Patterns

🏦 Dive into the patterns of loan approvals with this comprehensive analysis. This project investigates the various factors influencing loan approval status, offering insights into how attributes like gender, marital status, dependents, education, self-employment, income, loan amount, loan term, credit history, and property area contribute to the approval decision.

## Introduction

This project focuses on analyzing a dataset of loan applications to understand the factors affecting loan approval status. By examining various attributes such as applicant details, income, loan amount, credit history, and property area, the analysis aims to uncover trends, disparities, and insights in loan approval patterns.

## Dataset Description

The dataset comprises 381 rows and 13 columns, each representing different attributes related to loan applications. The columns in the dataset are:

1. **Loan_ID**: A unique loan ID.
2. **Gender**: Gender of the applicant (Male/Female).
3. **Married**: Marital status of the applicant (Yes/No).
4. **Dependents**: Number of dependents of the applicant.
5. **Education**: Education level of the applicant (Graduate/Not Graduate).
6. **Self_Employed**: Whether the applicant is self-employed (Yes/No).
7. **ApplicantIncome**: Income of the applicant.
8. **CoapplicantIncome**: Income of the co-applicant.
9. **LoanAmount**: Loan amount in thousands.
10. **Loan_Amount_Term**: Term of the loan in months.
11. **Credit_History**: Credit history that meets guidelines (1: meets guidelines, 0: does not meet).
12. **Property_Area**: Area where the property is located (Urban/Semi-urban/Rural).
13. **Loan_Status**: Loan approved (Y/N).

### Data Quality

- **Missing Values**: The dataset contains some missing values in columns such as Gender, Dependents, Self_Employed, Loan_Amount_Term, and Credit_History.
- **Duplicates**: The dataset contains no duplicate values.
- **RangeIndex**: The dataset includes 381 entries.
- **Data Types**: The dataset consists of 4 float columns, 1 integer column, and 8 object columns.

## Analysis Steps

### Step 1 | Python Libraries

1.1 | Import Libraries

1.2 | Library configurations

### Step 2 | Preparing the Dataset

2.1 | Loading Data

2.2 | Data Information

2.3 | Attribute Overview

### Step 3 | Data Preprocessing

3.1 | Columns Formatting

3.2 | Missing Value Handling Strategies

3.3 | Duplicate Value Management Techniques

3.4 | Statistical Data Summary

### Step 4 | Exploratory Data Analysis

4.1 | Individual Variables Analysis

4.2 | Data Outlier Identification

4.3 | Handling Data Outliers

4.4 | Pairs of Variables Insights

4.5 | Multiple Variables Examination

### Step 5 | Hypothesis Testing

5.1 | Hypothesis Testing with Chi-squared test

5.2 | Hypothesis Testing with Z-test

### Step 6 | Model Development & Evaluation

6.1 | Data Normalization

6.2 | Feature Encoding

6.3 | Feature Selection

6.4 | Model Preparing

6.5 | KNeighborsClassifier

6.6 | DecisionTreeClassifier

6.7 | Gaussian Naïve Bayes

6.8 | RandomForestClassifier

6.9 | Best Model Result
![Multiple Variables Examination](loan_charts/Best%20Model%20Result.png)

## How to Use This Repository

1. **Clone the Repository**: `git clone https://github.com/yourusername/Loan-Status-Analysis.git`
2. **Navigate to the Project Directory**: `cd Loan-Status-Analysis`
3. **Explore the Data**: The dataset is available in the `data` folder. Load and explore it using your preferred data analysis tools.
4. **Run the Analysis**: Use the provided Jupyter notebooks to perform analyses and visualize the findings.

## Contributing

Contributions are welcome! Please fork the repository and create a pull request with your changes. For major changes, please open an issue first to discuss what you would like to change.

## Contact

If you have any questions or suggestions, please feel free to contact me at [ms_jahid@yahoo.com].
