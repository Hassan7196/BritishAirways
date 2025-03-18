# Predictive Modeling for Customer Bookings: A British Airways Case Study

## Overview
This project focuses on predicting whether a customer will complete a booking based on various features such as sales channel, trip type, purchase lead time, flight duration, and more. The dataset, provided by British Airways, contains 50,000 entries with 14 features. The goal is to build a machine learning model that can accurately predict booking completions and provide actionable insights for optimizing customer engagement and revenue.

The project uses machine learning to analyze these features and predict booking completion. The insights gained can help British Airways optimize marketing strategies, improve customer engagement, and increase revenue.

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

## Key Steps
The project involved the following steps:

### 1. Data Exploration and Preprocessing
- **Handled Missing Values**: Checked for missing data and imputed if necessary.
- **Outlier Handling**: Capped outliers in `purchase_lead` and `length_of_stay` using the IQR method.
- **Feature Encoding**:
  - Encoded categorical variables (`sales_channel`, `trip_type`, `flight_day`) using Label Encoding.
  - Applied Frequency Encoding to high-cardinality features like `route` and `booking_origin`.
- **Feature Scaling**: Scaled numerical features using StandardScaler.

### 2. Model Training
- **Train-Test Split**: Split the data into 70% training and 30% testing sets.
- **Trained Multiple Models**:
  - Logistic Regression
  - Decision Tree
  - Random Forest
  - Gradient Boosting
  - Support Vector Machine (SVM)
  - K-Nearest Neighbors (KNN)
  - Naive Bayes

### 3. Model Evaluation
- Evaluated models using accuracy, precision, recall, and F1-score.
- Addressed class imbalance using SMOTE (Synthetic Minority Oversampling Technique).

## Model Performance
| Model               | Accuracy | Precision (Class 1) | Recall (Class 1) | F1-Score (Class 1) |
|---------------------|----------|----------------------|-------------------|---------------------|
| Logistic Regression | 65%      | 0.65                 | 0.68              | 0.66                |
| Decision Tree      | 85%      | 0.84                 | 0.86              | 0.85                |
| Random Forest      | 90%      | 0.93                 | 0.88              | 0.90                |
| Gradient Boosting  | 84%      | 0.86                 | 0.81              | 0.83                |
| SVC                | 64%      | 0.62                 | 0.78              | 0.69                |
| KNN                | 81%      | 0.74                 | 0.96              | 0.83                |
| Naive Bayes        | 64%      | 0.59                 | 0.89              | 0.71                |

### Best Model: Tuned Random Forest
| Metric       | Score |
|-------------|--------|
| Accuracy    | 91%    |
| Precision (Class 1) | 0.93  |
| Recall (Class 1) | 0.88  |
| F1-Score (Class 1) | 0.90  |

**Best Parameters Found using GridSearchCV:**
- `max_depth`: None
- `min_samples_split`: 2
- `n_estimators`: 300

### Key Findings
#### Class Imbalance:
- The dataset is imbalanced, with only ~15% of bookings being completed (class 1).
- Most models achieved high overall accuracy (~85-91%) but struggled to predict class 1 effectively.

#### Important Features:
- `flight_duration`, `booking_origin_encoded`, and `route_freq_encoded` were the most significant predictors of booking completion.
- `purchase_lead_capped` and `length_of_stay_capped` also contributed significantly.

#### Challenges:
- The imbalance in the dataset made it difficult for models to predict class 1 effectively.
- Feature engineering and advanced techniques like SMOTE were used to address this issue.

### Conclusion
The **Tuned Random Forest Model** performed the best, achieving 91% accuracy with strong precision and recall for class 1. This model can be used to help British Airways optimize customer engagement strategies and increase booking completions.


