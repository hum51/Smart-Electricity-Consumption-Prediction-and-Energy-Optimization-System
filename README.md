# ⚡ Smart Electricity Consumption Prediction & Energy Optimization System

> **Task ML-3 | Teyzix Core Internship (June Batch)**

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.0+-orange.svg)](https://scikit-learn.org/)
[![XGBoost](https://img.shields.io/badge/XGBoost-1.5+-red.svg)](https://xgboost.readthedocs.io/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)

-

## 📋 Table of Contents

- [📖 Project Overview](#-project-overview)
- [🎯 Objectives](#-objectives)
- [📊 Dataset](#-dataset)
- [🛠️ Technology Stack](#️-technology-stack)
- [📈 Key Achievements](#-key-achievements)
- [📂 Project Structure](#-project-structure)
- [🚀 Installation](#-installation)
- [💻 Usage](#-usage)
- [📊 Results](#-results)
- [🔮 Future Improvements](#-future-improvements)
- [📝 Report](#-report)
- [👤 Author](#-author)

---

## 📖 Project Overview

This project develops a **production-ready Machine Learning system** that predicts daily electricity consumption based on user behavior and appliance usage patterns. The system provides **personalized energy optimization recommendations** to help users reduce their electricity bills.

### 🎯 Why This Project?

- ⚡ **Energy Crisis:** Rising electricity costs and growing energy demand
- 💰 **Cost Savings:** Help users save 10-15% on monthly bills
- 🌍 **Sustainability:** Promote energy conservation
- 🤖 **AI Innovation:** Apply ML to real-world problems

### 🎯 Key Features

| Feature | Description |
|---------|-------------|
| 🔮 **Prediction** | Predict daily electricity consumption with 95.87% accuracy |
| 📊 **Analysis** | Identify peak usage hours and high-consumption appliances |
| 💡 **Recommendations** | Personalized energy optimization tips |
| 📈 **Reporting** | Comprehensive reports and visualizations |
| 💻 **Interactive CLI** | User-friendly command-line interface |



## 🎯 Objectives

| # | Objective | Status |
|---|-----------|--------|
| 1 | Create original dataset with 500+ records | ✅ |
| 2 | Perform data preprocessing and cleaning | ✅ |
| 3 | Conduct comprehensive EDA | ✅ |
| 4 | Engineer new features | ✅ |
| 5 | Develop and compare ML models | ✅ |
| 6 | Build prediction system | ✅ |
| 7 | Generate energy recommendations | ✅ |

---

## 📊 Dataset

### 📋 Dataset Overview

| Property | Value |
|----------|-------|
| **Total Records** | 856 |
| **Total Features** | 18 (Original) |
| **Target Variable** | Daily_Electricity_Consumption_kWh |
| **Data Collection** | Self-created, realistic simulation |

### 📋 Features Description

| Category | Features |
|----------|----------|
| 🏠 **Household** | House_Type, Family_Members, Rooms |
| 📺 **Appliances** | AC, Fan, Refrigerator, Washing Machine, Water Motor, Lighting |
| 🌤️ **Environmental** | Temperature, Day of Week, Season, Holiday |
| 🏭 **Industrial** | Machinery_Load_kW, Machinery_Usage_Hours |
| 💰 **Financial** | Electricity_Unit_Price |
| 🎯 **Target** | Daily_Electricity_Consumption_kWh |


## 🛠️ Technology Stack

### 📦 Libraries Used

```python
import pandas as pd          # Data manipulation
import numpy as np           # Numerical computing
import matplotlib.pyplot as plt  # Visualization
import seaborn as sns        # Statistical visualization
from sklearn.model_selection import train_test_split  # Data splitting
from sklearn.preprocessing import LabelEncoder, StandardScaler  # Preprocessing
from sklearn.linear_model import LinearRegression  # Linear Regression
from sklearn.tree import DecisionTreeRegressor  # Decision Tree
from sklearn.ensemble import RandomForestRegressor, GradientBoostingRegressor  # Ensemble
from sklearn.svm import SVR  # Support Vector Regression
from xgboost import XGBRegressor  # XGBoost
from sklearn.metrics import mean_absolute_error, mean_squared_error, r2_score  # Metrics
🛠️ Tools & Platforms
Tool	Purpose
🐍 Python 3.8+	Programming Language
📓 Jupyter Notebook	Development Environment
🤖 Google Colab	Cloud Execution
📊 Scikit-learn	Machine Learning
🚀 XGBoost	Gradient Boosting
📈 Matplotlib/Seaborn	Visualization
💾 Joblib	Model Serialization
📈 Key Achievements
#	Achievement	Details
1	Original Dataset	856 records, 18 features, self-created
2	High Accuracy	95.87% R² Score with Random Forest
3	Models Compared	6 ML models systematically evaluated
4	Feature Engineering	10 new features created
5	Visualizations	20+ comprehensive charts
6	Cross-Validation	5-fold CV with 0.94 mean R²
7	Cost Savings	10-15% potential bill reduction
8	Production-Ready	Complete ML pipeline with saved models
📂 Project Structure
text
smart-electricity-consumption-prediction/
│
├── 📊 data/
│   ├── smart_electricity_consumption_dataset.csv
│   ├── smart_electricity_consumption_cleaned.csv
│   └── smart_electricity_consumption_featured.csv
│
├── 📓 notebooks/
│   └── Smart_Electricity_Consumption_Prediction.ipynb
│
├── 🤖 models/
│   ├── electricity_consumption_model.pkl
│   ├── scaler.pkl
│   ├── feature_columns.pkl
│   └── label_encoders.pkl
│
├── 💻 src/
│   └── predict_cli.py
│
├── 📝 reports/
│   ├── Project_Report.txt
│   ├── Performance_Summary.csv
│   └── Project_Report.pdf
│
├── 🖼️ images/
│   ├── heatmap.png
│   ├── feature_importance.png
│   └── model_comparison.png
│
├── 📄 README.md
├── 📋 requirements.txt
├── 📜 LICENSE
└── .gitignore

💻 Usage
🎮 Interactive Mode
bash
python src/predict_cli.py --interactive
Sample Input:

text
Enter House Type (0-6): 0
Number of Family Members: 5
Number of Rooms: 4
AC Usage Hours (0-24): 8
Fan Usage Hours (0-24): 12
Refrigerator Usage Hours (0-24): 24
Washing Machine Usage Hours (0-24): 1
Water Motor Usage Hours (0-24): 0.5
Lighting Hours (0-24): 8
Outdoor Temperature (°C): 35
Day of Week (0-6): 5
Season (0-3): 2
Electricity Unit Price (Rs/kWh): 35
Sample Output:

text
═══════════════════════════════════════════════════════════════
PREDICTION RESULTS
═══════════════════════════════════════════════════════════════
Predicted Daily Consumption: 27.46 kWh
Predicted Monthly Consumption: 823.80 kWh
Predicted Monthly Cost: Rs. 28,833.00

ENERGY OPTIMIZATION RECOMMENDATIONS
═══════════════════════════════════════════════════════════════
1. [Air Conditioner]
   Reduce AC usage to 6-8 hours/day. Set temperature to 26°C.
   Potential Savings: 5-10%

2. [Lighting]
   Switch to LED bulbs. Use natural lighting.
   Potential Savings: 1-3%

3. [General Tips]
   Monitor peak usage hours (6-10 PM).
   Potential Savings: 5-10%
📊 Batch Prediction
bash
python src/predict_cli.py --batch data/test_data.csv
📊 Results
🏆 Model Performance Comparison
Model	R² Score	RMSE	MAE	Time (sec)
Random Forest	0.9587	15.23	4.82	2.34
XGBoost	0.9512	16.45	5.14	3.12
Gradient Boosting	0.9354	18.92	5.67	4.56
Decision Tree	0.8816	25.61	7.84	0.45
Linear Regression	0.7265	38.92	12.45	0.23
SVR	0.6234	45.67	14.82	8.91
📈 Best Model: Random Forest Regressor
Metric	Value
R² Score	0.9587 (95.87%)
RMSE	15.23 kWh
MAE	4.82 kWh
Cross-Validation R²	0.94 ± 0.02
🔍 Feature Importance (Top 5)
Rank	Feature	Importance
1	AC_Usage_Hours	0.184
2	Total_Appliance_Hours	0.156
3	Outdoor_Temperature_C	0.132
4	Fan_Usage_Hours	0.108
5	Machinery_Load_kW	0.087
📊 Key Insights
Insight	Finding
🌞 Seasonal Impact	Summer: 28.5 kWh/day, Winter: 12.3 kWh/day
🎉 Holiday Effect	15% lower consumption on holidays
🔥 Top Correlation	AC_Usage (0.62), Temperature (0.58)
🏭 Highest Consumers	Industrial > Outlets > Villas > Houses > Apartments
🔮 Future Improvements
#	Improvement	Benefit
1	🌤️ Weather API Integration	Real-time accurate predictions
2	🖥️ Interactive Dashboard	Streamlit/Gradio web application
3	🔍 SHAP/LIME Explainability	Model transparency
4	📱 Mobile Application	Accessibility on phones
5	📡 IoT Integration	Automatic data collection
6	🔴 Real-Time Monitoring	Live consumption tracking
7	🤖 Deep Learning	LSTM/RNN for time-series
📝 Report
📄 Generated Reports
Report	Description
Project_Report.txt	Complete project documentation
Performance_Summary.csv	Model metrics summary
Project_Report.pdf	Professional PDF report
🖼️ Visualizations
📊 Histograms & KDE Plots
📦 Box Plots & Violin Plots
🔥 Correlation Heatmaps
📈 Scatter Plots with Trend Lines
🥧 Pie Charts & Donut Charts
📉 Feature Importance Plots
📊 Model Comparison Charts

🙏 Acknowledgments
providing this opportunity for Mentors and instructors for guidance
Open-source community for amazing libraries

Energy saved is energy produced. Smart consumption leads to sustainable future. 🌍⚡
