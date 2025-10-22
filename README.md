# 📊 Sales Analytics Project
> End-to-end data analytics project using SQL, Python, and Power BI — transforming raw e-commerce data into business insights.


This repository demonstrates a complete **end-to-end data analytics workflow**, from raw transactional data to interactive visual insights.  
The project combines **SQL (data modeling)**, **Python (analysis)**, and **Power BI (visualization)** to uncover business performance, customer behavior, and sales trends.

---

## 🚀 Project Overview

The goal of this project was to:
- Design a repeatable data pipeline from raw Olist e-commerce data  
- Model and aggregate sales data using SQL (SQLite)  
- Create visually clean and intuitive dashboards in Power BI  
- Derive actionable insights for sales and marketing teams  

This project is a **portfolio showcase** of practical data analytics, combining technical accuracy with visual storytelling.

---

## 🧠 Tech Stack

| Area | Tool / Technology |
|------|--------------------|
| Data Processing & Modeling | SQL (SQLite) |
| Data Exploration & Validation | Excel |
| Data Visualization | Power BI |
| Version Control & Documentation | Git, GitHub |
| Supplementary Analysis | Jupyter Notebook (Python) |

---

## 🗂️ Repository Structure
```
Portfolio-Analytics/
│
├── data_raw/ # Original Olist datasets
│├── olist_customers_dataset.csv
│├── olist_orders_dataset.csv
│└── ... other CSV files
│
├── data_processed/ # Reserved for processed or transformed data outputs.
│└── README.md
│
├── sql/ # SQLite database and SQL queries
│├── data.sqlite
│└── README.md
│
├── notebooks/ # Exploratory and SQL validation notebooks
│├── eda.ipynb
│└── sql_analysis.ipynb
│
├── powerbi/ # Power BI reports and visuals
│├── portfolio_project_olist - Newest.pbix
│├── Overview.png
│├── Daily.png
│├── Customers.png
│└── Products.png
│
└── docs/ # Detailed documentation
└── project_documentation.md
│
├── .gitignore
└── README.md
```
---

## 📈 Power BI Dashboards

The report is divided into four pages, each focusing on a different business perspective:

### 1️⃣ Overview
- KPIs: **Total Sales**, **Total Orders**, **Avg Revenue per Order**  
- Trend visuals: monthly and annual performance  
- Filters: Year, Month  

### 2️⃣ Daily Trends
- KPIs: **Total Revenue**, **Total Orders**, **Avg Daily Orders**, **Avg Daily Revenue**
- Combo chart: **Orders vs Revenue (Daily)**  
- Bar chart: **Revenue by Weekday**  
- Hierarchical slicer: Year → Month → Day  

### 3️⃣ Customers
- KPIs: **Total Customers**, **Avg Revenue per Customer**, **Top 10 Customers Revenue %**  
- Bar chart: **Top 10 Customers by Revenue**  
- Table: **Customer Orders, Revenue, and Avg/Order**  

### 4️⃣ Products
- KPIs: **Top 10 Products Revenue**, **Total Products**, **Avg Revenue per Product**  
- Bar chart: **Top 10 products by revenue**
- Bar chart: **Revenue and Customers by Category**
- Donut chart: **Revenue Share by Category**  


---

## 🔍 Key Insights

### 💰 Revenue Trends
- Peak sales in **March–May 2018**
- Clear seasonal pattern

### 🕒 Weekly Behavior
- **Monday** generates the highest daily revenue  
- **Weekends** show ~25-30% lower sales activity

### 👥 Customer Insights
- Most customers make **≤5 purchases**, suggesting potential for loyalty programs

### 📦 Product Insights
- **Health & Beauty** and **Watches & Gifts** dominate sales
- Mid-tier categories such as **Sports & Leisure** and **Computers & Accessories** remain stable.
- **Garden Tools** and **Auto** show potential growth opportunities

---

## 📘 Full Project Documentation

For detailed explanations, SQL scripts, and Power BI report design breakdowns, see the full documentation:

👉 [View Full Documentation](docs/project_documentation.md)

--- 

Data source: [Olist E-commerce Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)