![Forecasting UK Mortgage Rates](/resources/images/banner.png)
# End-to-End Machine Learning Pipeline for Forecasting UK Mortgage Rates

## Overview
UK mortgage rates directly impact affordability, re-financing decisions, and lender risk management. The objective of this project is to build a machine learning pipeline that forecasts short-term mortgage rate movements to support decisions such as re-financing timing, product pricing, and risk assessment.

The project demonstrates a complete end-to-end workflow from data acquisition to model evaluation and can be converted into a production-ready pipeline.

### Library dependencies
- pandas  
- numpy  
- scikit-learn  
- matplotlib / seaborn  
- joblib (for model saving)  (?)

## Project Objectives
The objectives of this project are to:
- Acquire and validate data from official sources
- Perform feature engineering
- Create time-aware train/validation splits
- Build pipelines for Linear Regression and Random Forest models
- Evaluate model performance
- Save models and create an inference function

## Dataset
The dataset is comprised of four files which were sourced from official UK public institutions, ensuring data quality and reproducibility: [The Bank of England](https://www.bankofengland.co.uk/) and the [Office for National Statistics](https://www.ons.gov.uk/).

|Source|File|Description|
|--|--|--|
|Bank Of England|2y_fixed.csv|Monthly fixed 2-year mortgage rates by LTV|
|Bank Of England|5y_fixed.csv|Monthly fixed 5-year mortgage rates by LTV|
|Bank Of England|BoE_base_rate.csv|Daily Bank of England base rate|
|ONS|Inflation(CPIH).csv|Monthly Consumer Price Index including Housing|

## Notebook Structure
**1. Data Loading & Preprocessing** – Load CSVs, clean column names, convert dates, align monthly data
**2. Feature Engineering** – Create lagged mortgage rates, rolling averages, and other predictive features
**3. Train/Test Split** – Use time-aware split to avoid future data leakage
**4. Baseline Model: Linear Regression** – Simple regression to establish a baseline
**5. ML Model: Random Forest** – More advanced model to capture non-linear trends
**6. Model Evaluation** – Compare predictions using metrics like MAE, RMSE
**7. Model Saving & Inference Function** – Save trained models and create a reusable prediction function

## Conclusion
This project demonstrates a complete end-to-end machine learning workflow for predicting UK mortgage rates using official economic data. The workflow is modular and can be converted into a production-ready pipeline, supporting financial decisions such as refinancing timing, product pricing, and risk assessment. Both Linear Regression and Random Forest models were implemented to showcase baseline and more advanced modeling approaches.

## Licences
This project is released under the MIT License.
