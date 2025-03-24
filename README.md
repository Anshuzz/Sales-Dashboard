# 📊 Tableau Sales Performance Dashboard

## 🚀 Overview
The **Tableau Sales Performance Dashboard** is an interactive and data-driven visualization tool designed to help businesses analyze sales metrics, track trends, and compare product performance. This project provides key insights into year-over-year sales, product subcategories, and weekly trends, enabling data-driven decision-making.

## 🎯 Features
✅ **KPI Overview** – Displays total sales, profits, and quantities for the current and previous year.  
✅ **Sales Trends Analysis** – Visualizes monthly sales trends, highlighting peak and low-performing months.  
✅ **Product Subcategory Comparison** – Compares sales performance across different product categories.  
✅ **Weekly Sales & Profit Analysis** – Tracks weekly trends and highlights above/below-average performance.  
✅ **Interactive Filtering** – Allows dynamic exploration of data with filters on time, region, and product categories.  

## 🛠️ Tech Stack
- **Tableau** – Data visualization and dashboard creation  
- **SQL (MySQL/PostgreSQL)** – Data extraction and transformation  
- **Python (Pandas, NumPy)** – Data preprocessing and cleaning  
- **CSV & Database Integration** – Supports both file-based and SQL-based data sources  

---

## 📂 Dataset Details
The dataset includes sales transactions with the following key columns:  

| Column Name          | Description |
|----------------------|-------------|
| `order_id`          | Unique identifier for each order |
| `order_date`        | Date of the transaction |
| `product_category`  | Main category of the product |
| `product_subcategory` | Subcategory of the product |
| `sales`             | Revenue generated from the sale |
| `profit`            | Profit earned from the sale |
| `quantity`          | Number of units sold |
| `region`            | Geographical region of the sale |
| `customer_id`       | Unique identifier for the customer |

---

## 📊 Tableau Dashboards
### 🔹 **Sales Dashboard**
- Provides an **overview of sales performance** for the past and current year.
- Displays **KPI metrics** like **total sales, profit, and quantity**.
- Identifies **monthly sales trends** and highlights **best/worst-performing months**.

### 🔹 **Customer Dashboard**
- Analyzes **customer purchase behavior** based on historical data.
- Identifies **top-performing customers** and segments them by spending patterns.
- Provides insights into **regional sales performance**.

---

## ⚙️ Installation & Usage

### 🔽 **1. Download Dataset**
- Download the dataset in **CSV format** or connect directly to a **SQL database**.

### 🛠 **2. Data Preprocessing (Optional)**
- If needed, clean and preprocess data using **Python**:

```python
import pandas as pd

# Load dataset
df = pd.read_csv("sales_data.csv")

# Convert date columns to datetime format
df["order_date"] = pd.to_datetime(df["order_date"])

# Fill missing values
df.fillna({"profit": 0, "quantity": 1}, inplace=True)

# Generate additional columns for analysis
df["year"] = df["order_date"].dt.year
df["month"] = df["order_date"].dt.month
df["week"] = df["order_date"].dt.strftime('%Y-W%U')

# Save cleaned dataset
df.to_csv("cleaned_sales_data.csv", index=False)

print("✅ Data preprocessing complete. Cleaned file saved as 'cleaned_sales_data.csv'.")
