# 📊 Sales & Profit Analytics Dashboard (Power BI)

An interactive, end-to-end **Power BI** report designed to analyze sales performance, net profitability, commission costs, 
and order trends across multiple product categories, timeframes, and sales representatives.

---

## 📌 Features & Key Capabilities

* **Interactive KPI Metrics:** Executive cards tracking `Total Sales`, `Net Profit`, `Total Commission Cost`, `Total Order Count`, and `YoY Sales Growth %`.
* **Dynamic Bookmark Navigation:** Seamlessly switch between **Chart Views** (e.g., *Category-wise* or *Monthly trends*) and **Table Views** without cluttering the canvas.
* **Report Page Tooltips:** Custom hover tooltips providing instant category breakdowns upon hovering over main data points.
* **Targeted Drill-Through Page (`SalesPerson_Details`):** Allows users to right-click any salesperson's name and drill through to an individual performance breakdown filtered strictly for that rep.
* **Conditional Formatting:** Automated visual callouts highlighting negative net profit transactions in red for quick loss detection.
* **Row-Level Security (RLS):** Configured data security roles using `USERPRINCIPALNAME()` to restrict salesperson visibility to their own performance metrics upon login.

---

## 🛠️ Data Modeling & Transformation

* **Data Cleaning & Standardization (Power Query):**
  * Handled duplicate entries, trimmed hidden whitespace, and removed invalid `null` records across dimension tables.
  * Performed grouping and aggregation on the `Commission` table to ensure **100% unique primary keys**.
* **Data Model Architecture:**
  * Built a star-schema model connecting dimension tables (`Commission`, `Dim_Customer`, `Category`, `Dim_Date`) to the
  * central fact table (`Fact_sales`) via active **1-to-Many (1:*)** relationships.

---

## 📐 Key DAX Measures

```dax
// Total Sales Measure
Total Sales = SUM(Fact_sales[Total Sales])

// Net Profit Measure
Net Profit = SUM(Fact_sales[Net Profit])

// Total Commission Cost
Total Commision Cost = SUM(Fact_sales[Commission Cost])

// YoY Sales Growth %
YoY Sales Growth % = 
DIVIDE(
    [Total Sales] - [Previous Year Sales Amount],
    [Previous Year Sales Amount],
    0
)
```
Dashboard Preview

Add screenshots of your dashboard inside the Images folder and update this section.

Example:

Images/Dashboard.png
📌 Business Insights
Identified top-performing products and categories.
Analyzed sales and profit trends over time.
Compared regional sales performance.
Evaluated customer purchasing behavior.
Monitored key business KPIs for decision-making.
🎯 Learning Outcomes

Through this project, I gained practical experience in:

Power BI Dashboard Development
Power Query ETL Process
DAX Calculations
Data Visualization Best Practices
Business Analytics
Report Optimization
Interactive Reporting

   Author
  Yogaraj M
  Program Analyst | SQL Developer | Aspiring Data Analyst
