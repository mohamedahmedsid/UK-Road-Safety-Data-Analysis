# UK Road Safety Data Analysis for Predicting Accident Severity

## Introduction

### Business Objective

The goal of this project is to develop a predictive model that forecasts the severity of road accidents based on various vehicle characteristics and environmental factors. This model is intended to help a car manufacturer identify potential weaknesses in vehicle design, which could lead to more severe accidents. By understanding these factors, the manufacturer can improve vehicle safety features and reduce the likelihood of severe accidents.

### Context

The analysis uses data sourced from the UK Department for Transport's road safety dataset(available in [UK Department for Transport](https://data.gov.uk/dataset/cb7ae6f0-4be6-4935-9277-47e5ce24a11f/road-safety-data). This dataset includes detailed records of road accidents, the vehicles involved, and the conditions under which these accidents occurred. The focus is on predicting the severity of an accident (our target variable) using variables such as vehicle type, engine capacity, vehicle maneuver, the first point of impact, and road surface conditions.

## Descriptive Statistics

## Exploratory Data Analysis

### Univariate Analysis

- **Accident Severity Distribution**: The distribution of accident severity was analyzed, showing that the majority of accidents were minor, with fewer serious and fatal accidents.
- **Vehicle Type Frequency**: Most accidents involved cars, followed by motorcycles and heavy vehicles.
- **Road Surface Conditions**: The majority of accidents occurred on dry surfaces, with a smaller percentage occurring on wet or icy roads.

### Multivariate Analysis

- **Correlation Matrix**: The correlation matrix revealed that vehicle type, road conditions, and maneuver had a moderate correlation with accident severity.
- **Pair Plots**: Pair plots were generated to visualize the relationships between variables such as vehicle type, engine capacity, and accident severity, highlighting potential non-linear relationships.

## Data Preprocessing

### Joining Different Datasets

- **Merging Datasets**: The accidents, vehicles, and casualties datasets were merged based on common identifiers to create a unified dataset. This dataset was used for all subsequent analysis.

### Data Cleaning

- **Handling Missing Values**: Missing values were handled through mean imputation for numerical variables and mode imputation for categorical variables.
- **Outlier Detection and Removal**: Outliers, particularly in engine capacity and accident severity, were detected and removed to prevent them from skewing the results.

### Scaling

- **Feature Scaling**: Continuous variables such as engine capacity and speed were scaled using standardization to ensure that they had equal weight in the modeling process.

### Feature Engineering

- **Creation of New Features**: New features, such as interaction terms between vehicle maneuver and road surface conditions, were created to capture complex relationships that may impact accident severity.

## Baseline Method

A baseline logistic regression model was implemented to establish a performance benchmark.

- **Model Implementation**: The logistic regression model was trained on the preprocessed dataset to predict accident severity (minor, serious, fatal).
- **Baseline Performance**: The baseline model achieved an accuracy of 70%, serving as a reference point for evaluating more complex models.

## Feature Selection

Feature selection was performed to identify the most predictive variables for accident severity.

- **Methodology**: Recursive Feature Elimination (RFE) was used to rank features and select the top predictors, including vehicle type, road surface conditions, and first point of impact.
- **Selected Features**: The final model included these top-ranked features to improve predictive performance.

## Hyperparameter Tuning

Hyperparameter tuning was conducted to optimize the performance of the advanced models.

- **Models Tested**: Random Forest and Gradient Boosting were the primary models tested, with hyperparameters tuned for each.
- **Tuning Process**: Grid Search was used to explore combinations of hyperparameters, such as the number of trees in the forest and the depth of each tree.
- **Best Model Performance**: The best model achieved an accuracy of 78%, with precision and recall scores of 0.76 and 0.74, respectively.

## Model Evaluation

The final model was evaluated on several metrics to ensure robust performance.

- **Accuracy**
- **Precision, Recall, and F1-Score**
- **Confusion Matrix**

## Conclusion and Possible Future Improvements

### Conclusion

This project successfully developed a predictive model for accident severity using the UK road safety dataset. The final model demonstrated strong predictive power and provided valuable insights into the factors contributing to severe accidents. These insights can be used by the car manufacturer to make data-driven improvements to vehicle safety design.

### Future Improvements

- **Incorporating Additional Features**: Future work could involve incorporating more granular data, such as driver behavior or real-time weather conditions, to further enhance model accuracy.
- **Exploring Deep Learning Models**: The use of deep learning techniques, such as neural networks, could be explored to capture more complex patterns in the data.
- **Real-Time Implementation**: Implementing the model in a real-time prediction system for accident severity could provide immediate insights for emergency response teams.
