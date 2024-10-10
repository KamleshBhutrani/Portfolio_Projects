# Used Car Price Prediction Model

## Overview

This project aims to predict the prices of used cars using machine learning models based on a range of features such as car specifications, performance metrics, and physical dimensions. The goal is to create a robust model capable of accurately estimating the resale value of a car based on historical data and engineered features.

## Process Overview

### 1. Data Cleaning and Preprocessing
The raw dataset underwent extensive cleaning and preprocessing, which included:
- **Handling Missing Values**: Imputed missing data in key columns to ensure there are no critical gaps affecting model performance.
- **Text Removal**: Cleaned columns such as seating arrangement (`e.g., "5 seats"`) and fuel tank volume (`e.g., "15 gal"`) to remove non-numeric characters.
- **Normalization and Standardization**: Applied to certain numeric columns to ensure consistent data scaling across the dataset.

### 2. Feature Engineering
Several new features were created to enrich the dataset and improve the model's predictive capability:
- **`avg_fuel_economy`**: Calculated as the average of city and highway fuel economy values.
- **`hp_x_engine_displacement`**: A product of horsepower and engine displacement, capturing the engine's power relative to its size.
- **`total_leg_room`**: Summed the front and back legroom to represent overall passenger space.
- **`volume`**: Created by multiplying height, width, and length to reflect the car’s total size.
- **Categorical Bucketing**: 
    - **Engine Displacement Buckets**
    - **Mileage Buckets**
    - **Horsepower Buckets**
- **`hp_ratio_engine_disp`**: Ratio between horsepower and engine displacement to measure engine efficiency.
- **`fuel_x_engine_disp`** and **`fuel_x_mileage`**: Interaction terms capturing fuel efficiency across engine sizes and mileage.

### 3. Model Building and Comparison
The following four machine learning models were implemented and evaluated:
- **Random Forest**
- **XGBoost**
- **LightGBM**
- **CatBoost**

After training, the models were compared using the following metrics:
- **R-Squared (R²)**: To assess how well the model explains variance in the used car prices.
- **Mean Squared Error (MSE)**: To measure the average squared difference between predicted and actual prices.

### 4. Model Stacking
To enhance accuracy, model stacking was used. Stacking combines predictions from multiple models into a meta-model that leverages the strengths of each base model, improving overall prediction accuracy.

### 5. Model Evaluation
The models were evaluated on the test set using the following metrics:
- **R-Squared (R²)**: Assesses the proportion of the variance in the dependent variable that is predictable from the independent variables.
- **Mean Squared Error (MSE)**: Measures the average squared difference between the predicted and actual prices.

### 6. Insights from the Analysis
- **Feature Importance**: Features such as engine displacement, mileage, and horsepower were found to have a significant impact on the model's performance.
- **Impact of Mileage and Age**: Higher mileage and older cars saw greater depreciation, which was captured by the model.
- **Interaction Effects**: Interaction features such as horsepower-to-engine displacement ratio improved prediction accuracy by capturing vehicle efficiency.

## Conclusion
This project demonstrates how machine learning models can be applied to predict used car prices with a high degree of accuracy. Through the use of advanced models such as XGBoost, LightGBM, CatBoost, and Random Forest, combined with feature engineering and model stacking, the project achieves strong predictive performance.

