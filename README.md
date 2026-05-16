## Predicting Monthly Pneumonia Admissions in Under-5 Children in Bangladesh this winter
## Overview
This project focuses on forecasting the number of pneumonia admissions for children under 5 years old in Bangladesh during the upcoming winter (Dec 2026 – Feb 2027). Pneumonia is a leading cause of hospitalization among young children, especially during cold months. Accurate predictions help hospitals plan resources, staffing, and preventive healthcare measures.

The dataset spans 10 years (2014–2023) and includes demographic, environmental, and hospital-related features:
- Demographics: District, Gender, Age in months
- Environmental factors: Minimum and maximum temperature, humidity, rainfall, wind speed, air quality index
- Hospital factors: Hospital beds occupied, vaccination coverage
- Seasonal flag: Winter season indicator

Machine learning regression models are applied to forecast admissions, with performance evaluated using MAE, RMSE, and R² metrics.

## Project Goals
- Analyze historical trends in pneumonia admissions during winter months.
- Examine the impact of environmental and hospital-related factors.
- Build predictive models to forecast monthly pneumonia admissions for winter 2026.
- Provide actionable insights for hospitals and public health authorities to improve preparedness.

## Dataset
- Source: Synthetic dataset generated from publicly available health reports for academic purposes.
- Rows: 3120 (monthly records over 10 years, expanded for preprocessing practice)
- Columns: 14, including Month, District, Gender, Age_Months, Pneumonia_Admissions_U5, environmental factors, hospital factors, and Winter_Season_Flag.
- Notes: Some missing and faulty values were intentionally introduced for preprocessing exercises.

## Project Structure
- README.md
- data
- notebooks
- report

## Data Preprocessing
Handle missing values in Humidity_Percent and Rainfall_mm.
Correct faulty values (e.g., Age_Months > 60, invalid districts).
Encode categorical variables (Month, District, Gender).
Scale numerical features as needed.
Optionally, exclude the target variable for preprocessing practice.

## Exploratory Data Analysis (EDA)
- Visualize distribution of pneumonia admissions by month, district, gender, and age.
- Analyze seasonal trends (higher admissions in winter).
- Correlation analysis between features and admissions.
- Visualizations: histograms, boxplots, line plots, heatmaps.

## Feature Selection
- Correlation analysis to check relationships with the target.
- Recursive Feature Elimination (RFE) using Random Forest or Linear Regression.
- SelectKBest with f_regression to pick top predictors.

## Modeling
- Regression algorithms: Linear Regression, Decision Tree, Random Forest, Gradient Boosting, XGBoost, LightGBM
- Train-test split: 70/30
- Hyperparameter tuning: GridSearchCV or RandomizedSearchCV
- Evaluation metrics: MAE, RMSE, R²

## Business Insights
- Identify key drivers: temperature, humidity, AQI, vaccination coverage, hospital beds.
- Forecasting enables hospitals to plan bed allocation, staff, and preventive interventions.
- Policymakers can use predictions to enhance vaccination campaigns and public health measures.

**Ethical Use & Disclaimer**
* The dataset is synthetic for academic purposes.
* This project is for educational use only; predictions should not be used for real medical decisions.
* AI/ML models are supporting tools, not substitutes for expert medical judgment.

## Summary:

### Data Analysis Key Findings

*   **Feature Selection:** The top 10 most relevant features identified for predicting 'Pneumonia\_Admissions\_U5' using `SelectKBest` with `f_regression` are `Max_Temp_C`, `Humidity_Percent`, `Rainfall_mm`, and monthly indicators: `Month_Dec`, `Month_Feb`, `Month_Jun`, `Month_Mar`, `Month_Nov`, `Month_Oct`, and `Month_Sep`.
*   **Data Split:** The dataset was successfully split into training (2496 samples) and testing (624 samples) sets, with each containing 10 features.
*   **Initial Model Performance:**
    *   The **Random Forest Regressor** showed the best initial performance with an MAE of 0.8779 and an R2 score of 0.0166.
    *   Linear Regression had an MAE of 0.9006 and an R2 score of -0.0210.
    *   Decision Tree Regressor had an MAE of 1.0895 and an R2 score of -0.4791.
    *   All models demonstrated very low or negative R2 scores, indicating limited explanatory power.
*   **Model Optimization:**
    *   The **Random Forest Regressor** was selected for optimization using `GridSearchCV`.
    *   Optimal hyperparameters found were `max_depth`: 15, `min_samples_leaf`: 4, `min_samples_split`: 10, and `n_estimators`: 150.
    *   The optimized model achieved a slightly improved R2 score of 0.1694 during cross-validation.
*   **Optimized Model Evaluation:**
    *   The optimized Random Forest Regressor on the test set yielded an MAE of 0.8700, MSE of 1.3385, RMSE of 1.1569, and an R2 Score of 0.0264.
    *   The R2 score of 0.0264 indicates that the model explains only about 2.64% of the variance in pneumonia admissions, suggesting very limited predictive power.
    *   The Mean Absolute Percentage Error (MAPE) for the optimized model was 334.2954%, an extremely high value likely due to the scaling of the target variable.
*   **Predictor Impact:**
    *   `Humidity_Percent` showed a weak positive correlation, while `Max_Temp_C` and `Rainfall_mm` exhibited very weak negative correlations with pneumonia admissions.
    *   **Seasonal patterns** emerged as significant, with `Month_Feb` and `Month_Nov` associated with increased pneumonia admissions, and `Month_Dec`, `Month_Jun`, `Month_Mar`, and `Month_Oct` associated with fewer admissions compared to a baseline.
 


### Insights or Next Steps

*   **Seasonal Preparedness is Crucial:** Public health organizations should focus resources and awareness campaigns on pneumonia prevention and treatment during November and February, as these months show consistent increases in admissions.
*   **Enhance Predictive Power with Additional Data:** Given the current model's low R2 score, future efforts should prioritize integrating a broader range of features, such as socio-economic factors, specific air pollutants, and more granular health data, or exploring dedicated time-series models to better capture temporal dependencies.


### Transparency & Disclosure
- AI usage: 15%


