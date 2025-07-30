# Dynamic Pricing for E-Commerce (Airbnb Chicago)

This project focuses on implementing a **dynamic pricing model** for the e-commerce sector using **real-world Airbnb data from Chicago**. As e-commerce platforms face rapid shifts in customer demand and market trends, this solution helps generate optimized price recommendations using machine learning. The project emphasizes both business sustainability and customer satisfaction.

---

## Tech Stack

- Python
- Jupyter Notebook
- scikit-learn
- Pandas, NumPy, Matplotlib, Seaborn
- GridSearchCV, KNN, Random Forest, Gradient Boosting, SVR

---

## Overview

Dynamic pricing allows businesses to respond in real-time to changing market conditions. This project explores and compares various regression algorithms to predict Airbnb listing prices based on features such as amenities, reviews, availability, and location.

Key goals:

- Improve price prediction accuracy
- Enable competitive yet fair pricing
- Enhance customer trust and retention
- Support data-driven pricing strategies

---

## Dataset

**Source:** [Inside Airbnb](https://insideairbnb.com/get-the-data)  
**City:** Chicago  
**Date:** September 2023

**Target Variable:** `price`  
**Features Include:**

- Room/property details (accommodates, bedrooms, bathrooms, etc.)
- Host response time
- Amenities (top 10 extracted)
- Review scores (cleanliness, value, communication, etc.)
- Location (latitude, longitude)
- Availability and listing activity

---

## Exploratory Data Analysis (EDA)

- Identified missing values in features like `bedrooms` and `review_scores`
- Detected and removed duplicates
- Visualized price distributions by `room_type`
- Extracted the most common amenities and their influence on price
- Revealed trends between amenity count and pricing

---

## Data Preprocessing

Steps included:

- Text-to-numeric conversion (`bathrooms_text`)
- Label encoding of categorical features
- Cleaning and normalization of `price` column
- Mean imputation for missing values
- Amenity count extraction
- Removal of duplicate rows

---

## Feature Engineering & Selection

- Used **KNN clustering** on latitude and longitude to create `cluster_label`
- Dropped raw lat/lon after clustering
- Ranked features by importance using a **Random Forest Regressor**
- Selected top features and removed low-impact ones like `neighbourhood`

---

## Machine Learning Models

The dataset was split 80/20 for training and testing. The following models were trained, tuned, and evaluated:

| Model                 | MSE          | RMSE       | MAE       | R² Score |
| --------------------- | ------------ | ---------- | --------- | -------- |
| Linear Regression     | 18745.07     | 136.91     | 76.96     | 0.56     |
| **Random Forest**     | **10751.51** | **103.62** | **52.06** | **0.75** |
| Ridge Regression      | 18735.96     | 136.88     | 76.92     | 0.56     |
| **Gradient Boosting** | **10854.47** | **104.18** | **52.65** | **0.74** |
| SVR (RBF kernel)      | 24716.01     | 157.21     | 62.14     | 0.42     |

> **Best Models:** Random Forest & Gradient Boosting

---

## Insights

- Ensemble models showed the strongest predictive power
- Linear and Ridge Regression were interpretable but less effective for capturing complex data patterns
- SVR underperformed due to sensitivity to hyperparameters and data scale

---

## Future Enhancements

- Integrate **neural networks** for improved pattern recognition
- Scale the model with **larger datasets**
- Deploy the trained model using **Django or FastAPI**
- Create a REST API for real-time price prediction

---

## Conclusion

This project demonstrates the power of machine learning in building robust, data-driven pricing systems. By modeling dynamic pricing with real-world Airbnb data, it enables better decision-making for e-commerce platforms and offers future potential for neural network integration and deployment.
