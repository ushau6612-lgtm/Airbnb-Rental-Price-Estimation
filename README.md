# Airbnb-Rental-Price-Estimation
Airbnb Rental Price Estimation is a machine learning regression project that predicts the nightly rental price of an Airbnb property based on property characteristics, location, room type, guest capacity, bedrooms, bathrooms, reviews, rating, minimum stay requirements, and availability
# Airbnb Rental Price Estimation

## Overview

Airbnb Rental Price Estimation is a machine learning regression project designed to predict the nightly rental price of an Airbnb property.

The model uses information such as location, room type, number of guests, bedrooms, bathrooms, number of reviews, rating, minimum nights, and availability to estimate the price per night.

This project demonstrates a complete machine learning workflow, including data exploration, preprocessing, model training, prediction, evaluation, feature analysis, and visualization.

## Objective

The main objective of this project is to develop a machine learning model that can estimate the nightly rental price of an Airbnb property based on its characteristics.

The project aims to:

* Explore Airbnb listing data
* Understand factors affecting rental prices
* Analyze price differences between room types
* Handle missing values
* Prepare numerical and categorical features
* Train a regression model
* Predict Airbnb rental prices
* Evaluate model performance
* Identify important factors affecting rental prices
* Visualize relationships between listing characteristics and prices

## Dataset

The project uses a synthetic Airbnb listings dataset containing **800 records and 11 columns**.

The dataset is intended for educational and machine learning practice purposes.

### Dataset Features

| Feature           | Description                                           |
| ----------------- | ----------------------------------------------------- |
| listing_id        | Unique identifier for each Airbnb listing             |
| location          | Location of the Airbnb property                       |
| room_type         | Type of accommodation                                 |
| guests            | Maximum number of guests the property can accommodate |
| bedrooms          | Number of bedrooms                                    |
| bathrooms         | Number of bathrooms                                   |
| number_of_reviews | Number of reviews received by the listing             |
| rating            | Average customer rating                               |
| minimum_nights    | Minimum number of nights required for a booking       |
| availability_days | Number of days the property is available              |
| price_per_night   | Nightly rental price                                  |

### Target Variable

`price_per_night`

The `price_per_night` column is the target variable that the machine learning model predicts.

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-learn

## Machine Learning Algorithm

The project uses **Linear Regression** as the machine learning algorithm.

Linear Regression is a supervised learning algorithm used to predict continuous numerical values. In this project, it is used to estimate the nightly rental price of an Airbnb property.

## Features Used

### Numerical Features

The following numerical features are used:

* Guests
* Bedrooms
* Bathrooms
* Number of reviews
* Rating
* Minimum nights
* Availability days

### Categorical Features

The following categorical features are used:

* Location
* Room type

The `listing_id` column is excluded from the model because it is only an identifier and does not provide meaningful predictive information.

## Data Preprocessing

The project performs several preprocessing steps before training the model.

### Missing Value Handling

Missing numerical values are replaced using the median value of the corresponding feature.

Missing categorical values are replaced using the most frequently occurring category.

### Numerical Feature Scaling

Numerical features are standardized using `StandardScaler`.

### Categorical Feature Encoding

Categorical features are converted into numerical values using `OneHotEncoder`.

The encoder uses `handle_unknown="ignore"` to prevent errors when an unseen category appears during prediction.

## Train-Test Split

The dataset is divided into training and testing data.

* 80% training data
* 20% testing data

A `random_state` of 42 is used to make the results reproducible.

## Model Pipeline

A Scikit-learn Pipeline is used to combine preprocessing and model training.

The pipeline consists of:

1. Numerical data imputation
2. Numerical feature standardization
3. Categorical data imputation
4. One-hot encoding
5. Linear Regression

This approach ensures that the same preprocessing operations are consistently applied during both training and prediction.

## Model Evaluation

The model is evaluated using three standard regression metrics.

### Mean Absolute Error

MAE measures the average absolute difference between actual rental prices and predicted rental prices.

A lower MAE indicates better model performance.

### Root Mean Squared Error

RMSE measures the square root of the average squared prediction error.

RMSE gives greater importance to larger prediction errors.

A lower RMSE indicates better prediction performance.

### R² Score

R² Score measures how much of the variation in rental prices is explained by the model.

A higher R² Score generally indicates a better-performing regression model.

## New Airbnb Price Prediction

The project includes an example new Airbnb listing with the following information:

```text
Location: Downtown
Room Type: Entire home
Guests: 4
Bedrooms: 2
Bathrooms: 2
Number of Reviews: 120
Rating: 4.7
Minimum Nights: 2
Availability Days: 200
```

The trained model uses these details to estimate the property's rental price per night.

## Feature Impact Analysis

The project analyzes the coefficients generated by the Linear Regression model.

The regression coefficients are used to understand which processed features have a greater influence on the predicted rental price.

Features are ranked according to their absolute coefficient values to identify the most influential factors.

The program displays the top factors affecting rental price prediction.

## Visualizations

The project generates three visualization files.

### 1. Guests vs Price

File:

```text
guests_vs_price.png
```

This scatter plot shows the relationship between the number of guests a property can accommodate and its nightly rental price.

### 2. Actual vs Predicted Prices

File:

```text
actual_vs_predicted.png
```

This scatter plot compares the actual rental prices from the testing dataset with the prices predicted by the Linear Regression model.

### 3. Room Type Price Comparison

File:

```text
room_type_price.png
```

This bar chart compares the average nightly rental price across different room types.

## Project Structure

```text
Airbnb_Rental_Price_Estimation/
│
├── README.md
├── airbnb_rental_price_estimation.py
├── airbnb_listings.csv
├── requirements.txt
│
├── guests_vs_price.png
├── actual_vs_predicted.png
└── room_type_price.png
```

The PNG visualization files are generated when the Python program is executed.

## Installation

Make sure Python is installed on your computer.

Install the required dependencies using:

```bash
pip install -r requirements.txt
```

## Requirements

The project requires the following Python libraries:

```text
pandas
numpy
matplotlib
scikit-learn
```

## How to Run

Open a terminal or command prompt in the project directory.

Install the required packages:

```bash
pip install -r requirements.txt
```

Run the Python script:

```bash
python airbnb_rental_price_estimation.py
```

The program will:

1. Load the Airbnb dataset.
2. Display the first five records.
3. Display the dataset shape.
4. Check for missing values.
5. Prepare numerical and categorical features.
6. Handle missing values.
7. Standardize numerical features.
8. Encode categorical features.
9. Split the dataset into training and testing sets.
10. Train the Linear Regression model.
11. Generate rental price predictions.
12. Calculate MAE, RMSE, and R² Score.
13. Display actual and predicted prices.
14. Predict the price of a new Airbnb listing.
15. Analyze important factors affecting rental prices.
16. Generate visualization files.

## Machine Learning Workflow

```text
Airbnb Dataset
      |
      v
Data Loading
      |
      v
Data Exploration
      |
      v
Missing Value Analysis
      |
      v
Feature Selection
      |
      +-----------------------+
      |                       |
      v                       v
Numerical Features      Categorical Features
      |                       |
      v                       v
Median Imputation      Most Frequent Imputation
      |                       |
      v                       v
StandardScaler         One-Hot Encoding
      |                       |
      +-----------+-----------+
                  |
                  v
           Train-Test Split
                  |
                  v
          Linear Regression
                  |
                  v
             Prediction
                  |
                  v
           Model Evaluation
                  |
        +---------+---------+
        |         |         |
        v         v         v
       MAE       RMSE       R²
                  |
                  v
       Feature Impact Analysis
                  |
                  v
           Data Visualization
```

## Key Learning Outcomes

This project provides practical experience with:

* Regression-based machine learning
* Airbnb rental price prediction
* Data exploration
* Data cleaning
* Missing-value handling
* Numerical feature scaling
* Categorical feature encoding
* One-hot encoding
* Scikit-learn pipelines
* Linear Regression
* Train-test splitting
* Model evaluation
* Regression coefficient analysis
* Data visualization
* Predicting values for new data

## Limitations

The project uses a synthetic dataset and a Linear Regression model. Real-world Airbnb rental prices can depend on many additional factors, including exact location, seasonal demand, local events, property quality, amenities, host reputation, booking demand, competition, and market conditions.

Therefore, the predictions should be considered estimates for educational purposes rather than actual market prices.

## Dataset Disclaimer

The included Airbnb dataset is synthetic and intended for educational and classroom machine learning practice.

It does not contain real Airbnb listing records or actual Airbnb customer information.

## Conclusion

This project demonstrates how machine learning can be used to estimate Airbnb rental prices from property characteristics and listing information.

It covers the complete regression workflow, from data preprocessing and feature engineering to model training, evaluation, prediction, feature analysis, and visualization.

## Author

Airbnb Rental Price Estimation Machine Learning Project
