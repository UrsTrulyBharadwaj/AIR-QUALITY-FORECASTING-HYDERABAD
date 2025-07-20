# AIR-QUALITY-FORECASTING-HYDERABAD
A complete machine learning project to forecast daily PM2.5 pollution levels in Hyderabad using historical air quality and weather data (2019). This project includes data cleaning, exploratory data analysis (EDA), feature engineering, model training using Random Forest, model evaluation, and an optional Flask web app for live predictions.

## ## Datasets Used

We utilized two primary datasets for this project:

- **Air Quality Data** (`city_day.csv`): Contains daily records of various air pollutants (including PM2.5, PM10, NO2, SO2, CO, O3, and more) for major Indian cities, including Hyderabad, for the year 2019.
- **Weather Data** (`combined_output.csv`): Includes daily weather metrics such as temperature, humidity, rainfall, and wind speed, reported by district (Hyderabad in our case) for the same year.

## Merging Process

We filtered both datasets to include only records from Hyderabad during 2019. After handling missing values, we merged the two datasets on the `Date` field to create a unified dataset named **`hyd_merged_2019.csv`**. This new dataset contains daily pollution and weather variables for Hyderabad, serving as the foundation for our exploratory analysis and machine learning models.


## Project Workflow Overview

Step	--             Description
Data Collection	--Air quality (city_day.csv) & weather data (combined_output.csv) for Hyderabad

Data Cleaning & Merging--	Filtered for Hyderabad (2019), handled missing values, merged into a single dataset

Exploratory Data Analysis	-- Visualized trends, distributions, and correlations

Feature Engineering-- 	Created lags, rolling stats, and calendar features

Modeling-- 	Random Forest regression to predict PM2.5

Model Evaluation--	Reported MAE, RMSE, R², and (optional) MAPE

Saving & Deployment-- 	Model exported with joblib, Flask app for predictions

Reporting/Documentation--	This notebook and README drafted for submission

---

## Steps to Reproduce:

1. **Install dependencies:**
    ```
    pip install pandas numpy scikit-learn matplotlib seaborn joblib flask
    ```

2. **Prepare data:**
    - Place `city_day.csv` and `combined_output.csv` in the `data/` folder.
    - Run the notebook up to the "Feature Engineering" step.
    - Output file: `data/hyd_merged_2019.csv`.

3. **Train and evaluate:**
    - Execute modeling cells.  
    - Check metrics: MAE, RMSE, R² (shown in output cells).

4. **Save and deploy model:**
    ```
    import joblib
    joblib.dump(model, 'data/pm25_rf_model_hyd_2019.pkl')
    ```

5. **(Optional) Run Flask web app:**
    - Ensure `app.py`, `templates/index.html`, and the model pickle are in project root.
    - Start app:
      ```
      python app.py
      ```
    - Open browser at http://localhost:5000

---


## Model & Results

- **Best model:** Random Forest Regressor
- **Metrics:**
    - MAE: ~1.56 µg/m³
    - RMSE: ~2.90 µg/m³
    - R² Score: ~0.98
- Key features: lagged PM2.5, rolling averages, calendar & weather variables
- EDA and plots included in the notebook for insight


---

## Author

- BHARADWAJ 
- Internship Project, 2025
