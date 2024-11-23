# mlfs-book
O'Reilly book - Building Machine Learning Systems with a feature store: batch, real-time, and LLMs


## ML System Examples


[Dashboards for Example ML Systems](https://featurestorebook.github.io/mlfs-book/)

## Course Comparison

| Course                         | MLOps | LLLMs             | Feature/Training/Inference | Working AI Systems | Focus |
|--------------------------------|-------|----------------------------|--------------------|------------------|
| Building AI Systems (O'Reilly) | Yes   | Fine-Tuning & RAG | Yes                        | High               | Project-based, Software Engineering, Fundamentals    |
| [Made With ML](https://madewithml.com/)                   | No          | Yes   | No                         | No                 | Software Engineering, Model Training   |
| [7 Steps MLOps](https://www.pauliusztin.me/courses/the-full-stack-7-steps-mlops-framework)            | Yes   | Separate Course    | Yes                        | Low                | Learning Tools and Project    |


# **Air Quality Prediction System for ID2223**

### **Lab 1 - Serverless AI System for Air Quality Prediction**

This project is part of the ID2223 Machine Learning course at KTH for HT2024. The goal of the lab is to build a serverless AI system that predicts air quality (PM2.5) for a specified location, using Hopsworks, feature engineering, and machine learning model development.

### **Overview**

The objective of this lab is to create a serverless AI system to predict air quality levels at specific locations using machine learning. The system takes air quality and weather data, creates feature groups in Hopsworks, trains a machine learning model, and visualizes the results on Hopsworks.

This project uses the following data sources:
- **Air Quality Data** from [AQICN](https://aqicn.org)
- **Weather Data** from [Open-Meteo](https://open-meteo.com)

The complete workflow includes data loading, feature engineering, training a model, making batch predictions, and visualization of results.

### **Architecture**

1. **Data and Feature Engineering**:
   - **Daily Feature Pipeline**: Automatically gets daily weather and air quality data and stores them as Feature Groups in the Hopsworks Feature Store.
   - **Backfill Pipeline**: Backfills historical data from the selected sensor to create a large dataset.

2. **Model Training**:
   - A regression model (`XGBRegressor`) is trained using weather and air quality features to predict PM2.5 levels.
   - Features are extracted from a Feature View created in the Hopsworks platform.

3. **Batch Inference**:
   - The trained model is used to predict PM2.5 levels for the next 7-10 days using weather forecast data.
   - The results are visualized using a dashboard.

### **Components**

This project is divided into several main components:
1. **Data handling**
 Downloads and processes historical air quality and weather data.
 Runs daily to get new data from AQICN and Open-Meteo.

2. **Model Training Pipeline**:
 Trains a machine learning model to predict PM2.5 levels based on features from air quality and weather data.

3. **Batch Inference:
   Runs predictions on new data and saves the results for visualization.
   A public dashboard visualizing air quality predictions for a selected location.

### **Setup Instructions**

To set up and run the system, please follow the steps below:

#### **Prerequisites**
- A **Hopsworks** account at [hopsworks.ai](https://app.hopsworks.ai).
- A **GitHub** account to manage the code.


### **Results**

- The trained model is capable of predicting PM2.5 levels based on weather conditions and historical air quality data.
- The model performance is evaluated using metrics like Mean Squared Error (MSE)
- **Hindcast Graphs** are provided to show prediction performance compared to observed values.
