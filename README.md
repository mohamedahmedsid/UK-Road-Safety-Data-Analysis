# UK Road Safety Data Analysis for Predicting Accident Severity

## Overview

This repository contains an end-to-end exploratory and predictive analysis of UK road safety data. The objective is to forecast accident severity using vehicle characteristics and environmental factors so a car manufacturer can spot potential design weaknesses and improve safety features.

Data is sourced from the [UK Department for Transport road safety dataset](https://data.gov.uk/dataset/cb7ae6f0-4be6-4935-9277-47e5ce24a11f/road-safety-data), which records accidents, involved vehicles, and the conditions in which the incidents occurred. Key predictors include vehicle type, engine capacity, maneuver, first point of impact, and road surface conditions.

## Project Structure

- `Data preprocessing.ipynb`: Cleans, merges, and prepares the accidents, vehicles, and casualties data for analysis.
- `Model.ipynb`: Develops and evaluates predictive models for accident severity.

## Methodology

### Exploratory Data Analysis

- **Accident severity distribution**: Most incidents are minor, with fewer serious and fatal cases.
- **Vehicle type frequency**: Cars dominate the dataset, followed by motorcycles and heavy vehicles.
- **Road surface conditions**: Accidents occur mainly on dry surfaces, with fewer incidents on wet or icy roads.
- **Correlation and pair plots**: Vehicle type, road conditions, and maneuver show moderate relationships with accident severity; pair plots highlight potential non-linear effects for variables such as engine capacity.

### Data Preparation

- **Merging datasets**: Combined accident, vehicle, and casualty tables on shared identifiers to create a unified modeling table.
- **Handling missing values**: Mean imputation for numeric fields and mode imputation for categorical fields.
- **Outlier treatment**: Identified and removed extreme values (notably in engine capacity and severity) to reduce skew.
- **Feature scaling**: Standardized continuous variables (e.g., engine capacity, speed) to balance model influence.
- **Feature engineering**: Added interaction terms, such as vehicle maneuver × road surface condition, to capture compound effects.

### Modeling

- **Baseline**: Logistic regression predicting severity categories (minor, serious, fatal) achieved ~70% accuracy.
- **Feature selection**: Recursive Feature Elimination prioritized vehicle type, road surface condition, and first point of impact for improved performance.
- **Model tuning**: Random Forest and Gradient Boosting models were grid-searched over tree count and depth parameters.
- **Best performance**: The tuned model reached ~78% accuracy with precision and recall of 0.76 and 0.74, respectively.

### Evaluation

Final models were compared using accuracy, precision/recall/F1, and confusion matrices to understand class-level behavior.

## How to Reproduce

1. **Set up Python**: Create a virtual environment and install dependencies used in the notebooks: `pandas`, `numpy`, `scikit-learn`, `imbalanced-learn`, `matplotlib`, and `seaborn`.
2. **Download data**: Retrieve the raw accident, vehicle, and casualty files from the [UK Department for Transport source](https://data.gov.uk/dataset/cb7ae6f0-4be6-4935-9277-47e5ce24a11f/road-safety-data) and place them in a local data directory (not tracked in this repository).
3. **Run notebooks**:
   - Execute `Data preprocessing.ipynb` to clean and merge the datasets, producing the modeling-ready table.
   - Execute `Model.ipynb` to train, tune, and evaluate the predictive models.

## Conclusion and Next Steps

The project demonstrates that vehicle and environment attributes can meaningfully predict accident severity on the UK road network. Insights from the tuned model can guide safety-focused design changes and operational planning.

Potential enhancements include:

- Incorporating richer behavioral or weather data for finer-grained predictions.
- Exploring deep learning architectures to capture higher-order relationships.
- Deploying the model in a real-time pipeline to inform emergency response and in-vehicle safety systems.
