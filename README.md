# 📊 DAX & Data Visualization Using Power BI
This project demonstrates data analysis, DAX calculations, and interactive dashboard creation using Power BI.
A Power BI dashboard designed to transform raw business data into interactive visual insights using DAX calculations and data visualization techniques for better decision-making.

## 🎯 Project Overview

### * **Business Problem:** 
Businesses often struggle to interpret large datasets and identify performance trends quickly. This dashboard centralizes key metrics into interactive reports for efficient analysis.

### * **Objective:** 
 Monitor KPIs
 Analyze performance trends
 Compare business metrics
 Support data-driven decisions

### * **Target Audience:** 
 Business Analysts
 Sales Operations Teams
 Management & Decision Makers
 Data Analytics Learners

## 🗃️ Data Sources & Architecture

### * **Source Systems:**
 Local Excel Files (.xlsx) were used as the primary data source for importing and transforming the dataset into Power BI. 
 Data was loaded and prepared through Power Query Editor before creating relationships and measures. 

### * **Data Volume:**
* Time frame Covered: Based on the dataset available in the workbook (mention actual period if known, e.g., Jan 2024 – Dec 2025). 
* Approximate Row Count: Add the total rows loaded into the model (example: ~10,000–50,000 rows depending on your dataset). 
* Multiple tables were integrated for analysis and reporting. Time Period: (Update based on dataset)

### * **Storage Mode:** 
* Import Mode 
* Data is imported into the Power BI model and stored inside the .pbix file. 
* Provides faster report performance and supports full Power BI modeling features.

## ⚙️ Data Transformation (ETL)

### 1. Extract
Imported multiple source tables into Power BI. 

### 2. Transform

Performed data cleaning and preparation:
  1.Handled missing values 
  2.Removed duplicates 
  3.Corrected data types
  4.Created custom columns: 
    Profit Margin % 
    Profit Status 
  5.Applied conditional columns 
  6.Merged tables using Order ID 
  7.Grouped and aggregated data 
  8.Standardized values 

### 🛠️ Load

  A.Loaded transformed tables into the Power BI data model for analysis and reporting.
  B.Imported cleaned and transformed datasets using Power Query.
  C.Established relationships between tables to create an optimized data model.
  D.Ensured data integrity and prepared the model for DAX calculations and dashboard visualization.
  E.Validated data consistency after loading into the Power BI environment.


## 🛠️ Tools & Technologies

- **Power BI Desktop**
- **DAX (Data Analysis Expressions)**
- **Power Query**
- **Data Modeling**
- **Interactive Visualizations**


## 🧠 Data Model & DAX

* **Model Type:** 
Star Schema (Recommended Data Model Design)

* **Fact Tables:** 
  1.List of Orders - Contains order details and customer location information.
  2.Order Details - Includes product sales transaction s and quantities.
  3.Sales Target - Stores target values for performance comparison.
  4.Order Profit - Contains profit values for profitability  analysis.

## DAX Calculations
 ### Category Type
```DAX
Category Type ='Order Details'[Category] & " - " & 'Order Details'[Sub-Category]
```

### Revenue Per Order
```DAX
Revenue Per Order = 
'Order Details'[Amount] * 'Order Details'[Quantity]
```

### Sales Category
```DAX
Sales Category = 
IF(
    'Order Details'[Amount] >
    AVERAGE('Order Details'[Amount]),
    "Above Average",
    "Below Average"
)
```

### Order Count 
```DAX
Order Count = COUNT('Order Details'[Order ID])
```

### Average Profit in Delhi
```DAX
Average Profit in Delhi = 
CALCULATE(
    AVERAGE('Order Details'[Profit]),
    'List of Orders'[City] = "Delhi"
)
```

### YTD Sales
```DAX
YTD Sales = 
TOTALYTD(
    SUM('Order Details'[Amount]),
'List of Orders'[Order Date])
```

### Total Sales
```DAX
Total Sales =SUM('Order Details'[Amount])
```

### Total Target 
```DAX
Total Target =SUM('Sales Target'[Target])
```

### Profit-Margin
```DAX
Profit-Margin = 
DIVIDE(
    SUM('Order Details'[Profit]),
    SUM('Order Details'[Amount]),
    0
)
```

### Max Profit Margin
```DAX
Max Profit Margin = 
(
MAX('Order Details'[Profit])
)
```

### Order Count
```DAX
Order Count =
DISTINCTCOUNT('Order Details'[Order ID])
```


## 🚀 Dashboard Features

### KPI Cards
- Total Sales
- Total Profit
- Total Quantity
- Total Target Achievement

### Visualizations Included
✔ Monthly Sales and Total Sales by Profit  
✔ Minimum Target and Count of Order ID by Target  
✔ Total Target vs Total Sales by Sub-Category  
✔ Sales Breakdown by Category  
✔ Profit Margin by Sub-Category  
✔ Treemap of Sales by Category & Sub-Category  
✔ Quantity vs Profit Scatter Analysis  
✔ Monthly Sales Trend Analysis  
✔ City-wise Sales Map  
✔ State-wise Order Distribution  

### Interactive Features

  Cross-filtering
  Dynamic visuals
  Drill-through capability
  Interactive exploration

### Design Theme
  Accessible Power BI theme
  Clean business-oriented layout

## 💡 Key Insights

### Trend A
Performance trends can be identified quickly through KPI tracking and visual comparison.

### Trend B
Interactive filtering highlights category-level and regional variations.

### Recommendation
Use KPI monitoring and drill-down analysis to improve decision-making and optimize business outcomes.

Focus marketing efforts on high-performing categories.
- Improve target planning for underperforming segments.
- Expand sales activities in strong-performing cities.
- Monitor profit margin regularly to improve profitability.

## 🚀 How To Use

### Trend A
Performance trends can be identified quickly through KPI tracking and visual comparison.

### Trend B
Interactive filtering highlights category-level and regional variations.

### Recommendation
Use KPI monitoring and drill-down analysis to improve decision-making and optimize business outcomes.
   Power BI Desktop
   Power Query
   DAX
   Data Modeling
  
## 📌 Author
### B Sugantha
Aspiring Data Analyst | Power BI | Data Visualization | DAX
