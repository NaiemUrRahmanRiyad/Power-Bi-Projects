# 📉 End-to-End Customer Churn Analysis

![Project Banner](https://pivotalstats.com/wp-content/uploads/2024/09/Project-Churn-Analysis.jpg)

> A complete data analytics project covering ETL, Power BI dashboarding, and Machine Learning-based churn prediction for a telecom company.

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Project Goals](#-project-goals)
- [Tech Stack](#-tech-stack)
- [Project Workflow](#-project-workflow)
  - [Step 1 – ETL in SQL Server](#step-1--etl-process-in-sql-server)
  - [Step 2 – Power BI Transform](#step-2--power-bi-transform)
  - [Step 3 – DAX Measures](#step-3--power-bi-measures)
  - [Step 4 – Power BI Visualization](#step-4--power-bi-visualization)
  - [Step 5 – Churn Prediction (ML)](#step-5--predict-customer-churn)
  - [Step 6 – Predicted Data Dashboard](#step-6--power-bi-visualization-of-predicted-data)
- [Key Metrics](#-key-metrics)
- [Dashboard Pages](#-dashboard-pages)
- [Dataset](#-dataset)

---

## 🔍 Overview

In today's competitive business environment, retaining customers is crucial for long-term success. This project performs a full **end-to-end churn analysis** for a telecom firm — from raw data ingestion to an interactive Power BI dashboard and a Machine Learning model to predict future churners.

Although focused on telecom, the techniques and insights are applicable across industries — retail, finance, healthcare, and any business that values customer retention.

---

## 🎯 Project Goals

- ✅ Build an entire **ETL pipeline** in SQL Server
- ✅ Create an interactive **Power BI dashboard** to analyze customer data
- ✅ Study churner profiles and **identify areas for marketing campaigns**
- ✅ Build a **Machine Learning model** (Random Forest) to predict future churners

### 📊 Analysis Dimensions
| Dimension | Details |
|-----------|---------|
| 👥 Demographic | Gender, Age Group, Marital Status |
| 🗺️ Geographic | State-wise churn distribution |
| 💳 Payment & Account | Payment method, contract type, tenure |
| 🌐 Services | Internet type, streaming, security, etc. |

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| ![SQL Server](https://img.shields.io/badge/SQL%20Server-CC2927?style=flat&logo=microsoft-sql-server&logoColor=white) | ETL, data storage & views |
| ![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black) | Data transformation & dashboarding |
| ![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white) | Machine Learning (Random Forest) |
| ![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat&logo=jupyter&logoColor=white) | ML model development |
| ![Excel](https://img.shields.io/badge/Excel-217346?style=flat&logo=microsoft-excel&logoColor=white) | Data export for ML input |

---

## 🔄 Project Workflow

### Step 1 – ETL Process in SQL Server

**1.1 Create the Database**
```sql
CREATE DATABASE db_Churn
```

**1.2 Import CSV via Import Wizard**
- Right-click DB → Task → Import → Flat File → Browse CSV
- Set `CustomerID` as Primary Key
- Allow NULLs for all other columns
- Change `Bit` columns to `Varchar(50)`

**1.3 Data Exploration – Check Distinct Values**
```sql
SELECT Gender, Count(Gender) as TotalCount,
Count(Gender) * 1.0 / (Select Count(*) from stg_Churn) as Percentage
FROM stg_Churn
GROUP BY Gender
```

```sql
SELECT Customer_Status, Count(Customer_Status) as TotalCount, Sum(Total_Revenue) as TotalRev,
Sum(Total_Revenue) / (Select sum(Total_Revenue) from stg_Churn) * 100 as RevPercentage
FROM stg_Churn
GROUP BY Customer_Status
```

**1.4 Null Check**
```sql
SELECT 
    SUM(CASE WHEN Customer_ID IS NULL THEN 1 ELSE 0 END) AS Customer_ID_Null_Count,
    SUM(CASE WHEN Gender IS NULL THEN 1 ELSE 0 END) AS Gender_Null_Count,
    SUM(CASE WHEN Age IS NULL THEN 1 ELSE 0 END) AS Age_Null_Count,
    -- ... (all columns checked)
FROM stg_Churn;
```

**1.5 Clean & Load into Production Table**
```sql
SELECT 
    Customer_ID, Gender, Age, Married, State,
    ISNULL(Value_Deal, 'None') AS Value_Deal,
    ISNULL(Multiple_Lines, 'No') AS Multiple_Lines,
    ISNULL(Internet_Type, 'None') AS Internet_Type,
    ISNULL(Churn_Category, 'Others') AS Churn_Category,
    ISNULL(Churn_Reason, 'Others') AS Churn_Reason
    -- ... (all columns)
INTO [db_Churn].[dbo].[prod_Churn]
FROM [db_Churn].[dbo].[stg_Churn];
```

**1.6 Create Views for Power BI**
```sql
CREATE VIEW vw_ChurnData AS
    SELECT * FROM prod_Churn WHERE Customer_Status IN ('Churned', 'Stayed')

CREATE VIEW vw_JoinData AS
    SELECT * FROM prod_Churn WHERE Customer_Status = 'Joined'
```

---

### Step 2 – Power BI Transform

New calculated columns added in Power Query:

| Column | Logic |
|--------|-------|
| `Churn Status` | `if [Customer_Status] = "Churned" then 1 else 0` |
| `Monthly Charge Range` | Bucketed: `< 20`, `20-50`, `50-100`, `> 100` |
| `Age Group` | Bucketed: `< 20`, `20–35`, `36–50`, `> 50` |
| `Tenure Group` | Bucketed: `< 6 Months` → `>= 24 Months` |

**Additional Reference Tables Created:**
- 🗂️ `mapping_AgeGrp` — age group with sort order
- 🗂️ `mapping_TenureGrp` — tenure group with sort order
- 🗂️ `prod_Services` — unpivoted services table (Services & Status columns)

---

### Step 3 – Power BI Measures

```dax
Total Customers = COUNT(prod_Churn[Customer_ID])

New Joiners = CALCULATE(COUNT(prod_Churn[Customer_ID]), 
              prod_Churn[Customer_Status] = "Joined")

Total Churn = SUM(prod_Churn[Churn Status])

Churn Rate = [Total Churn] / [Total Customers]
```

---

### Step 4 – Power BI Visualization

**Summary Page**
- 📦 Top KPI Cards: Total Customers, New Joiners, Total Churn, Churn Rate %
- 👥 Demographic: Gender & Age Group vs Churn Rate
- 💳 Account Info: Payment Method, Contract, Tenure vs Churn Rate
- 🗺️ Geographic: Top 5 States by Churn Rate
- 📊 Churn Distribution: Category & Reason breakdown
- 🌐 Services: Internet Type & Service Usage vs Churn

**Churn Reason Page (Tooltip)**
- Detailed breakdown of Churn Reason vs Total Churn

---

### Step 5 – Predict Customer Churn

Using **Random Forest Classifier** — an ensemble of decision trees that votes on the final prediction, reducing overfitting.

**Install Required Libraries**
```bash
pip install pandas numpy matplotlib seaborn scikit-learn joblib
```

**Import Libraries & Load Data**
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import classification_report, confusion_matrix
from sklearn.preprocessing import LabelEncoder
import joblib

file_path = r"C:\yourpath\Prediction_Data.xlsx"
data = pd.read_excel(file_path, sheet_name='vw_ChurnData')
```

**Data Preprocessing**
```python
data = data.drop(['Customer_ID', 'Churn_Category', 'Churn_Reason'], axis=1)

columns_to_encode = ['Gender', 'Married', 'State', 'Value_Deal', 'Phone_Service',
                     'Multiple_Lines', 'Internet_Service', 'Internet_Type', ...]

label_encoders = {}
for column in columns_to_encode:
    label_encoders[column] = LabelEncoder()
    data[column] = label_encoders[column].fit_transform(data[column])

data['Customer_Status'] = data['Customer_Status'].map({'Stayed': 0, 'Churned': 1})

X = data.drop('Customer_Status', axis=1)
y = data['Customer_Status']
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
```

**Train & Evaluate Model**
```python
rf_model = RandomForestClassifier(n_estimators=100, random_state=42)
rf_model.fit(X_train, y_train)

y_pred = rf_model.predict(X_test)
print(confusion_matrix(y_test, y_pred))
print(classification_report(y_test, y_pred))
```

**Predict on New Joiners**
```python
new_data = pd.read_excel(file_path, sheet_name='vw_JoinData')
# Encode, predict, and save results
original_data['Customer_Status_Predicted'] = rf_model.predict(new_data)
original_data[original_data['Customer_Status_Predicted'] == 1].to_csv(r"C:\yourpath\Predictions.csv", index=False)
```

---

### Step 6 – Power BI Visualization of Predicted Data

**New DAX Measures**
```dax
Count Predicted Churner = COUNT(Predictions[Customer_ID]) + 0

Title Predicted Churners = "COUNT OF PREDICTED CHURNERS : " & COUNT(Predictions[Customer_ID])
```

**Churn Prediction Page**
- 📋 Grid: Customer ID, Monthly Charge, Total Revenue, Refunds, Referrals
- 👥 Demographic: Gender, Age Group, Marital Status vs Predicted Churn Count
- 💳 Account Info: Payment Method, Contract, Tenure vs Predicted Churn Count
- 🗺️ Geographic: State-wise Predicted Churn Count

---

## 📈 Key Metrics

| Metric | Description |
|--------|-------------|
| **Total Customers** | Overall customer base count |
| **Total Churn** | Number of customers who left |
| **Churn Rate** | Percentage of customers churned |
| **New Joiners** | Customers who recently joined |

---

## 🖥️ Dashboard Pages

| Page | Description |
|------|-------------|
| 📊 Summary | Historical churn analysis across all dimensions |
| 📋 Churn Reason (Tooltip) | Drill-through view of churn reasons |
| 🔮 Churn Prediction | Predicted future churners from ML model |

---



**Color Palette Used**

| Color | Hex |
|-------|-----|
| 🟣 Primary | `#4A44F2` |
| 🔵 Secondary | `#9B9FF2` |
| ⚪ Background | `#F2F2F2` |
| 🩵 Accent | `#A0D1FF` |

---

## 🙌 Acknowledgements

Project concept and tutorial by **[Pivotal Stats](https://pivotalstats.com/)**.

---

> ⭐ If you found this project helpful, please give it a star!
