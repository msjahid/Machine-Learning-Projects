# Diabetes Risk Analysis: Pima Indians Exploration 🩸💉

Explore the factors influencing diabetes risk with this comprehensive analysis of the Pima Indians Diabetes dataset. This project investigates various attributes related to diabetes risk and uses machine learning models to predict diabetes status.

---

## Introduction

This project focuses on analyzing a dataset of Pima Indians to understand the risk factors associated with diabetes. By examining various attributes such as glucose levels, BMI, insulin, and age, the analysis aims to uncover trends, correlations, and insights into diabetes risk.

---

## Dataset Description

The dataset comprises 768 rows and 9 columns, each representing different attributes related to diabetes risk.

| #   | Column                       | Description                                                       |
| --- | ---------------------------- | ----------------------------------------------------------------- |
| 1   | **Pregnancies**              | Number of pregnancies the individual has had                      |
| 2   | **Glucose**                  | Plasma glucose concentration (2-hour oral glucose tolerance test) |
| 3   | **BloodPressure**            | Diastolic blood pressure (mm Hg)                                  |
| 4   | **SkinThickness**            | Triceps skin fold thickness (mm)                                  |
| 5   | **Insulin**                  | 2-hour serum insulin (mu U/ml)                                    |
| 6   | **BMI**                      | Body mass index (weight in kg / height in m²)                     |
| 7   | **DiabetesPedigreeFunction** | Likelihood of diabetes based on family history                    |
| 8   | **Age**                      | Age of the individual in years                                    |
| 9   | **Outcome**                  | Diabetes status: 1 = diabetic, 0 = non-diabetic                   |

### Data Quality

- **Missing Values**: The dataset contains no missing values.
- **Duplicates**: The dataset contains no duplicate values.
- **RangeIndex**: The dataset includes 768 entries.
- **Data Types**: 7 integer columns and 2 float columns.

---

## Analysis Steps

### Step 1 | Python Libraries

Setting up the environment with required libraries and configurations.

### Step 2 | Preparing the Dataset

Loading data, confirming structure, and performing initial quality checks.

### Step 3 | Data Preprocessing

**3.1 | Columns Formatting**

**3.2 | Statistical Data Summary**

**3.3 | Individual Variable Summary**

---

### Step 4 | Exploratory Data Analysis

**4.1 | Individual Variables Analysis**

Histograms with density curves for all 8 features — pregnancies and insulin are heavily right-skewed, while glucose follows a near-normal distribution with a slight right tail (μ = 120.89):

![Histogram – All Features](diabetes_charts/hist_plot.png)

KDE curves show blood pressure is unimodal and symmetric, while skin thickness and insulin have clear bimodal shapes suggesting zero-value clusters in the data:

![KDE – All Features](diabetes_charts/kde_plot.png)

Frequency distributions for the two categorical-style variables confirm a class imbalance: 65.1% non-diabetic vs 34.9% diabetic:

![Categorical Distribution – Pregnancies & Outcome](diabetes_charts/plot_categorical_distribution.png)

**4.2 | Pairs of Variables Insights**

Bar + KDE comparisons of each feature split by outcome show that diabetic individuals (outcome = 1) consistently have higher mean glucose (141 vs 110), higher BMI (35.1 vs 30.3), and are older (37.1 vs 31.2):

![Continuous Features vs Target](diabetes_charts/plot_continuous_vs_target.png)

Grouped count charts comparing feature values against outcome — Pregnancies, Blood Pressure, Skin Thickness, and Age all show visible distributional shifts between diabetic and non-diabetic groups:

![Count Data by Outcome](diabetes_charts/visualize_count_data.png)

Grouped histograms for binned Glucose, Insulin, BMI, and Diabetes Pedigree Function broken by outcome — higher glucose groups (>25) and higher BMI groups (6–7) skew strongly toward diabetic outcomes:

![Grouped Count Data by Outcome](diabetes_charts/visualize_grouped_count_data.png)

Strip plots of each feature against outcome expose the individual data point spread and confirm that glucose and BMI have the clearest vertical separation between the two classes:

![Strip Plots by Outcome](diabetes_charts/plot_stripplots.png)

Full scatter matrix of all feature pairs colored by outcome — glucose vs BMI and glucose vs age pairings show the clearest class separation:

![Scatter Matrix](diabetes_charts/plot_scatter_matrix.png)

**4.3 | Outlier Identification**

Box plots across all 8 features — insulin has the most severe upper outliers (up to ~850 mu U/ml), while pregnancies and diabetes pedigree function also show significant right-tail spread:

![Boxplots](diabetes_charts/plot_boxplots.png)

**4.4 | Handling Outliers**

After Winsorization, violin plots by outcome for Pregnancies, Blood Pressure, Skin Thickness, and Age show cleaner distributions with the class separation signal preserved:

![Violin Grid by Outcome – Post Winsorization](diabetes_charts/plot_violin_grid.png)

A three-panel view (KDE, box, scatter vs outcome) for each feature after Winsorization confirms tighter distributions while retaining meaningful between-group differences:

![Numeric Data After Winsorization](diabetes_charts/visualize_numeric_data.png)

**4.5 | Multiple Variables Examination**

Full pairplot of all 8 features colored by outcome — diagonal KDE plots show that glucose and BMI have the most distinct separation between diabetic and non-diabetic distributions:

![Pairplot](diabetes_charts/pairplot.png)

**4.6 | Correlation Analysis**

A triangular lower-half correlation matrix highlights the strongest pairings: Skin Thickness and Insulin (0.51), Age and Pregnancies (0.58), and Glucose and Outcome (0.49):

![Correlation Heatmap – Lower Triangle](diabetes_charts/plot_corr_heatmap_single.png)

The full symmetric heatmap confirms the same findings across all feature pairs, with Glucose showing the highest correlation with Outcome at 0.49:

![Correlation Heatmap – Full](diabetes_charts/plot_correlation_heatmap.png)

Regression scatter plots of each normalized feature against Outcome — Glucose shows the steepest positive slope, while Blood Pressure and Pregnancies show much weaker trends:

![Scatter with Regression Lines](diabetes_charts/plot_scatter_with_regression.png)

**4.7 | Hypothesis Testing with Z-test**

Z-tests confirm that mean differences between diabetic and non-diabetic groups are statistically significant for Glucose, BMI, and Age.

---

### Step 5 | Model Development & Evaluation

**5.1 | Data Normalization**

**5.2 | Feature Selection**

ExtraTreesClassifier ranks Glucose as the dominant feature (importance ≈ 0.25), followed by BMI and Age. Insulin ranks last, reflecting its noisy zero-heavy distribution:

![Feature Importance – All Features](diabetes_charts/features_important.png)

After applying an importance threshold, all 8 features are retained — none fall below the cutoff, confirming that every feature contributes meaningfully to prediction:

![Selected Features Above Threshold](diabetes_charts/selected_features.png)

**5.3 | Model Preparing**

An 80/20 split produces 614 training instances and 154 test instances:

![Train/Test Split Distribution](diabetes_charts/train_test.png)

**5.4 | KNeighborsClassifier**

**5.4.1 | Overfitting and Underfitting in KNN**

Training accuracy starts at 100% (K=1) and falls sharply, while test accuracy rises from 64% — the curves converge around K=25–30, indicating the sweet spot for generalization:

![Overfit/Underfit Detection – KNN](diabetes_charts/overfit_underfit.png)

**5.4.2 | Hyperparameter Tuning**

Grid search over K values to find the optimal number of neighbors balancing bias and variance.

**5.4.3 | Confusion Matrix for KNN**

![Confusion Matrix – KNN](diabetes_charts/knn_confusion.png)

**5.5 | DecisionTreeClassifier**

**5.5.1 | Decision Tree Plot**

The tree first splits on Glucose (≤ 0.213), then branches on Age, BMI, and Blood Pressure — visually confirming the feature importance ranking:

![Decision Tree Plot](diabetes_charts/decsion_tree.png)

**5.5.2 | Parameter Tuning for Decision Tree**

![Confusion Matrix – Decision Tree](diabetes_charts/dt_matrix.png)

**5.6 | Naïve Bayes**

![Confusion Matrix – Gaussian Naïve Bayes](diabetes_charts/gnb_matrix.png)

**5.7 | RandomForestClassifier**

**5.7.1 | Parameter Tuning for Random Forest**

![Confusion Matrix – Random Forest](diabetes_charts/rf_matrix.png)

**5.8 | Support Vector Machine**

**5.8.1 | Parameter Tuning for SVM**

![Confusion Matrix – SVM](diabetes_charts/svm_matrix.png)

**5.9 | Best Model Result**

Decision Tree leads on test accuracy at 79.22%, narrowly beating KNN (77.92%). Random Forest scores 75.32% despite the highest training accuracy (88.27%), indicating mild overfitting. Gaussian Naïve Bayes and SVM both land around 72–74%:

![Best Model Result](diabetes_charts/Best%20Model%20Result.png)

---

## How to Use This Repository

1. **Clone the Repository**: `git clone https://github.com/yourusername/Diabetes-Risk-Analysis.git`
2. **Navigate to the Project Directory**: `cd Diabetes-Risk-Analysis`
3. **Explore the Data**: The dataset is available in the `diabetes_data` folder. Load and explore it using your preferred data analysis tools.
4. **Run the Analysis**: Use the provided Jupyter notebooks to perform analyses and visualize the findings.

---

## Contributing

Contributions are welcome! Please fork the repository and create a pull request with your changes. For major changes, please open an issue first to discuss what you would like to change.

---

## Contact

If you have any questions or suggestions, feel free to reach out at [ms_jahid@yahoo.com].
