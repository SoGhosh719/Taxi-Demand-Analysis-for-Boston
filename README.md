# Taxi-Demand-Analysis-for-Boston

# 🚕 Taxi Demand Analysis: A Data Science Case Study

This project explores key insights from a large-scale rideshare dataset, examining how ride pricing, demand, and external factors like time and weather affect taxi behavior in a major metropolitan city.

---

## 📂 Dataset Overview
- **Source**: `rideshare_kaggle.csv`
- **Size**: ~693,071 records (post-cleaning: 637,976 entries)
- **Features**: 57 columns including ride data (cab type, distance, surge), weather, time, and location
- **Cleaning**: Dropped rows with null values in critical columns such as `price`

---

## 💰 Price Distribution & Influencing Factors

### 📊 Price Distribution
- Right-skewed with most rides in the lower price range
- Outliers present, likely due to high surge pricing or long distances

### 🚖 Uber vs. Lyft Comparison
- **Median prices** are similar
- Lyft has more **extreme high-end outliers**
- Boxplot reveals variability, particularly at higher price levels

### 🚀 Surge Pricing Impact
- Surge multiplier has a strong positive correlation with price
- Surge >2.0 results in steep price hikes
- Wider price variance and IQR at high surge values

---

## 🌦 Weather & Time Influence

### Weather Correlation with Price
- Weak correlation with weather features:
  - `temperature`, `precipIntensity`, `humidity`, `windSpeed` ≈ 0
- ANOVA tests: p-values > 0.23 → **No statistical significance**

### Time of Day Pricing Trends
- Price peaks:
  - Morning (7–9 AM)
  - Evening (8–10 PM)
- Lowest prices seen between 3–5 AM

---

## 🔥 Ride Demand Patterns

### Ride Frequency by Hour
- Highest: 6 PM–10 PM
- Lowest: 2 AM–5 AM
- Matches with expected commute and social schedules

### Location Trends
- **Top pickup**: Haymarket Square
- **Top drop-off**: North Station

---

## 🧠 Predictive Modeling

### Random Forest Regressor: Price Prediction
- **Features**: Distance, surge multiplier, temperature, humidity, wind speed, hour
- **Results**:
  - MAE: $7.60
  - RMSE: $9.37
  - R²: -0.0068 (very poor fit)

### Cost Efficiency
- Calculated `cost_per_mile` by ride type
- Boxplots identify affordable vs. premium services

---

## 👤 Customer Behavior & Duration Analysis

### Ride Type Demand
- Lyft and Uber had similar ride counts
- Ride-specific popularity varies by service (UberX, Lyft Lux, etc.)

### Trip Duration (Estimated)
- Approximated by: `distance / windSpeed`
- Skewed distribution, with several long-duration outliers

---

## 🌩 Weather vs. Demand Analysis

- Weather has **no significant impact** on price
- Slight **drop in demand** during extreme conditions (wind, precipitation)
- Surge multiplier not correlated with weather

---

## 📌 Recommendations

### For Business Strategists
- Focus surge pricing on **peak hours** and **high-demand locations**
- Weather-based pricing is unnecessary

### For Data Scientists
- Improve feature engineering: encode `cab_type`, `ride name`, cluster locations
- Explore advanced models: XGBoost, time-series (LSTM)
- Incorporate traffic/event data for richer predictions

---

## 📁 Project Assets
- Data Cleaning & EDA Notebooks
- Visualizations (Seaborn, Matplotlib)
- Predictive Model (RandomForestRegressor)

> **Note**: Future work may include interactive dashboards using Streamlit or deployment to a cloud platform.

---

### 👨‍💻 Author
Soumyabrata Ghosh  
M.S. Business Analytics @ Clark University  
[GitHub Portfolio](https://github.com/SoGhosh719)
