# Retail Analytics Dashboard (Power BI)

This repository contains a Power BI dashboard project developed to support executive decision-making at an online retail company. The dashboard answers four key business questions requested by the CEO and CMO.

---

## 🔧 Tools Used
- Power BI Desktop (.pbix)
- Power Query Editor
- DAX (Data Analysis Expressions)

---

## 📊 Visualizations Overview

### 📈 Q1: Monthly Revenue Trends (2011)
A time series line chart showing revenue for each month in 2011, used to identify seasonal trends and support future forecasting decisions.

### 🌍 Q2: Top 10 Countries by Revenue (Excluding UK)
A stacked bar chart showing top 10 countries (excluding UK) by total revenue and quantity sold. Helps focus on high-performing international markets.

### 👥 Q3: Top 10 Customers by Revenue
A descending bar chart of the top 10 revenue-generating customers, aimed at helping the CMO with customer retention strategies.

### 🌎 Q4: Global Demand by Quantity (Excluding UK)
A filled map showing global demand across all countries (excluding UK), based on quantity sold. Assists the CEO in expansion planning.

---

## 🧹 Data Cleaning Summary

Data was cleaned in Power Query before analysis:
- Removed transactions with `Quantity < 1` (returns or errors)
- Removed records with `UnitPrice < 0`
- Created `Revenue = Quantity * UnitPrice`
- Extracted `Year` and `Month` from `InvoiceDate`

📄 Full steps in: `docs/data_cleaning_steps.md`

---

## ⚙️ Visual Creation Steps

Each question’s visual is in its own `.pbix` file.
Detailed creation instructions are in: `docs/visualization_steps.md`

📁 Files:
- `visuals/` contains Power BI files for each question
- `screenshots/` contains image previews of each visual
- `data/` includes cleaned dataset
- `docs/` holds documentation

---

## 📷 Preview Samples

| Question | Visual |
|---------|--------|
| Q1 | ![](screenshots/Q1.png) |
| Q2 | ![](screenshots/Q2.png) |
| Q3 | ![](screenshots/Q3.png) |
| Q4 | ![](screenshots/Q4.png) |

---

## 🚀 How to Run

1. Clone the repository.
2. Open any `.pbix` file in [Power BI Desktop](https://powerbi.microsoft.com/desktop).
3. Refresh the dataset if prompted (point it to `cleaned_data.csv`).
4. Navigate to the tab named after the question (Q1–Q4).

---

## ✅ Status
- [x] Data Cleaned
- [x] DAX Measures Added
- [x] Visuals Created
- [x] Documentation Completed


# 🧹 Data Cleaning Steps

The following steps were used to clean the dataset before analysis.

## ✅ Conditions Applied:

1. **Remove Invalid Quantities**
   - Filter: Quantity >= 1
   - Reason: Negative values represent returns.

2. **Remove Invalid Unit Prices**
   - Filter: UnitPrice >= 0
   - Reason: Negative prices are data entry mistakes.

3. **Create Revenue Column**
   ```dax
   Revenue = Quantity * UnitPrice

Year = YEAR(InvoiceDate)
Month = FORMAT(InvoiceDate, "MMMM")
MonthNum = MONTH(InvoiceDate)  // for sorting
 


---

## 📄 docs/visualization_steps.md

```markdown
# 📊 Visualization Creation Steps

## Q1: Monthly Revenue Trend (2011)
- Visual: Line Chart
- X-axis: Month
- Y-axis: Revenue
- Filter: Year = 2011
- Sort Month using MonthNum for correct order

## Q2: Top 10 Countries (Excl. UK)
- Visual: Stacked Column Chart
- Axis: Country
- Values: Revenue, Quantity
- Filter: Exclude UK
- Top N filter: Top 10 by Revenue

## Q3: Top 10 Customers by Revenue
- Visual: Bar Chart (Sorted Descending)
- Axis: Customer ID
- Value: Revenue
- Top N filter: Top 10 by Revenue

## Q4: Global Demand by Quantity
- Visual: Filled Map
- Location: Country
- Value: Quantity
- Filter: Exclude UK
![Screenshot 2025-04-08 235524](https://github.com/user-attachments/assets/570bddf6-2755-45cd-814c-9bdd77766a30)
![Screenshot 2025-04-08 235512](https://github.com/user-attachments/assets/9b348da6-b92c-4a12-9c67-3b37008229b5)
![Screenshot 2025-04-08 235457](https://github.com/user-attachments/assets/7447b586-be23-492d-b949-fdd47ae5d69e)
![Screenshot 2025-04-08 235558](https://github.com/user-attachments/assets/93040295-0881-4b3f-8666-08acef7c69a8)
