# Retail Analytics Dashboard (Power BI)

This repository contains a Power BI dashboard project developed to support executive decision-making at an online retail company. The dashboard answers four key questions requested by the CEO and CMO.

## 🔧 Tools Used
- Power BI Desktop (.pbix)
- Excel / Power Query for data cleaning
- DAX for calculations and measures

## 📊 Questions Answered

### Question 1 - Monthly Revenue Trends (2011 Only)
Shows revenue trends month-by-month in 2011 using a time series line chart. This helps the CEO identify seasonal trends.

### Question 2 - Top 10 Countries by Revenue (Excluding UK)
Displays a bar chart of top 10 countries based on revenue and quantity sold. The United Kingdom is excluded to focus on international markets.

### Question 3 - Top 10 Customers by Revenue
Shows a descending bar chart of the top 10 revenue-generating customers, helping the CMO identify high-value clients.

### Question 4 - Global Demand (Excluding UK)
Displays a filled map chart that highlights global demand across countries based on total quantity sold, helping the CEO with expansion strategy.

## 🧹 Data Cleaning

Data cleaning was done in Power Query. Invalid records were removed based on:
- Quantity must be >= 1
- Unit Price must be >= 0



## 📌 How to Run

1. Open any `.pbix` file in [Power BI Desktop](https://powerbi.microsoft.com/desktop).
2. Ensure the `cleaned_data.csv` is in the same path or refresh the data source.
3. View individual tabs named "Q1", "Q2", etc.


## ✅ Status
- [x] Data Cleaned
- [x] Visuals Created
- [x] Dashboard Saved in `.pbix` Format
- [x] Project Documented for GitHub
      

# Data Cleaning Steps

## Objective:
Clean the retail dataset before performing analysis.

## Steps:

1. **Remove Invalid Quantities**
   - Condition: `Quantity >= 1`
   - Reason: Negative or zero quantities represent returns or invalid entries.

2. **Remove Invalid Unit Prices**
   - Condition: `UnitPrice >= 0`
   - Reason: Negative unit prices are data entry errors.

3. **Applied via Power Query**:
   - Used `Filter Rows` for both conditions.
   - Ensured that only clean, valid transactions were kept for analysis.

4. **Additional Step**:
   - Extracted the `Year` and `Month` from the `InvoiceDate` to enable time series visuals.



 

