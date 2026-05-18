# Regression Analysis Lab – California Housing Dataset

## Overview

This project performs regression analysis using the California Housing dataset.  
The main goal is to predict house prices based on different housing-related features.

The project includes data exploration, preprocessing, visualization, regression model training, model evaluation, and result interpretation.

---

## Dataset

The dataset used in this lab is the California Housing Prices dataset.

Target variable:

`median_house_value`

This column represents the house price that the models try to predict.

---

## Cell 1 – Importing Libraries

This cell imports all necessary Python libraries.

It includes:

- `pandas` for working with data tables
- `numpy` for numerical operations
- `matplotlib` and `seaborn` for visualizations
- `sklearn` libraries for machine learning models, preprocessing, splitting data, and evaluation metrics

---

## Cell 2 – Loading the Dataset

This cell loads the dataset using:

`pd.read_csv("housing.csv")`

Then, `df.head()` displays the first five rows of the dataset.

This helps to quickly check if the dataset was loaded correctly.

---

## Cell 3 – Dataset Information

This cell uses:

`df.info()`

It shows:

- Number of rows and columns
- Column names
- Data types
- Missing values
- Memory usage

This helps understand the structure of the dataset.

---

## Cell 4 – Checking Missing Values

This cell checks missing values using:

`df.isnull().sum()`

It shows how many missing values exist in each column.

In this dataset, the `total_bedrooms` column usually contains missing values.

---

## Cell 5 – Descriptive Statistics

This cell uses:

`df.describe()`

It displays statistical information such as:

- Mean
- Minimum value
- Maximum value
- Standard deviation
- Quartiles

This helps understand the range and distribution of numerical columns.

---

## Cell 6 – Handling Missing Values

This cell fills missing values in the `total_bedrooms` column using the median value.

The median is used because it is less affected by extreme values compared to the mean.

---

## Cell 7 – Encoding Categorical Data

This cell converts the categorical column `ocean_proximity` into numerical values.

Machine learning models cannot directly work with text values, so categorical data must be converted into numbers.

`pd.get_dummies()` is used for this step.

---

## Cell 8 – Separating Features and Target

This cell separates the dataset into:

- `X` – input features
- `y` – target variable

The target variable is:

`median_house_value`

This is the value the models will predict.

---

## Cell 9 – Feature Scaling

This cell standardizes the feature values using `StandardScaler`.

Scaling is important because some features have very different ranges.

For example, population and longitude have different scales, so standardization helps models work more effectively.

---

## Cell 10 – Histogram Visualization

This cell creates histograms for numerical columns.

Histograms help show how each variable is distributed.

They are useful for identifying skewed data, unusual patterns, and possible outliers.

---

## Cell 11 – Boxplot Visualization

This cell creates boxplots for the dataset.

Boxplots are useful for detecting outliers and comparing the spread of different features.

---

## Cell 12 – Correlation Matrix

This cell creates a correlation heatmap.

The correlation matrix shows relationships between variables.

It helps identify which features are strongly related to the target variable and whether multicollinearity may exist.

---

## Cell 13 – Splitting the Dataset

This cell splits the dataset into training and testing sets.

The training set is used to train the models.

The testing set is used to evaluate model performance on unseen data.

The dataset is split as:

- 80% training data
- 20% testing data

---

## Cell 14 – Linear Regression Model

This cell creates and trains a Linear Regression model.

Linear Regression tries to find a straight-line relationship between input features and the target value.

After training, the model predicts house prices using the test data.

---

## Cell 15 – Polynomial Regression Model

This cell applies Polynomial Regression.

Polynomial Regression can capture more complex nonlinear relationships compared to simple Linear Regression.

Polynomial features are created first, and then Linear Regression is applied to those transformed features.

---

## Cell 16 – Decision Tree Regression Model

This cell trains a Decision Tree Regressor.

Decision Trees split the dataset into smaller parts and make predictions based on decision rules.

This model can capture nonlinear relationships but may overfit if not controlled.

---

## Cell 17 – Random Forest Regression Model

This cell trains a Random Forest Regressor.

Random Forest uses many decision trees together and combines their results.

It usually performs better than a single Decision Tree because it reduces overfitting and improves prediction stability.

---

## Cell 18 – Model Evaluation Function

This cell defines a function to evaluate model performance.

The function calculates:

- MAE – Mean Absolute Error
- MSE – Mean Squared Error
- R² Score

These metrics help compare how accurate each model is.

---

## Cell 19 – Evaluating All Models

This cell evaluates all regression models using the test data.

The models evaluated are:

- Linear Regression
- Polynomial Regression
- Decision Tree Regression
- Random Forest Regression

The results show which model performs better.

---

## Cell 20 – Model Comparison Table

This cell creates a table comparing the models.

The table includes the R² Score for each model.

A higher R² Score means the model explains more variation in the target variable.

---

## Cell 21 – Actual vs Predicted Plot

This cell creates a scatter plot comparing actual house prices with predicted house prices.

If the points are close to a straight diagonal pattern, it means the model predictions are close to the real values.

---

## Cell 22 – Residual Distribution

This cell calculates residuals.

Residuals are the differences between actual values and predicted values.

The histogram shows how prediction errors are distributed.

A good model should have residuals mostly centered around zero.



## Final Result

After comparing all models, Random Forest Regression performed the best.

It achieved a strong R² Score and produced better predictions compared to the other models.

---

## Conclusion

This lab demonstrated the full process of regression analysis.  
The dataset was loaded, explored, cleaned, preprocessed, and visualized.  
Several regression models were trained and evaluated using standard performance metrics.

The Random Forest Regression model provided the best overall performance because it handled nonlinear relationships better and reduced overfitting compared to a single Decision Tree.

Overall, this project improved practical understanding of data preprocessing, regression modeling, model evaluation, and machine learning visualization.
