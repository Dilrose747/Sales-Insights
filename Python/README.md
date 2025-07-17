# Python Analysis: Customer Segmentation & Sales Insights

This section contains the full Python-based exploratory data analysis and customer segmentation for the **UK Online Retail Dataset**.

The analysis was performed using **Jupyter Notebook**, and covers a wide range of steps from data cleaning to advanced clustering using RFM metrics and KMeans.

---

## Key Sections Covered

### 1. Data Cleaning & Preparation
- Standardized column names.
- Converted date columns to datetime format.
- Removed unnecessary columns (`row_id`, `postal_code`).

### 2. Exploratory Data Analysis (EDA)
- Distribution plots for sales, profit, and discounts.
- Order counts by category, region, and customer segment.
- Relationship plots: `Sales vs Profit`, `Discount vs Profit`.
- Correlation heatmap and monthly sales trend.

### 3. Product & Category Insights
- Top-selling products.
- Sales and profit by category.
- Sales performance by region and customer segment.

### 4. Shipping Analysis
- Calculated average shipping delays by shipping mode.

---

## Customer Segmentation (RFM + KMeans)

### RFM Metrics Computed
- **Recency**: Days since last purchase.
- **Frequency**: Number of unique orders.
- **Monetary**: Total spend.

### Clustering Process
- RFM values standardized using `StandardScaler`.
- Elbow method used to determine optimal number of clusters.
- KMeans applied to segment customers into 3 groups:
  - **Best Customers**
  - **Loyal Potential**
  - **Lost Customers**

### Cluster Insights
- Bar plots show the distribution of customers across segments.
- RFM summary statistics explain each cluster’s behavior.

---

## File Overview

| File | Description |
|------|-------------|
| `customer_segmentation_analysis.ipynb` | Complete notebook with code, plots, and interpretation |
| `python/` | Folder containing the Python code and this README file |

---

## Technologies Used
- **Pandas, NumPy** – Data manipulation
- **Matplotlib, Seaborn** – Data visualization
- **Scikit-learn** – Clustering with KMeans

---

## Author
- Mohamed Dilrose P M

