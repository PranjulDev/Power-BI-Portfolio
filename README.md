# Power BI Portfolio — Pranjul Gupta

## Overview
Power BI Developer portfolio showcasing data modeling, DAX expertise, and business intelligence dashboard development. All projects include interactive visualizations, time intelligence measures, and performance-optimized formulas.

---

## Project 1: Superstore Sales Intelligence Dashboard

**Live Link:** [GitHub Repository](https://github.com/PranjulDev/Power-BI-Portfolio)

### Description
3-page interactive executive dashboard analyzing retail sales performance across 4 years of historical data (2014-2017). Identifies profitability risks and customer segments driving revenue.

### Key Features
- **Page 1 — Executive Sales Overview:** 6 KPI cards with YTD Sales, Sales LY (year-over-year), profit trends, conditional formatting highlighting loss-making categories
<img width="1456" height="833" alt="Executive Sales Overview (Superstore Sales Dashboard)" src="https://github.com/user-attachments/assets/3602212a-ebf5-4dfe-8a50-ff51180a5686" />

- **Page 2 — Profitability Deep Dive:** Scatter analysis of Sales vs Profit by sub-category, matrix heatmap showing profit margins by Region × Category, identification of loss-making products (Tables: -$17.7K)
<img width="1280" height="728" alt="Profitability Deep Dive  (Superstore Sales Dashboard)" src="https://github.com/user-attachments/assets/660ae121-2ea0-4669-bc33-cd925495a4c3" />

- **Page 3 — Customer & Geography Analysis:** Geographic distribution (map visual), top 15 customers by revenue, customer segmentation (Consumer/Corporate/Home Office)
<img width="1297" height="730" alt="Customer   Geography Analysis (Superstore Sales Dashboard)" src="https://github.com/user-attachments/assets/95eb75fa-2a58-4ec7-b4ef-6cc11e63f6b3" />


### Data Model
- Star schema with fact table (Orders) and dimension tables (Dates, Products, Customers, Regions)
- Custom Date Dimension table with Year, Quarter, Month hierarchies
- Proper relationship cardinality configuration

### DAX Measures Used
```dax
Total Sales = SUM(Orders[Sales])
Total Profit = SUM(Orders[Profit])
YTD Sales = TOTALYTD([Total Sales], Date[Date])
Sales LY = CALCULATE([Total Sales], SAMEPERIODLASTYEAR(Date[Date]))
Profit Margin % = DIVIDE([Total Profit], [Total Sales], 0)
Discount Impact = SUMX(Orders, Orders[Sales] * Orders[Discount])
```

### Business Insights Delivered
- Technology category drives most revenue but Tables actively lose $17.7K annually
- Central Region Furniture margin at -1.75% requires immediate pricing review
- 99.37% customer repeat rate indicates strong loyalty
- 37% of orders are loss-making — indicates aggressive discount strategy

### Tools & Techniques
- Power BI Desktop (Data modeling, DAX, visualization)
- Power Query (ETL and data cleaning)
- Time intelligence (TOTALYTD, SAMEPERIODLASTYEAR)
- Conditional formatting with traffic light system
- Drill-through filters between pages

---

## Project 2: HR Analytics Employee Attrition Dashboard

**Status:** In Development

### Description
2-page HR analytics dashboard analyzing employee attrition patterns, compensation trends, and demographic risk factors. Identifies high-risk employee segments and retention patterns.

### Key Features
- **Page 1 — Executive Attrition Overview:** Attrition rate by Department, Job Role, Age Group with conditional color formatting (Red/Orange/Green). Overall attrition: 16.12% (237 of 1470 employees)
<img width="1611" height="905" alt="Executive Attrition Overview (HR Attrition Dashboard)" src="https://github.com/user-attachments/assets/27ead8ec-3c6a-41ba-8f50-0c3df31531f3" />

- **Page 2 — Compensation Analysis:** Salary distribution histogram, tenure vs attrition scatter plot revealing new hires at risk, department-wise salary comparison
<img width="1606" height="903" alt="Compensation Analysis (HR Attrition Dashboard)" src="https://github.com/user-attachments/assets/c66141a9-159f-449c-a11a-12d7e62ff88a" />


### Critical Business Findings
- Sales Representatives: 39.76% attrition (highest risk role)
- Under 25 age group: 39.18% attrition (onboarding/culture fit issue)
- Clear pattern: Low tenure + lower salary = higher attrition
- High earners (>$6500/month): 494 employees

### DAX Measures Used
```dax
Attrition Rate % = DIVIDE([Attrition Count], [Total Employees])
Conditional_Formatting = SWITCH(TRUE(),
    [Attrition Rate %] >= 0.20, "#FF4444",
    [Attrition Rate %] >= 0.10, "#FFD600",
    [Attrition Rate %] < 0.10, "#00B050")
High Earners = CALCULATE(COUNTROWS(HR), HR[MonthlyIncome] > 6500)
```

### Tools & Techniques
- Dynamic color formatting using SWITCH function (performance optimized)
- Scatter plot analysis for correlation detection
- Department-level filtering with cross-page slicer
- Histogram for salary distribution analysis

---

## Skills Demonstrated
- **DAX:** Measures, calculated columns, variables, time intelligence, CALCULATE, FILTER, conditional formatting
- **Data Modeling:** Star schema, relationships, cardinality management, Date dimensions
- **Power Query:** Data transformation, cleaning, merging
- **Visualization:** Chart selection, interactive slicers, drill-through, tooltips
- **SQL:** JOINs, CTEs, Subqueries, GROUP BY, Aggregations, Basic Window Functions
- **Performance:** SWITCH optimization, variable usage, formula efficiency

---

## How to Use
- Download .pbix files from repository
- Open in Power BI Desktop
- Use slicers to filter by Department, Region, Category, Age Group
- Click chart elements for drill-through to detailed pages
- Hover for interactive tooltips

---

## Contact
Available for full-time/freelance Power BI development roles.
Email ID: pranjulgupta25@outlook.com
Resume:(https://linkedin.com/in/pranjul-gupta-003875192)
- Time intelligence and drill-through functionality
- Data storytelling and business insights
