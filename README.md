# 📊 Production vs Test Inventory Analysis Dashboard

### Dashboard Links: 

https://app.powerbi.com/groups/601e121f-ddef-4b08-86c1-b90dae8abad3/reports/f6b7beaa-e8c7-46a1-b41f-29a983093fb6/c02db08ac3aa21adb418?experience=power-bi


## 📌 Project Overview

This project focuses on analyzing inventory performance across **production** and **test environments** using SQL and Power BI. The goal is to identify demand-supply gaps, profitability, and operational inefficiencies through data-driven insights.

---

## 🗂️ Dataset Description

### 1. Production Environment Dataset

Contains:

* Order Date
* Product ID
* Availability
* Demand

### 2. Test Environment Dataset

Simulated dataset used for validation and comparison.

### 3. Products Table

Includes:

* Product ID
* Product Name
* Unit Price

---

## ⚙️ Tech Stack

* **SQL**: MySQL & MS SQL Server
* **Data Transfer**: Migration between MySQL and MSSQL
* **Visualization**: Power BI
* **Data Modeling**: Joins, transformations, calculated columns
* **DAX**: KPI calculations

---

## 🔗 Data Modeling

Performed a **Left Join** between inventory dataset and product table:

```sql
prod_inventory AS a
LEFT JOIN products AS b
ON a.Product_ID = b.Product_ID
```

This enriched the dataset with pricing information for profit/loss analysis.

---

## 📈 Key KPIs (DAX Measures)

* **Total Availability**
* **Total Demand**
* **Total Profit**
* **Total Loss**
* **Average Availability Per Day**
* **Average Demand Per Day**
* **Average Loss Per Day**
* **Total Supply Shortage**

### Sample DAX:

```DAX
Average Availability Per Day = DIVIDE([Total Availability],[Total Number of Days])

Total Profit = 
SUMX(
    FILTER('Demand/Availability Data', 'Demand/Availability Data'[LOSS/PROFIT] > 0),
    'Demand/Availability Data'[LOSS/PROFIT] * 'Demand/Availability Data'[unit_price]
)
```

---

## 📊 Dashboard Features

* 📅 Time-based trend analysis (daily performance)
* 📦 Product-level demand vs availability insights
* 💰 Profit and loss tracking
* ⚠️ Supply shortage identification
* 🔍 Interactive filters and drill-down capabilities

---

## 🚀 Key Insights

* Identified frequent **supply shortages** where demand exceeded availability
* Highlighted **high-profit products** and underperforming inventory
* Detected **inefficiencies in stock distribution**
* Enabled better **inventory planning and forecasting**

---

## 🧠 Learnings

* Cross-platform database handling (MySQL ↔ MSSQL)
* Data cleaning and transformation
* Advanced DAX calculations
* Building business-focused dashboards in Power BI

---

## 📌 Future Improvements

* Add predictive analytics for demand forecasting
* Integrate real-time data pipelines
* Implement anomaly detection for inventory spikes

---

## 📷 Dashboard Preview

![Page_1](https://github.com/user-attachments/assets/1e019a3e-cc2f-4e96-b3a6-b678254f71ea)

![Page_2](https://github.com/user-attachments/assets/05eb9296-5dc4-461e-b92a-6afb7b15d9b9)

---


## ⭐ If you like this project

Give it a star and feel free to contribute!
