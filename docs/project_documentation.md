# 📘 Project Documentation

This folder contains detailed documentation for the entire analytics project.

## 📑 Contents
1. Project Overview  
2. Data Description and Sources  
3. SQL Modeling and Transformations  
4. Exploratory Data Analysis (EDA)  
5. Power BI Dashboard Design  
6. Insights Summary  
7. Repository Structure  
8. Key Learnings and Takeaways  
9. Future Improvements  

---

# 💼 Power BI Sales Analytics Project – Full Documentation

## 1️⃣ Project Overview

This project demonstrates a complete **end-to-end data analytics workflow**, from raw data to visual insights, using **SQL, Python, and Power BI**.  
The goal was to transform, model, and visualize business sales data to reveal key performance indicators (KPIs), customer patterns, and revenue trends.

**Key objectives:**
- Design a repeatable data pipeline from raw transactional data.
- Model and aggregate sales data using SQL.
- Create intuitive, interactive Power BI dashboards.
- Derive actionable insights for management and decision-making.

**Tools & Technologies**

| Area | Tool / Technology |
|------|--------------------|
| Data Cleaning & Aggregation | SQL (SQLite) |
| Data Exploration & Validation | Excel |
| Data Visualization | Power BI |
| Documentation & Version Control | Git, GitHub |
| Supplementary Analysis | Jupyter Notebook (Python) |

---

## 2️⃣ Data Description and Sources

The dataset is derived from the **Olist e-commerce dataset**, which simulates transactional online sales data.  
Multiple SQL-based views were created to support efficient analysis.

**Views used in the project:**
- `v_fact_sales` – core transaction-level sales data  
- `v_sales_daily` – aggregated daily sales  
- `v_sales_monthly` – aggregated monthly metrics  
- `v_customer_revenue` – customer-level total revenue  
- `v_top_products_per_customer` – top products and categories per customer  

**Main columns:**

| Column | Description | Example |
|---------|--------------|----------|
| `order_id` | Unique order identifier | 00123 |
| `customer_id` | Unique customer | CUST-456 |
| `product_id` | Product identifier | PROD-322 |
| `order_day` | Order date | 2018-03-21 |
| `revenue` | Total order value | 254.90 |
| `orders` | Number of orders in grouping | 3 |
| `category_en` | Product category (EN) | Furniture |

**Dataset size:** ~112K rows  
**Date range:** 2016–2018  

---

## 3️⃣ SQL Modeling and Transformations

The data was modeled and transformed in **SQLite**, producing several reusable *views* for Power BI integration.  
These transformations ensured consistency, performance, and accuracy across all reports.

**Key transformations:**
- Merging orders, items, and payment data into a unified transactional view (`v_fact_sales`).  
- Aggregating data by day and by month (`v_sales_daily`, `v_sales_monthly`).  
- Calculating per-customer revenue and order counts (`v_customer_revenue`).  
- Identifying top-selling products per customer segment (`v_top_products_per_customer`).  

**Example SQL transformation:**
```
CREATE VIEW v_fact_sales AS
SELECT
    oi.order_id,
    oi.order_item_id,
    o.customer_id,
    oi.product_id,
    DATE(o.order_purchase_timestamp) AS order_date,
    oi.price,
    oi.freight_value
FROM order_items AS oi
JOIN orders AS o
  ON oi.order_id = o.order_id;
```

---

## 4️⃣ Exploratory Data Analysis (EDA)

Before dashboard creation, **EDA was performed using Python (Jupyter Notebooks)** to validate and understand the Olist dataset.  
This step ensured clean data and consistent metrics prior to Power BI integration.

**Focus areas:**
- Identified missing or inconsistent data.  
- Reviewed sales distribution, order frequency, and customer activity.    

EDA confirmed the dataset’s reliability for accurate reporting and visualization.

---

## 5️⃣ Power BI Dashboard Design

The **Power BI report** was built with a **dark-themed teal gradient background** for clarity and professional appearance.  
It consists of four analytical pages — each focusing on a specific business dimension.

### 1️⃣ Overview Dashboard
**KPIs:** Total Sales, Total Orders, Average Revenue per Order  
**Visuals:**
- Line + column combo chart showing monthly and yearly trends  
- KPI cards for sales metrics  
**Filters:** Year, Month  

### 2️⃣ Daily Dashboard
**KPIs:** Total Revenue, Total Orders, Avg Daily Orders, Avg Daily Revenue
**Visuals:**
- Combo chart: Orders vs. Revenue (daily trend)  
- Bar chart: Revenue by Weekday  
**Filters:** Year → Month → Day  
📈 *Insight:* Monday–Wednesday consistently generate the highest daily revenue.

### 3️⃣ Customer Dashboard
**KPIs:** Total Customers, Avg Revenue per Customer, Top 10 Customers Revenue %  
**Visuals:**
- Bar chart: Top 10 customers by revenue  
- Table: Orders, Revenue, Avg/Order per customer  

### 4️⃣ Product Dashboard
**KPIs:** Top 10 Product Revenue, Total Products, Avg Revenue per Product  
**Visuals:**
- Bar chart: Top 10 products by revenue  
- Donut chart: Revenue share by category  
- Category-wise breakdown table  
📦 *Insight:* “Health & Beauty” & "Watches & Gifts" dominate total revenue.

---

## 6️⃣ Insights Summary

📊 **Revenue Trends**  
- Peak sales in **March–May 2018**.
- Clear seasonality pattern — activity declines sharply towards the end of the year (September onwards).
- 2018 outperforms earlier years in both total sales and order volume.

🕒 **Daily & Weekly Patterns**  
- Monday shows the highest average revenue.  
- Weekend sales ~25-30% lower than weekdays.  

👥 **Customer Insights**   
- Most customers place ≤5 orders — opportunity for loyalty strategies.  

📦 **Product Performance**  
- **Health & Beauty**, **Watches & Gifts**, categories generate most revenue.  
- Mid-tier categories include **Sports & Leisure**, **Computers & Accessories**, and **Furniture & Decor**, showing stable contribution levels.
- **Garden Tools**, **Auto**, and **Cool Stuff** underperform and represent potential areas for growth or product diversification.

---

## 7️⃣ Repository Structure
```
Portfolio-Analytics/
│
├── data_raw/                  # Original Olist datasets
│├── olist_customers_dataset.csv
│├── olist_orders_dataset.csv
│└── ... other CSV files
│
├── data_processed/            # Reserved for processed or transformed data outputs.
│└── README.md
│
├── sql/                       # SQLite database and SQL queries
│├── data.sqlite
│└── README.md
│
├── notebooks/                 # EDA and SQL validation
│├── eda.ipynb
│└── sql_analysis.ipynb
│
├── powerbi/                   # Power BI reports and visuals
│├── portfolio_project_olist - Newest.pbix
│├── Overview.png
│├── Daily.png
│├── Customers.png
│└── Products.png
│
└── docs/                      # Documentation
   └── project_documentation.md
│
├── .gitignore
└── README.md
```

---

## 8️⃣ Key Learnings and Takeaways

- **Data modeling:** Converting raw data into structured fact/dimension-style views improves performance and analytical flexibility.  
- **SQL proficiency:** Reusable views and aggregations simplify Power BI integration.  
- **Visualization design:** Consistent color palette, clear KPIs, and hierarchy-based slicers improve readability.  
- **Iterative workflow:** Building SQL + EDA foundations first ensures Power BI accuracy.  
- **Storytelling:** Combining metrics with visuals enhances communication of insights.

---

## 9️⃣ Future Improvements

Planned or potential next steps for further enhancement:

1. **Automated Power BI refresh** via Power BI Service or Python scheduling.  
2. **Forecasting models** To predict future monthly revenue.  
3. **Regional segmentation** to analyze sales by state or region.    
4. **Power BI Web App publication** for interactive sharing.

