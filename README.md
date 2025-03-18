# Predictive Modeling for Customer Bookings: A British Airways Case Study

## Overview
This project focuses on predicting whether a customer will complete a booking based on various features such as sales channel, trip type, purchase lead time, flight duration, and more. The dataset, provided by British Airways, contains **50,000 entries** with **14 features**. The goal is to build a machine learning model that can accurately predict booking completions and provide actionable insights for optimizing customer engagement and revenue.

The goal of this project is to predict whether a customer will complete a booking based on historical booking data. The dataset includes features such as:
- **Number of passengers**
- **Sales channel** (Internet or Mobile)
- **Trip type** (Round Trip, One Way, Circle Trip)
- **Purchase lead** (time between booking and travel)
- **Length of stay** (duration of the trip)
- **Flight details** (hour, day, duration, route)
- **Customer preferences** (extra baggage, preferred seat, in-flight meals)

The project uses **machine learning** to analyze these features and predict booking completion. The insights gained can help British Airways optimize marketing strategies, improve customer engagement, and increase revenue.


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
The project involved the following steps:

### **1. Data Exploration and Preprocessing**
- **Handled Missing Values**: Checked for missing data and imputed if necessary.
- **Outlier Handling**: Capped outliers in `purchase_lead` and `length_of_stay` using the IQR method.
- **Feature Encoding**:
  - Encoded categorical variables (`sales_channel`, `trip_type`, `flight_day`) using **Label Encoding**.
  - Applied **Frequency Encoding** to high-cardinality features like `route` and `booking_origin`.
- **Feature Scaling**: Scaled numerical features using **StandardScaler**.

### **2. Model Training**
- **Train-Test Split**: Split the data into 70% training and 30% testing sets.
- **Trained Multiple Models**:
  - Logistic Regression
  - Decision Tree
  - Random Forest
  - Gradient Boosting
  - Support Vector Machine (SVM)
  - K-Nearest Neighbors (KNN)
  - Naive Bayes

### **3. Model Evaluation**
- Evaluated models using **accuracy**, **precision**, **recall**, and **F1-score**.
- Addressed class imbalance using **SMOTE** (Synthetic Minority Oversampling Technique).

---

## Model Performance
Here’s a summary of the model performance:

| Model               | Accuracy | Precision (Class 1) | Recall (Class 1) | F1-Score (Class 1) |
|---------------------|----------|---------------------|------------------|--------------------|
| Logistic Regression | 85.23%   | 0.00                | 0.00             | 0.00               |
| Decision Tree       | 77.16%   | 0.26                | 0.30             | 0.28               |
| Random Forest       | 85.22%   | 0.50                | 0.10             | 0.16               |
| Gradient Boosting   | 85.28%   | 0.56                | 0.02             | 0.03               |

### **Best Model: Random Forest**
- **Accuracy**: 85.22%
- **Precision (Class 1)**: 0.50
- **Recall (Class 1)**: 0.10
- **F1-Score (Class 1)**: 0.16

---

## Key Findings
1. **Class Imbalance**:
   - The dataset is imbalanced, with only ~15% of bookings being completed (class 1).
   - Most models achieved high overall accuracy (~85%) but struggled to predict class 1 accurately.

2. **Important Features**:
   - `purchase_lead`, `flight_duration`, and `wants_extra_baggage` showed some correlation with the target variable.
   - `route` and `booking_origin` were also significant predictors.

3. **Challenges**:
   - The imbalance in the dataset made it difficult for models to predict class 1 effectively.
   - Feature engineering and advanced techniques like SMOTE were used to address this issue.

---
---

## How to Use This Repository
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/predictive-modeling-british-airways.git
