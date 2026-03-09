# Loan Status Analysis: Exploring Approval Patterns

🏦 Dive into the patterns of loan approvals with this comprehensive analysis. This project investigates the various factors influencing loan approval status, offering insights into how attributes like gender, marital status, dependents, education, self-employment, income, loan amount, loan term, credit history, and property area contribute to the approval decision.

---

## Introduction

This project focuses on analyzing a dataset of loan applications to understand the factors affecting loan approval status. By examining various attributes such as applicant details, income, loan amount, credit history, and property area, the analysis aims to uncover trends, disparities, and insights in loan approval patterns.

---

## Dataset Description

The dataset comprises 381 rows and 13 columns, each representing different attributes related to loan applications.

| #   | Column                | Description                                                 |
| --- | --------------------- | ----------------------------------------------------------- |
| 1   | **Loan_ID**           | A unique loan ID                                            |
| 2   | **Gender**            | Gender of the applicant (Male/Female)                       |
| 3   | **Married**           | Marital status of the applicant (Yes/No)                    |
| 4   | **Dependents**        | Number of dependents of the applicant                       |
| 5   | **Education**         | Education level (Graduate/Not Graduate)                     |
| 6   | **Self_Employed**     | Whether the applicant is self-employed (Yes/No)             |
| 7   | **ApplicantIncome**   | Income of the applicant                                     |
| 8   | **CoapplicantIncome** | Income of the co-applicant                                  |
| 9   | **LoanAmount**        | Loan amount in thousands                                    |
| 10  | **Loan_Amount_Term**  | Term of the loan in months                                  |
| 11  | **Credit_History**    | Credit history (1: meets guidelines, 0: does not meet)      |
| 12  | **Property_Area**     | Area where the property is located (Urban/Semi-urban/Rural) |
| 13  | **Loan_Status**       | Loan approved (Y/N)                                         |

### Data Quality

- **Missing Values**: Some missing values exist in Gender, Dependents, Self_Employed, Loan_Amount_Term, and Credit_History.
- **Duplicates**: No duplicate values found.
- **RangeIndex**: 381 entries.
- **Data Types**: 4 float columns, 1 integer column, and 8 object columns.

---

## Analysis Steps

### Step 1 | Python Libraries

Setting up the environment with required libraries and configurations.

### Step 2 | Preparing the Dataset

Loading the data and performing an initial overview of attributes and data types.

![Status Check](loan_charts/status_check.png)

### Step 3 | Data Preprocessing

**3.1 | Columns Formatting**

**3.2 | Missing Value Handling**

Identifying and addressing missing values across key columns.

![Missing Values Heatmap](loan_charts/missing_value.png)

**3.3 | Duplicate Value Management**

**3.4 | Statistical Data Summary**

---

### Step 4 | Exploratory Data Analysis

**4.1 | Individual Variables Analysis**

Exploring the distribution of each categorical and continuous variable.

![Loan Status Distribution](loan_charts/loan_status_distribution.png)

![Categorical Variable Distributions](loan_charts/barchart_category_data.png)

Breakdown of key demographic variables:

|                                                              |                                                                |
| ------------------------------------------------------------ | -------------------------------------------------------------- |
| ![Gender](loan_charts/gender_distribution.png)               | ![Married](loan_charts/married_distribution.png)               |
| ![Dependents](loan_charts/dependents_distribution.png)       | ![Education](loan_charts/education_distribution.png)           |
| ![Self Employed](loan_charts/self_employed_distribution.png) | ![Credit History](loan_charts/credit-history_distribution.png) |
| ![Property Area](loan_charts/property_distribution.png)      |                                                                |

Continuous variable distributions:

![Histogram – Continuous Data](loan_charts/histogram_continous_data.png)

![KDE – Continuous Data](loan_charts/kde_continous_data.png)

**4.2 | Outlier Identification**

![Box Plot](loan_charts/box-plot.png)

**4.3 | Handling Outliers**

**4.4 | Pairs of Variables Insights**

![Box and Scatter](loan_charts/box_and_scatter.png)

![Violin Plot](loan_charts/violin_plot.png)

![Violin Plot – Binary](loan_charts/violin_plot_binary.png)

**4.5 | Multiple Variables Examination**

![Correlation Heatmap](loan_charts/correlation.png)

![Regression Plot](loan_charts/regplot.png)

![Pair Plot](loan_charts/pairplot.png)

---

### Step 5 | Hypothesis Testing

**5.1 | Chi-squared Test** — Testing independence between categorical variables and loan status.

**5.2 | Z-test** — Comparing group means for continuous variables against loan approval outcomes.

---

### Step 6 | Model Development & Evaluation

**6.1 | Data Normalization**

**6.2 | Feature Encoding**

**6.3 | Feature Selection**

![Feature Importance](loan_charts/feature_importance.png)

![Feature Selection](loan_charts/feature_selection.png)

**6.4 | Model Preparation**

![Train/Test Data Split](loan_charts/train_test_data.png)

**6.5 | KNeighborsClassifier**

![Overfit/Underfit Analysis – KNN](loan_charts/overfit_undefit.png)

![Confusion Matrix – KNN](loan_charts/confusion_matrix_knn.png)

**6.6 | DecisionTreeClassifier**

![Confusion Matrix – Decision Tree](loan_charts/confusion_matrix_dtree.png)

**6.7 | Gaussian Naïve Bayes**

![Confusion Matrix – Gaussian NB](loan_charts/confusion_matrix_gnb.png)

**6.8 | RandomForestClassifier**

![Confusion Matrix – Random Forest](loan_charts/confusion_matrix_rf.png)

**6.9 | Best Model Result**

![Best Model Result](loan_charts/Best%20Model%20Result.png)

---

## How to Use This Repository

1. **Clone the Repository**: `git clone https://github.com/msjahid/Loan-Status-Analysis.git`
2. **Navigate to the Project Directory**: `cd Loan-Status-Analysis`
3. **Explore the Data**: The dataset is available in the `data` folder. Load and explore it using your preferred data analysis tools.
4. **Run the Analysis**: Use the provided Jupyter notebooks to perform analyses and visualize the findings.

---

## Contributing

Contributions are welcome! Please fork the repository and create a pull request with your changes. For major changes, please open an issue first to discuss what you would like to change.

---

## Contact

If you have any questions or suggestions, feel free to reach out at [ms_jahid@yahoo.com].
