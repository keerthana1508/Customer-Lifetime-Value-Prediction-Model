# 🧮 Customer Lifetime Value (CLTV) Prediction Model

📄 **Customer Lifetime Value Prediction – Project Report**  
👤 **Author**: Keerthana Kothoju  
📅 **Date**: 18/05/2025  
🏢 **Project by**: Elevate Labs  

---

## 🎯 Objective

The aim of this project is to predict **Customer Lifetime Value (CLTV)** using historical purchase behavior. This predictive model helps in **targeted marketing** by segmenting customers based on their predicted future value.

---

## 🧰 Tools & Technologies

- Python: `Pandas`, `NumPy`, `Seaborn`, `Matplotlib`, `Scikit-learn`, `XGBoost`
- Jupyter Notebook
- Excel (used for basic data inspection)

---

## 📦 Dataset Overview

- **Source**: Online Retail transactional data  
- **Fields**:  
  `InvoiceNo`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `UnitPrice`, `CustomerID`, `Country`  
- **Size**: 541,909 rows × 8 columns  
- **Missing Values**: Found in `CustomerID` and `Description`  
- **Focus**: United Kingdom customers only  

---

## 🔍 Exploratory Data Analysis (EDA)

### 🧼 Data Cleaning

- Removed rows with missing `CustomerID`
- Dropped records with negative `Quantity` or `UnitPrice`
- Created `TotalPrice = Quantity × UnitPrice`

### 📊 Key Visual Insights

- **📈 Monthly Revenue Trend**: Shows revenue performance over time
- **🏆 Top Products Sold**: Top 10 bestsellers by quantity
- **💰 Top Customers**: Highest revenue-contributing customers
- **📦 Order Value Distribution**: Right-skewed distribution, indicating smaller order values dominate

---

## 🔧 Feature Engineering

Generated customer-level metrics from transactions:

- `Recency`: Days since last purchase  
- `Frequency`: Count of unique invoices  
- `Average Order Value (AOV)`: TotalSpend / NumInvoices  
- `CLTV` (Target): Total spend per customer  

These were combined into a new DataFrame called **`customer_df`**.

---

## 📈 Advanced Visual Analysis (Post-Feature Engineering)

- **CLTV Distribution**: Right-skewed (few high-value customers)
- **Recency Boxplot**: Most customers purchase recently, some are inactive
- **Frequency vs CLTV**: Frequent customers tend to be more valuable
- **AOV vs CLTV**: Higher AOV often correlates with higher CLTV

---

## 🤖 Model Training

- **Algorithm**: `XGBoost Regressor`
- **Features**: `Recency`, `Frequency`, `AOV`
- **Target**: `CLTV`

### 📊 Performance Metrics:

| Metric | Score     |
|--------|-----------|
| MAE    | 305.83    |
| RMSE   | 2695.84   |

---

## 🧪 Validation & Segmentation

Customers were segmented based on their predicted CLTV:

- 🟢 **High Value**: Top 20%  
- 🟡 **Medium Value**: Next 30%  
- 🔴 **Low Value**: Bottom 50%  

This segmentation helps marketers **personalize outreach** and retain valuable customers more effectively.

---

## ✅ Conclusion

This project demonstrates:

- ✅ Clean and insightful EDA  
- ✅ Smart feature extraction  
- ✅ A working CLTV prediction model  
- ✅ Practical customer segmentation for business strategy  

---
