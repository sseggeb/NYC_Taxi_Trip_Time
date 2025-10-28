# README: NYC Taxi Trip Duration Prediction

---

## Project Overview
This repository contains a **Supervised Learning Project** focused on predicting the duration of yellow taxi trips in New York City (NYC) using publicly available taxi trip record data for a machine learning regression task.

* **Problem:** Predicting **Trip Duration** for NYC yellow taxi trips.
* **Target Variable:** `trip_duration_seconds`.
* **Data Period:** March 2025.
* **GitHub Repository:** `https://github.com/sseggeb/MSDS_5509_Final_Pro.git`

---

## Data Source and Acquisition
The data used in this analysis is the **NYC Yellow Taxi Trip Data** downloaded via the KaggleHub API. Specifically, the project utilizes the Parquet file corresponding to **March 2025 (`yellow_tripdata_2025-03.parquet`)**.

| Data Source | Details |
| :--- | :--- |
| **Dataset Name** | `elemento/nyc-yellow-taxi-trip-data` |
| **File Used** | `yellow_tripdata_2025-03.parquet` |

---

## Exploratory Data Analysis (EDA) and Data Cleaning
The initial dataset contained over **4.1 million rows**. Key steps in data cleaning and preparation included:

* **Handling Missing Values:** Rows with missing values in the `passenger_count` column were dropped, reducing the dataset to **3,228,594 rows** for modeling.
* **Outlier/Anomalies:** Data quality issues, such as negative values in fare columns, were noted for handling.
* **Feature Engineering:** New temporal features (e.g., day of the week, hour of the day) were extracted from pickup and dropoff datetimes, and the **trip duration** in seconds was calculated as the target variable.

---

## Modeling and Evaluation
Two supervised learning regression models were trained and evaluated on the cleaned and engineered dataset:

### Models Used
1.  **Random Forest Regressor**
2.  **Gradient Boosting Machine (GBM) Regressor**

### Performance Metrics
The models were evaluated using:
* **RMSE (Root Mean Square Error)**
* **$R^2$ (R-squared)**

### Final Model Performance

| Model | RMSE | $R^2$ |
| :--- | :--- | :--- |
| **Random Forest** | **312.43** | **0.82** |
| **GBM** | 329.07 | 0.79 |

---

## Conclusion

The **Random Forest model** provided the most accurate predictions for trip duration.

### Key Findings:
* The Random Forest Regressor demonstrated superior performance with a lower **RMSE (312.43)** and a higher **$R^2$ (0.82)** compared to the Gradient Boosting Machine.

### Future Improvements:
* Model performance could potentially be improved by incorporating **external data** such as daily weather conditions or information about special events in the city.
* Further **hyperparameter tuning** of the GBM model is suggested, as it theoretically should be able to outperform the Random Forest model.
