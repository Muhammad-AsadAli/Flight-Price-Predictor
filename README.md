# ✈️ Flight Price Prediction

## 📌 Overview

This project focuses on analyzing and predicting flight ticket prices using a **Random Forest Regressor**. The dataset contains various flight details such as airline, journey date, departure/arrival times, route, and number of stops. The goal is to uncover patterns that influence pricing and to build a machine learning model capable of accurately predicting fares.

---

## 📊 Dataset

The primary dataset `FlightFare_Dataset.xlsx` contains **10,001 entries** with the following columns:

- **Airline**: Name of the airline (e.g., IndiGo, Air India)
- **Date_of_Journey**: Date of the flight (e.g., 24/03/2019)
- **Source**: Departure city (e.g., Bangalore, Delhi)
- **Destination**: Arrival city (e.g., New Delhi, Cochin)
- **Route**: Route taken by the flight (e.g., BLR → DEL)
- **Dep_Time**: Scheduled departure time (e.g., 22:20)
- **Arrival_Time**: Arrival time at the destination (e.g., 01:10 22 Mar)
- **Duration**: Total flight duration (e.g., 2h 50m)
- **Total_Stops**: Number of stops (e.g., non-stop, 1 stop)
- **Additional_Info**: Additional details like in-flight meals, etc.
- **Price**: Ticket price in INR (target variable)

An **additional unseen dataset** `Unseen_Dataset.xlsx` is used to test the model's predictive performance.

---

## 🧪 Notebook Workflow (`Flight_Price.ipynb`)

The notebook follows these steps:

### 🔹 1. Data Loading
- Loads necessary libraries: `pandas`, `numpy`, `seaborn`, `matplotlib`
- Imports and previews the dataset

### 🔹 2. Data Preprocessing
- Renames columns for consistency
- Extracts date/time features such as:
  - Day, Month of Journey
  - Hours and Minutes from Departure and Arrival times
- Converts `Duration` into total minutes
- Encodes categorical features like Airline, Source, Destination, etc.

### 🔹 3. Model Training
- Trains a **Random Forest Regressor** on the cleaned dataset

### 🔹 4. Predictions on Unseen Data
- Applies the same preprocessing steps on `Unseen_Dataset.xlsx`
- Generates predictions
- Saves the final output to `ModelOutput.xlsx`

### 🔹 5. Model Evaluation
- Splits the original data into training and test sets
- Evaluates using:
  - **R² Score**: ~0.82
  - **Normalized RMSE**: ~0.05

---

## 📈 Results

- **R² Score**: 0.82 → The model explains approximately 82.4% of the variance in ticket prices
- **Normalized RMSE**: 0.05 → Low error relative to the range of flight prices
- **Output File**: `ModelOutput.xlsx` contains predicted prices merged with the unseen test data

---

## ⚙️ Requirements

To run the notebook, install the required libraries:
`pip install pandas numpy seaborn matplotlib scikit-learn openpyxl`
