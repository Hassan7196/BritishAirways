# Predictive Modeling for Customer Bookings: A British Airways Case Study

## Overview
This project focuses on predicting whether a customer will complete a booking based on various features such as sales channel, trip type, purchase lead time, flight duration, and more. The dataset, provided by British Airways, contains 50,000 entries with 14 features. The goal is to build a machine learning model that can accurately predict booking completions and provide actionable insights for optimizing customer engagement and revenue.

---

## Table of Contents
1. [Project Overview](#overview)
2. [Dataset Description](#dataset-description)
3. [Key Steps](#key-steps)
4. [Model Performance](#model-performance)
5. [Key Findings](#key-findings)


---

## Dataset Description
The dataset contains the following features:
- **num_passengers**: Number of passengers traveling.
- **sales_channel**: Sales channel used for booking (Internet or Mobile).
- **trip_type**: Type of trip (Round Trip, One Way, Circle Trip).
- **purchase_lead**: Number of days between booking and travel.
- **length_of_stay**: Number of days spent at the destination.
- **flight_hour**: Hour of flight departure.
- **flight_day**: Day of the week of flight departure.
- **route**: Origin and destination flight route.
- **booking_origin**: Country from where the booking was made.
- **wants_extra_baggage**: Whether the customer wanted extra baggage.
- **wants_preferred_seat**: Whether the customer wanted a preferred seat.
- **wants_in_flight_meals**: Whether the customer wanted in-flight meals.
- **flight_duration**: Total duration of the flight (in hours).
- **booking_complete**: Target variable indicating whether the booking was completed (1) or not (0).

---

## Key Steps
1. **Data Exploration and Preprocessing:**
   - Handled categorical variables by encoding them into numerical values.
   - Applied frequency encoding to the `booking_origin` column.
   - Visualized data distributions and correlations.

2. **Model Training:**
   - Trained multiple models, including Logistic Regression, Decision Tree, Random Forest, Gradient Boosting, and more.
   - Split the data into 70% training and 30% testing sets.

3. **Model Evaluation:**
   - Evaluated models using accuracy, precision, recall, and F1 score.
   - Identified challenges due to dataset imbalance.

---

## Model Performance
| Model                  | Accuracy | Precision (Class 1) | Recall (Class 1) | F1 Score (Class 1) |
|------------------------|----------|---------------------|------------------|--------------------|
| Logistic Regression    | 85.23%   | 0.00                | 0.00             | 0.00               |
| Decision Tree          | 77.16%   | 0.26                | 0.30             | 0.28               |
| Random Forest          | 85.22%   | 0.50                | 0.10             | 0.16               |
| Gradient Boosting      | 85.28%   | 0.56                | 0.02             | 0.03               |

---

## Key Findings
1. The dataset is imbalanced, with only ~15% of bookings being completed (class 1).
2. Most models achieved high overall accuracy (~85%) but struggled to predict class 1 accurately.
3. Features like `purchase_lead`, `flight_duration`, and `wants_extra_baggage` showed some correlation with the target variable.


---

## How to Use This Repository
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/predictive-modeling-british-airways.git
