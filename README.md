# Predicting Sleep Quality from Wearable Multisensor Data
**Course:** COGS 109: Modeling and Data Analysis | UC San Diego  
**Team Members:** Anthony Mitine, Harshatha Prasanna, Yuxing Liu

## Project Overview
Wearable devices provide a non-invasive way to monitor daily activity and rest, but transforming raw physiological data into meaningful health measures remains a complex challenge. This project utilizes the open-source **MMASH (Multilevel Monitoring of Activity and Sleep in Healthy People)** dataset to predict an individual's overall sleep quality based on daytime behaviors.

Because the dataset does not include clinical sleep staging (like REM duration), we engineered a composite **Sleep Quality Score (0-100)** using available metrics such as Total Sleep Time, Latency Efficiency, Wake After Sleep Onset, and Sleep Fragmentation. Using Multiple Linear Regression and Lasso Regularization, we evaluate which daytime physiological features (heart rate, step count, heavy activity duration) hold the strongest predictive power and statistical association with overnight restfulness.

## Repository Structure
* `data/` : Directory containing the 22 user folders from the MMASH dataset (ignored via `.gitignore` to prevent pushing large files).
* `COGS109_Final_Project.ipynb` : The primary Jupyter Notebook containing data aggregation, cleaning, Exploratory Data Analysis (EDA), and regression modeling.

## Dataset
The data is sourced from PhysioNet's **Multilevel Monitoring of Activity and Sleep in Healthy People** (v1.0.0). It includes 24 hours of continuous beat-to-beat heart data, triaxial accelerometry, and sleep logs for 22 healthy participants.
* [MMASH on PhysioNet](https://physionet.org/content/mmash/1.0.0/)

## Methodology Highlights
* **Target Variable Construction:** Custom weighted formula penalizing sleep disruptions while rewarding duration and efficiency.
* **Validation Strategy:** 5-fold cross-validation to ensure model generalizability.
* **Model Selection:** Comparing Baseline Ordinary Least Squares (OLS) against Lasso Regression (L1 Regularization) to handle potential multicollinearity among physical movement features.
