# Data-Analytics-Portfolio---Nova-Retail-Group
“Advanced SQL analysis of retail sales data using Databricks. Demonstrates CTEs, window functions, and business intelligence insights from 2,500 transactions across 500 customers.”
# Nova Retail Group Database Analysis 📊

A comprehensive SQL and data analytics project analyzing retail sales, customer behavior, and product performance. Built using **Databricks SQL** and **Python**, this project demonstrates advanced database querying, data transformation, and business intelligence capabilities.

**Student:** Tshegofatso Motaung  
**Project Date:** April 2026  
**Skill Level:** Advanced SQL & Business Analytics

-----

## 🎯 Project Overview

Nova Retail Group is a growing South African retail company operating across multiple regions through both physical stores and online channels. This project analyzes **2 years of transactional data** to uncover insights about:

- **Customer Behavior:** Segmentation, loyalty, lifetime value
- **Sales Performance:** Revenue trends, channel comparison, regional analysis
- **Product Portfolio:** Profit margins, underperforming items, category analysis
- **Pricing Strategy:** Discount effectiveness and impact on profitability

### Key Metrics

- **Total Records:** 4,030+ transactions across 4 tables
- **Time Period:** 2023-2024
- **Regions:** North, South, East, West
- **Product Categories:** Electronics, Home Appliances, Lifestyle Goods
- **Sales Channels:** Online, Store

-----

## 📊 Dataset Overview

|Table                |Records|Purpose                                |
|---------------------|-------|---------------------------------------|
|**Products**         |30     |Product catalog with pricing & costs   |
|**Customers**        |500    |Customer demographics & metadata       |
|**Sales**            |2,500  |Transaction details & financial metrics|
|**Customer_Feedback**|1,000  |Ratings, satisfaction, NPS scores      |

### Data Relationships

```
Customers (1) ──→ (Many) Sales (Many) ──→ Products (1)
                      ↓
                Customer_Feedback
```

-----

## 🚀 Quick Start

### Prerequisites

- Databricks Workspace Access
- SQL IDE (DBeaver, VS Code with SQL extension)
- Python 3.8+ (for data analysis)
- Git for version control

### Setup Instructions

1. **Clone this repository**
   
   ```bash
   git clone https://github.com/zibonelemabaso-jpg/nova-retail-analysis.git
   cd nova-retail-analysis
   ```
1. **Import CSV Data to Databricks**
   
   ```sql
   -- Option 1: Using COPY INTO
   COPY INTO warehouse.default.products FROM 'file:/data/Products.csv'
   FILE_FORMAT = (TYPE = 'CSV', HEADER = TRUE, INFER_SCHEMA = TRUE)
   
   COPY INTO warehouse.default.customers FROM 'file:/data/Customers.csv'
   FILE_FORMAT = (TYPE = 'CSV', HEADER = TRUE, INFER_SCHEMA = TRUE)
   
   COPY INTO warehouse.default.sales FROM 'file:/data/Sales.csv'
   FILE_FORMAT = (TYPE = 'CSV', HEADER = TRUE, INFER_SCHEMA = TRUE)
   ```
1. **Verify Data Import**
   
   ```sql
   SELECT 'Products' AS TableName, COUNT(*) AS Records FROM products
   UNION ALL
   SELECT 'Customers', COUNT(*) FROM customers
   UNION ALL
   SELECT 'Sales', COUNT(*) FROM sales
   UNION ALL
   SELECT 'Customer_Feedback', COUNT(*) FROM customer_feedback;
   ```
1. **Run Queries**
- See `QUERIES.sql` for complete query library
- Execute queries in sequential order (Part 1 → Part 5)

-----

## 📁 Repository Structure

```
nova-retail-analysis/
├── README.md                          # This file
├── PROJECT_DOCUMENTATION.md           # Detailed findings & insights
├── SQL_FUNDAMENTALS.md                # SQL concepts explained
├── DATABRICKS_GUIDE.md                # Databricks implementation
├── QUERIES.sql                        # Complete SQL queries (organized)
├── data/
│   ├── Products.csv
│   ├── Customers.csv
│   ├── Sales.csv
│   └── Customer_Feedback.csv
├── notebooks/
│   ├── 01_Data_Exploration.sql
│   ├── 02_Basic_Analysis.sql
│   ├── 03_Advanced_Analytics.sql
│   └── 04_Executive_Summary.sql
└── reports/
    ├── Sales_Analysis_2024.md
    ├── Customer_Insights.md
    └── Product_Portfolio_Review.md
```

-----

## 🔍 Key Findings (Executive Summary)

### Finding 1: Customer Satisfaction Drives Loyalty ⭐

- **Highly satisfied customers (4-5 stars)** average **5.04 orders/customer**
- **Less satisfied customers (1-3 stars)** average **4.96 orders/customer**
- **Neutral customers** average **6.11 orders/customer**
- **Insight:** Satisfaction correlates with repeat purchases; focus on service quality ROI

### Finding 2: Discounts Erode Profitability 💰

|Discount Band|Total Sales|Profit Margin|
|-------------|-----------|-------------|
|0%           |R3.9M      |72.25%       |
|1-10%        |R3.5M      |62.17%       |
|11-20%       |R1.8M      |40.51%       |
|21-30%       |R760K      |24.23%       |

**Insight:** Every 10% discount increase reduces profit margins by ~10-15%; strategic discounting recommended

### Finding 3: Regional Performance Variance 🗺️

1. **North Region:** R2.92M (731 orders) - Top performer
1. **East Region:** R2.49M (600 orders)
1. **South Region:** R2.36M (595 orders)
1. **West Region:** R2.22M (574 orders)

**Insight:** 32% revenue gap between #1 and #4; investigate North’s success factors

### Finding 4: Underperforming Products Need Strategy Shift 📦

Bottom 5 products by revenue: Water Bottle, Scented Candles, Yoga Mat, Electric Kettle, Sunglasses

- Despite low sales, many have good ratings (3.7-4.0 stars)
- **Recommendation:** Reposition through marketing/bundling rather than discontinue

### Finding 5: Year-over-Year Growth is Positive 📈

- **2023 Sales:** R4.69M
- **2024 Sales:** R5.29M
- **Growth Rate:** +12.75%

-----

## 💻 Technologies & Skills Demonstrated

### SQL Fundamentals Used

✅ **Querying:** SELECT, WHERE, ORDER BY, LIMIT  
✅ **Aggregation:** SUM, COUNT, AVG, MIN, MAX  
✅ **Grouping:** GROUP BY, HAVING clauses  
✅ **Joining:** INNER JOIN, LEFT JOIN (multiple joins)  
✅ **Window Functions:** ROW_NUMBER(), RANK(), PARTITION BY  
✅ **CTEs:** WITH clauses for complex queries  
✅ **Subqueries:** Nested and correlated subqueries  
✅ **Date Functions:** EXTRACT(), YEAR(), MONTH()  
✅ **String Functions:** CONCAT(), CASE statements  
✅ **Advanced:** NULLIF for division by zero safety

### Tools & Platforms

- 🔷 **Databricks SQL** - Distributed data warehouse
-----

## 📚 Query Complexity Breakdown

|Section   |Queries |Complexity     |Focus                                   |
|----------|--------|---------------|----------------------------------------|
|**Part 1**|5       |⭐ Beginner     |Basic SELECT, WHERE, GROUP BY           |
|**Part 2**|5       |⭐⭐ Intermediate|JOINs, aggregations, date functions     |
|**Part 3**|5       |⭐⭐⭐ Advanced   |CTEs, window functions, subqueries      |
|**Part 4**|3       |⭐⭐⭐ Advanced   |Business intelligence, complex joins    |
|**Part 5**|Insights|⭐⭐⭐⭐ Expert    |Multi-table analysis, strategic thinking|

-----

## 🎓 Learning Outcomes

By completing this project, you’ll master:

1. **Database Design** - Understanding relational schemas and data normalization
1. **Query Optimization** - Writing efficient queries that execute at scale
1. **Data Analysis** - Extracting actionable insights from raw data
1. **Business Intelligence** - Translating technical findings into strategic recommendations
1. **Cloud Data Platforms** - Working with Databricks and distributed computing
1. **Data Storytelling** - Communicating complex analysis to stakeholders

-----

## 📖 Documentation Files

- **<PROJECT_DOCUMENTATION.md>** - Deep dive into findings, queries, and recommendations
- **<SQL_FUNDAMENTALS.md>** - Explanations of SQL concepts with examples
- **<DATABRICKS_GUIDE.md>** - Setup and optimization tips for Databricks
- **<QUERIES.sql>** - Complete query library organized by section

-----

## 🔗 Query Examples

### Example 1: Top Customers by Revenue

```sql
SELECT c.CustomerID, 
       CONCAT(c.FirstName, ' ', c.LastName) AS CustomerName,
       SUM(s.TotalSales) AS TotalSpent
FROM customers c
INNER JOIN sales s ON c.CustomerID = s.CustomerID
GROUP BY c.CustomerID, c.FirstName, c.LastName
ORDER BY TotalSpent DESC
LIMIT 10;
```

### Example 2: Product Performance with Window Functions

```sql
WITH ProductSales AS (
  SELECT p.Category, p.ProductName, SUM(s.UnitPrice) AS TotalSales
  FROM products p 
  JOIN sales s ON p.ProductID = s.ProductID
  GROUP BY p.Category, p.ProductName
)
SELECT *, ROW_NUMBER() OVER (PARTITION BY Category ORDER BY TotalSales DESC) AS Rank
FROM ProductSales;
```

### Example 3: Year-over-Year Growth Analysis

```sql
WITH YearlySales AS (
  SELECT YEAR(OrderDate) AS SalesYear, SUM(UnitPrice) AS TotalSales
  FROM sales
  WHERE YEAR(OrderDate) IN (2023, 2024)
  GROUP BY YEAR(OrderDate)
)
SELECT 
  MAX(CASE WHEN SalesYear = 2023 THEN TotalSales END) AS Sales_2023,
  MAX(CASE WHEN SalesYear = 2024 THEN TotalSales END) AS Sales_2024,
  ((MAX(CASE WHEN SalesYear = 2024 THEN TotalSales END) - 
    MAX(CASE WHEN SalesYear = 2023 THEN TotalSales END)) / 
   MAX(CASE WHEN SalesYear = 2023 THEN TotalSales END)) * 100 AS GrowthPercent
FROM YearlySales;
```

-----

## 💡 Key Recommendations

### 1. Enhance Customer Satisfaction Programs

- Focus on service quality, faster delivery, product reliability
- Target top 25% of customers with VIP experiences
- Expected ROI: +5-10% repeat purchase rate

### 2. Optimize Discount Strategy

- Limit discounts to 0-10% range
- Use strategic discounting only for seasonal promotions
- Test discount elasticity for each product category
- Expected impact: +8-12% profit margin improvement

### 3. Product Portfolio Review

- Investigate success factors in North region
- Reposition low-revenue/high-rating products via marketing
- Consider bundling underperformers with bestsellers
- Discontinue only truly unprofitable items

### 4. Regional Expansion

- Analyze North region’s success (32% higher revenue)
- Implement winning strategies in underperforming regions
- Consider market research in West region
- Expected upside: +15-20% in underperforming regions

### 5. Channel Strategy

- Online channel outperforms stores (higher avg order value)
- Invest in online infrastructure and marketing
- Use stores for customer experience and local presence
- Expected impact: Shift 5-10% more volume to online

-----

## 📊 Visualizations & Reports

Check the `/reports` directory for:

- Sales trend analysis (2023-2024)
- Customer segmentation reports
- Product performance dashboards
- Regional comparison charts
- Discount effectiveness analysis

-----

## 🤝 Contributing

This is a student project for portfolio purposes. If you’d like to:

- Add additional analysis
- Improve query performance
- Enhance documentation
- Fix data issues

Please submit a pull request with detailed descriptions.

-----

## 📝 License

This project is for educational purposes. Data is synthetic and created for training.

-----

## 📧 Contact & Questions

**Student:** Zibonele mabaso  
**Email:** zibonelemabaso@gmail.com  
**GitHub:** [zibonelemabaso-jpg](https://github.com/zibonelemabaso-jpg)

-----

## ✨ Acknowledgments

- Nova Retail Group (fictional company for case study)
- Databricks SQL Documentation
- SQL Window Functions Reference
- Data Analytics Bootcamp Curriculum

-----

**Last Updated:** April 2026  
**Status:** Complete ✅
