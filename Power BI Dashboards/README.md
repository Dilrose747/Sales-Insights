## 📊 Power BI Dashboards

The final component of this project involved designing **three fully interactive Power BI dashboards** that transform insights into a business-friendly visual story. Each dashboard is optimized with slicers, custom DAX measures, consistent layout templates, and navigation buttons to create a professional, end-user-ready reporting system.

---

### 🔹 1. **Sales Insights Dashboard**

#### 📌 Objective:
To analyze overall performance trends in sales, profit, and quantity over time, by region, and across product categories.

#### 📈 Key Visuals:
- **KPI Cards** for Total Sales, Profit, Quantity Sold, Total Orders
- **Monthly Sales Trend Line Chart**
- **Regional Sales Map** (Map Visual)
- **Sales by Category & Sub-Category (Bar Chart)**
- **Sales by Segment with % contribution (Donut Chart)**

#### 🧮 DAX Measures Used:
- `Total Sales = SUM(Sales)`
- `Total Profit = SUM(Profit)`
- `Profit Margin = DIVIDE(SUM(Profit), SUM(Sales))`

#### 🧠 Insights:
- Identified peak months and seasonal patterns
- Highlighted most profitable categories and top-selling products
- Compared segment performance and regional contribution

---

### 🔹 2. **Customer Segment Dashboard**

#### 📌 Objective:
To display insights derived from **RFM Segmentation + KMeans Clustering**, highlighting different types of customers based on recency, frequency, and monetary value.

#### 📈 Key Visuals:
- **RFM Cluster Treemap** (Best, Average, Churned Customers, etc.)
- **Sales and Profit by different Segments** using Stacked Bars
- **Line Chart of Sales by Segments over Years**
- **Table of Top 10 Customers by Profit**

#### 🧮 DAX Highlights:
- `Total Customers = DISTINCTCOUNT(Customer ID)`
- `Sales by Segment = CALCULATE(SUM(Sales), Segment Filter)`

#### 🧠 Insights:
- Enables targeting campaigns for high-value customers
- Identifies customers who haven’t purchased recently (churn risk)
- Helps tailor loyalty programs based on behavioral segmentation

---

### 🔹 3. **Shipping Analysis Dashboard**

#### 📌 Objective:
To assess performance across shipping modes, delivery delays, and their impact on customer experience and profit margins.

#### 📈 Key Visuals:
- **Ship Mode-wise Sales and Profit (Grouped Column)**
- **Average Shipping Duration in days (Column Chart)**
- **Number of Customers by Shipment Mode (Treemap)**
- **Line Chart of Number of Shipments over Years**

#### 🧮 DAX Examples:
- `Shipping Duration = DATEDIFF('Order Date', 'Ship Date', DAY)`
- `Avg Shipping Duration = AVERAGEX(Orders, [Delivery Time])`

#### 🧠 Insights:
- Highlights regions or modes with delayed shipments
- Evaluates shipping mode profitability vs delivery speed
- Aids decisions on optimizing logistics costs and delivery strategy

---

### 🔗 Dashboard Navigation

Each dashboard includes **interactive buttons at the top** that allow users to switch between dashboards easily, improving UX:

- `Go to Sales Overview Dashboard`
- `Go to Customer Insights Dashboard`
- `Go to Shipping Insights Dashboard`

This was done using **Power BI Bookmarks and Page Navigation Actions** to simulate a web-like navigation experience.

---

### 📁 Power BI File

You can explore the report directly by opening the `.pbix` file in Power BI Desktop:  
🔗 [`Customer-Sales-Segments-Dashboard.pbix`](./Customer-Sales-Segments-Dashboard.pbix)

---

### 🧠 Why This Matters

Power BI bridges technical analysis and business communication. These dashboards were designed to:
- Empower business users to explore data interactively
- Communicate complex analysis (like clustering) in a visually intuitive manner
- Simulate real-world BI project scenarios that drive decision-making

