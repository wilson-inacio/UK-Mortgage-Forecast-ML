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
1. **Data Loading & Preprocessing** – Load CSVs, clean column names, convert dates, align monthly data
2. **Feature Engineering** – Create lagged mortgage rates, rolling averages, and other predictive features
3. **Train/Test Split** – Use time-aware split to avoid future data leakage
4. **Baseline Model: Linear Regression** – Simple regression to establish a baseline
5. **Machine Learning Model: Random Forest** – More advanced model to capture non-linear trends
6. **Model Evaluation** – Compare predictions using metrics like MAE, RMSE
7. **Machine Learning Pipeline** - Create a Machine Learning Pipeline that can modularize all the steps taken so far
8. **Model Saving & Inference Function** – Save trained models and create a reusable prediction function
9. **Findings** - Findings and Take-aways
10. **Conclusions and Next Steps** - Conclusion of the project, limitations and future work

## Results and Analysis
For this project three models were compared: a **Naive Model** that predicts next month values from previous month values, a **Linear Regression** used as a baselinbe, since the data exhibits a clear linear trend over time, and a **Random Forest** to test whether a more flexible, non-linear model could improve performance. This second model was also tuned to optimize its hyperparameters and verify performance with the best possible configuration.
**Findings**
- The Linear Regression model improved upon the Naive model by reducing forecasting error by approximately 50%.
- The Linear Regression model captured the main trend effectively and performed comparably to the tuned Random Forest.
- The Random Forest did not significantly outperform Linear Regression, confirming that the relationship in the data is primarily linear.

## Conclusion
This project demonstrates a complete end-to-end machine learning workflow for predicting UK mortgage rates using official economic data. The workflow is modular and can be converted into a production-ready pipeline, supporting financial decisions such as refinancing timing, product pricing, and risk assessment. Both Linear Regression and Random Forest models were implemented to showcase baseline and more advanced modeling approaches.<br>
Linear Regression provides a simple and interpretable model for this dataset, while Random Forest offers no substantial advantage in predictive accuracy. This validates the choice of Linear Regression for this task and highlights the value of using a baseline model for comparison.<br>
The significant improvement of the Linear Regression model of approximately 50% error forecasting reduction compared to a naive baseline also demonstrates that incorporating macroeconomic indicators (Bank Rate and CPIH) alongside lag features substantially improves predictive accuracy.

|Model|2 Year MAE|2 Year RMSE|5 Year MAE|5 Year RMSE|
|-|-|-|-|-|
|Naive Model|0.22|0.36|0.20|0.32|
|Linear Regression|0.11|0.19|0.10|0.17|
|Random Forest|0.24|0.12|0.23|0.13|
|Tuned Random Forest|0.23|0.35|0.23|0.35|
###### Notes:
###### - Lower MAE and RMSE indicate better predictions.
###### - Linear Regression outperforms Random Forest on both targets, confirming the linear trend in the data.

## Licences
This project is released under the MIT License.
