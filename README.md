# 🛍️ 360° Retail Analytics: From Data Cleaning to Insightful Dashboards – End-to-End Data Analytics Project

This is a complete business intelligence and analytics project built using **Excel**, **SQL**, **Python**, and **Power BI**. It analyzes a retail dataset to uncover insights into **sales trends**, **shipping performance**, and **customer segmentation**.

---

## 📌 Project Objective

To build an end-to-end data analytics solution that can:
- Clean and transform raw retail data using Excel
- Perform sales and customer analysis using SQL and Python
- Build RFM-based customer segments using clustering techniques
- Design professional Power BI dashboards for business decision-making

---

## 📂 Dataset Used

Dataset: [Superstore Sales Dataset (Kaggle)](https://www.kaggle.com/datasets/)  
File format: Excel (.xlsx)

**Key Columns:**
- Order ID, Order Date, Ship Date, Customer ID, Segment, City, State, Region, Product Details, Sales, Quantity, Discount, Profit

---

## 🧰 Tools & Technologies Used

| Tool         | Purpose                              |
|--------------|---------------------------------------|
| Excel        | Initial data cleaning and pivoting   |
| MySQL        | SQL-based data exploration & queries |
| Python       | EDA, RFM Analysis, Clustering        |
| Power BI     | Dashboard creation and storytelling  |
| Git & GitHub | Version control and portfolio        |

---

## ✅ Project Workflow

### 1. 📊 Excel (Data Cleaning & Initial Exploration)

- Cleaned the raw data (e.g., fixed date format issues like `mm-dd-yyyy`)
- Used **VLOOKUP**, **Pivot Tables**, and **Filters** for quick summaries
- Verified completeness and removed redundant columns
- Exported cleaned version to be used in SQL and Python

---

### 2. 🛢️ SQL (Exploratory Analysis)

**Environment:** MySQL

Key analysis performed:
- Monthly sales trend by order date
- State and Region-wise sales & profit breakdown
- Product category and sub-category performance
- Average delivery time (ship date – order date)

🧠 *Advanced queries*:  
Used `JOIN`, `GROUP BY`, `DATE_FORMAT`, `CTE`, `RANK()` and `CASE` to prepare intermediate summaries for dashboards.

---

### 3. Python (EDA & Customer Segmentation)

**Platform:** Jupyter Notebook

- Imported cleaned dataset using Pandas
- Created RFM (Recency, Frequency, Monetary) table
- Applied **KMeans clustering** after interpreting **Elbow Method**
- Visualized clusters using **Seaborn** and **Matplotlib**
- Labelled customers into: **Best**, **Average**, **Churned**, etc.

---

### 4. 📊 Power BI (Dashboard Building)

Built **three interactive dashboards** using cleaned data and SQL summaries:

#### 🔹 Sales Insights Dashboard
- Total Sales, Profit, Quantity, Avg Discount KPIs
- Monthly trend line chart
- Category/Sub-category bar charts
- Region and State map visual

#### 🔹 Shipping Analysis Dashboard
- Shipping mode distribution
- Avg delivery time trend
- Region-level shipping delay comparisons
- Product categories causing delivery delays

#### 🔹 Customer Segmentation Dashboard
- RFM metric cards
- Segment filter with customer count
- Cross-visual interactions for detailed filtering

✅ Features Implemented:
- DAX measures for KPIs
- Drill-downs and slicers
- Navigation buttons to switch between dashboards

---

## 💡 Key Insights

- **Top-performing segments**: Corporate segment dominates high-profit states.
- **Shipping**: Second Class shipping mode has higher delays in Southern regions.
- **Customer Segments**: ~25% of customers fall under high-frequency & high-spending cluster – loyal base for campaigns.
- **Profitability Issues**: Discounts >20% often lead to negative profits in certain sub-categories like Tables.

---


