# Iris Diversity: Analysis, Modeling, Prediction

🌸 Dive into the world of Iris flowers with this comprehensive analysis. This project explores the Iris dataset to understand the diversity among different Iris species, develop predictive models, and evaluate their performance.

---

## Introduction

This project focuses on analyzing a dataset of Iris flowers to understand the diversity among different species. By examining various attributes such as sepal length, sepal width, petal length, and petal width, the analysis aims to uncover trends, disparities, and insights into the different Iris species.

---

## Dataset Description

The dataset comprises 150 rows and 6 columns, each representing different attributes related to Iris flowers.

| #   | Column            | Description                                                |
| --- | ----------------- | ---------------------------------------------------------- |
| 1   | **Id**            | A unique identifier for each Iris flower                   |
| 2   | **SepalLengthCm** | Length of the sepals in centimeters                        |
| 3   | **SepalWidthCm**  | Width of the sepals in centimeters                         |
| 4   | **PetalLengthCm** | Length of the petals in centimeters                        |
| 5   | **PetalWidthCm**  | Width of the petals in centimeters                         |
| 6   | **Species**       | Species of the Iris flower (Setosa, Versicolor, Virginica) |

### Data Quality

- **Missing Values**: The dataset contains no missing values.
- **Duplicates**: The dataset contains no duplicate values.
- **RangeIndex**: The dataset includes 150 entries.
- **Data Types**: 4 float columns, 1 integer column, and 1 object column.

---

## Analysis Steps

### Step 1 | Python Libraries

Setting up the environment with required libraries and configurations.

### Step 2 | Preparing the Dataset

Loading the data and performing an initial overview of attributes, data types, and statistical summaries.

### Step 3 | Data Preprocessing

**3.1 | Columns Formatting**

**3.2 | Missing Value Handling**

Confirming data completeness across all columns — zero missing values found.

![Missing Values Heatmap](iris_charts/missing_value.png)

**3.3 | Duplicate Value Management**

---

### Step 4 | Exploratory Data Analysis

**4.1 | Individual Variables Analysis**

The dataset is perfectly balanced — each of the three species accounts for exactly 33.33% of the records.

![Species Distribution](iris_charts/species_distribution.png)

Histogram distributions of the four continuous features, with density curves overlaid:

![Histogram – Continuous Features](iris_charts/hist_plot.png)

KDE curves reveal that petal length and petal width show clear bimodal patterns, indicating strong species separation:

![KDE – Continuous Features](iris_charts/kde_plot.png)

**4.2 | Outlier Identification**

Box plots exposing the spread and outliers across all four features:

![Boxplots](iris_charts/boxplot.png)

**4.3 | Handling Outliers**

After applying Winsorization, KDE plots by species show how each feature separates across Setosa, Versicolor, and Virginica:

![KDE by Species – Post Outlier Treatment](iris_charts/kde_pair-value.png)

Violin plots reinforce the same picture — Setosa is clearly distinct, while Versicolor and Virginica overlap more on sepal features:

![Violin Grid by Species](iris_charts/violin_grid.png)

**4.4 | Pairs of Variables Insights**

Scatter plots of petal and sepal dimensions, colored by species, confirm that petal measurements are the strongest separators:

![Multiple Variable Scatter](iris_charts/multiple_variable_analysis.png)

Violin-boxplot overlays per species and feature, combining distribution shape with quartile summaries:

![Violin Boxplot Grid](iris_charts/plot_violin_boxplots_grid.png)

Outlier analysis using regression plots across all features with species as the grouping variable:

![Outlier Analysis](iris_charts/outlier_analysis.png)

**4.5 | Multiple Variables Examination**

The correlation heatmap shows that petal length and petal width are highly correlated (0.96), and both correlate strongly with sepal length (0.87 and 0.82 respectively):

![Correlation Heatmap](iris_charts/correlation_heatmap.png)

Faceted relplots showing sepal and petal relationships broken out per species:

|                                                   |                                                   |
| ------------------------------------------------- | ------------------------------------------------- |
| ![Relplot – Sepal](iris_charts/relplot_sepal.png) | ![Relplot – Petal](iris_charts/relplot_petal.png) |

Pairplot providing a full cross-feature view with per-species KDE on the diagonal:

![Pairplot](iris_charts/pairplot.png)

**4.6 | Hypothesis Testing with Z-test**

Z-tests were conducted to assess whether mean differences across species for each feature are statistically significant.

---

### Step 5 | Model Development & Evaluation

**5.1 | Feature Selection**

ExtraTreesClassifier feature importances confirm petal width and petal length as the dominant predictors, with sepal features contributing far less:

![Feature Importance](iris_charts/fetaures_selection.png)

**5.2 | Data Normalization**

**5.3 | KNeighborsClassifier**

Overfit/underfit detection across different values of k, with training and testing accuracy tracked:

![Overfit/Underfit Detection – KNN](iris_charts/overfit_underfit.png)

Confusion matrix and classification report — KNN achieves 97% accuracy on the test set:

![Confusion Matrix – KNN](iris_charts/confusion_knn.png)

**5.4 | DecisionTreeClassifier**

![Confusion Matrix – Decision Tree](iris_charts/dt_confusion.png)

**5.5 | Naïve Bayes**

Three Naïve Bayes variants were evaluated — Gaussian, Multinomial, and Bernoulli — all achieving 96.7% accuracy:

|                                                 |                                                 |                                                 |
| ----------------------------------------------- | ----------------------------------------------- | ----------------------------------------------- |
| ![GNB Confusion](iris_charts/gnb_confusion.png) | ![MNB Confusion](iris_charts/mnb_confusion.png) | ![BNB Confusion](iris_charts/BNB_confusion.png) |

All three Naïve Bayes variants scored identically:

![Naïve Bayes Algorithm Scores](iris_charts/nb_all_result.png)

**5.6 | Best Model Result**

KNN and GaussianNB tied for the top spot at 96.7%, with Decision Tree close behind at 93.3%:

![Best Model Result](iris_charts/Best%20Model%20Result.png)

---

## How to Use This Repository

1. **Clone the Repository**: `git clone https://github.com/msjahid/iris_prediction.git`
2. **Navigate to the Project Directory**: `cd iris_prediction`
3. **Explore the Data**: The dataset is available in the `iris_data` folder. Load and explore it using your preferred data analysis tools.
4. **Run the Analysis**: Use the provided Jupyter notebooks to perform analyses and visualize the findings.

---

## Contributing

Contributions are welcome! Please fork the repository and create a pull request with your changes. For major changes, please open an issue first to discuss what you would like to change.

---

## Contact

If you have any questions or suggestions, feel free to reach out at [ms_jahid@yahoo.com].
