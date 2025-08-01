
# 🧮 Credit Risk Dashboard — Dirty Credit Customers EDA

This dashboard visualizes cleaned and enriched credit customer data, highlighting patterns in credit risk, demographic profiles, and regional behavior.

## 📌 Project Overview

The project is based on a raw dataset with inconsistent entries, which was cleaned using Python. A Power BI dashboard was developed to enable business stakeholders to explore credit score distributions, high-risk profiles, and credit performance trends over time.

## 🎯 Objectives

- Clean and preprocess real-world customer data  
- Categorize credit risk using a derived credit level metric  
- Track trends by region, gender, marital status, and time  
- Support dynamic filtering and drill-down analytics  

## 📊 Dashboard Features

- **Average Credit Score Card**  
- **Total Customers Card**  
- **Average Credit Amount Card**  
- **High-Risk Percentage Card**  
- **Credit Risk Segmentation** (Bar Chart)  
- **Customer Distribution by Credit Level** (Pie Chart)  
- **Monthly Credit Trend** (Line Chart)  
- **High Risk by Marital Status** (Bar Chart)  
- **High Risk by Gender** (Donut Chart)  
- **High Risk Trend by Month** (Line Chart)  
- **Customer Distribution Map** (Region-level)  
- **Dynamic filters**: by Region, Gender, Date Range  


## 🧼 Data Cleaning

Performed using a Python pipeline:
- Standardized text fields (`Gender`, `FullName`)  
- Fixed invalid or missing date formats  
- Filled missing values (e.g., `CreditScore`) with statistical methods  
- Removed outliers from numerical columns  
- Created a new column `CreditLevel` based on `CreditScore`  

## 🧮 DAX Measures Used

- `Avg Credit Score = AVERAGE(CreditScore)`  
- `Total Customers = COUNT(CustomerID)`  
- `Avg Credit = AVERAGE(CreditAmount)`  
- `High Risk % = DIVIDE(CALCULATE(COUNT(CustomerID), CreditLevel = "Very Poor"), [Total Customers])`  
- `Credit Risk Segmentation = COUNT(CustomerID) by CreditLevel`  
- `High Risk by Gender = COUNT(CustomerID) where CreditLevel = "Very Poor"`  
- `High Risk by Marital Status = COUNT(CustomerID) grouped by MaritalStatus and filtered by risk level`  
- `Monthly Credit Trend = SUM(CreditAmount) by Month`  
- `Customers This Year = COUNT(CustomerID) filtered by current year`  
- `Dynamic Date Range = Slicer on JoinDate`  

## 🗂️ Project Structure

```
credit-dashboard/
├── data/
│   └── dirty_credit_customers.csv
├── notebooks/
│   └── cleaning_and_eda.ipynb
├── powerbi/
│   └── credit_dashboard.pbix
├── screnshoots/
├── README.md
└── requirements.txt
```

## 🧰 Tools & Technologies

- **Python**: pandas, numpy, matplotlib, seaborn  
- **Power BI**: DAX, visuals, slicers, cards  
- **Jupyter Notebook**: for data transformation  
- **GitHub**: version control & documentation  

## 📌 Insights Supported

- Customer segments based on credit levels  
- Gender and marital status influence on credit risk  
- Temporal trends in credit activity  
- Region-level performance and high-risk concentration  

## 📥 How to Use

1. Clone the repository:
```bash
git clone https://github.com/yourusername/credit-dashboard.git
```

2. Install requirements:
```bash
pip install -r requirements.txt
```

3. Run the cleaning notebook:
```bash
jupyter notebook notebooks/cleaning_and_eda.ipynb
```

4. Open the dashboard in Power BI:
```
powerbi/credit_dashboard.pbix
```

---

## ✍️ Author

Created as part of the **Dirty Credit Customers — EDA Project**  
Focus: Data cleaning, segmentation, and interactive dashboarding.
