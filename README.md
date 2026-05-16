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

Forecasted Pneumonia Admissions (Winter 2026-2027)

Based on the optimized Random Forest Regressor, the projected pneumonia admissions for children under 5 (U5) during winter 2026-2027 are:

## Forecasted Pneumonia Admissions (Winter 2026-2027)

| Month       | Predicted Admissions (U5) |
|------------|---------------------------|
| Dec 2026   | 382                       |
| Jan 2027   | 403                       |
| Feb 2027   | 434                       |


The forecast shows a gradual increase in admissions as winter progresses, with February predicted to have the highest admissions.

## Key Drivers of Pneumonia Admissions

The most influential factors identified by the model:

- Environmental Factors:
Max_Temp_C: 0.2996 (most influential)
Humidity_Percent: 0.2868
Rainfall_mm: 0.2708

- Seasonal Month Indicators:

| Month       | Importance Score |
|------------|-----------------|
| Month_Dec  | 0.0333          |
| Month_Oct  | 0.0288          |
| Month_Feb  | 0.0254          |
| Month_Nov  | 0.0243          |
| Month_Mar  | 0.0127          |
| Month_Sep  | 0.0113          |
| Month_Jun  | 0.0069          |


**Interpretation:** Environmental conditions—maximum temperature, humidity, and rainfall—drive pneumonia admissions, while specific months highlight seasonal peaks.

## Implications for Public Health
Seasonal Preparedness: Focus preventive measures and resources in December, January, and February.
Environmental Monitoring: Track temperature, humidity, and rainfall to anticipate admissions peaks.
Guidance for Planning: Because the model’s R² is low, predictions are indicative, not definitive.
Future Improvements: Integrate richer datasets and advanced models for better accuracy.

### Transparency & Disclosure
- AI usage: 15%


