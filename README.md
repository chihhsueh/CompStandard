## 📦 Inventory & Vendor Performance Analysis
🧠 Project Overview
Effective inventory and sales management are essential for profitability in the retail and wholesale industry. This project explores a dataset to help businesses minimize losses from inefficient pricing, poor inventory turnover, and vendor dependency.

The goal of this analysis is to provide actionable insights that help identify underperforming brands, optimize vendor relationships, and improve operational efficiency across the supply chain.

🎯 Objectives
This project aims to:

📉 Identify underperforming brands that may require promotional or pricing adjustments

🏆 Determine top vendors contributing to sales and gross profit

📦 Analyze the impact of bulk purchasing on unit costs

🔄 Assess inventory turnover to reduce holding costs and improve efficiency

🚫 Recommend phasing out low-performing vendors

## 📂 Workflow & Thought Process

### **1️⃣ Exploratory Data Analysis**
**Goal:** Understand the structure of the database, assess data quality, and identify useful aggregations.  

**Steps Taken:**
- Connected to the database and listed available tables.
- Inspected the **purchases**, **purchase_prices**, **vendor_invoice**, and **sales** tables.
- Explored data for a sample vendor to understand relationships between purchase, sales, and invoice records.
- Created a preliminary `vendor_sales_summary` table with key metrics:
  - **Total Sales & Purchase Dollars**
  - **Gross Profit & Profit Margin**
  - **Stock Turnover**
  - **Sales-to-Purchase Ratio**
- Cleaned and standardized column formats.
- Stored aggregated results back into the database for later analysis.

---

### **2️⃣ Vendor Performance Analysis**
**Goal:** Derive actionable business insights from vendor-level and brand-level performance data.

**Key Analyses:**
- **Brand performance**:
  - Identified brands with low sales but high profit margins → potential pricing/promotion opportunities.
- **Top vendors**:
  - Ranked by contribution to sales and gross profit.
  - Calculated cumulative contribution % to identify dependency on key vendors.
- **Bulk purchasing analysis**:
  - Compared unit purchase prices across small, medium, and large order sizes.
- **Inventory turnover**:
  - Flagged vendors with slow-moving inventory (StockTurnover < 1).
- **Capital lock-in**:
  - Calculated value of unsold inventory per vendor.
- **Statistical tests**:
  - Computed 95% confidence intervals for profit margins of top vs. low-performing vendors.
  - Tested for significant differences between the two groups.

---

### **3️⃣ Data Pipeline Scripts**
- **`ingestion_db.py`** – Handles database connection and ingestion processes.
  - **Log Summary (`ingestion_db.log`)**: Records timestamps and confirms successful ingestion of data into the database.  
- **`get_vendor_summary.py`** – Queries and generates summarized vendor performance tables for analysis.
  - **Log Summary (`get_vendor_summary.log`)**: Creates a vendor summary table with key metrics, cleans and standardizes the data, then ingests it back into the database.  

---

## 🛠 Tools & Technologies
- **Python** (in Jupyter Notebook)
  - Libraries: pandas, seaborn
- **SQL** for querying and filtering datasets.
- **Power BI** for interactive dashboards and visualizations.

---

## 📂 Data Source
The dataset used in this project is too large to store directly on GitHub.  
You can download it here: **[Google Drive Link](https://drive.google.com/file/d/1Ym9G25c7AZBP7sVIWlbh1L0g5Y5sUCR9/view?usp=sharing)**
After downloading, unzip the file and place the contents in the `data` folder of the project.

### 📑 `vendor_sales_summary` Table

This aggregated table was created during the analysis by combining data from `purchases`, `purchase_prices`, `vendor_invoice`, and `sales`.

**Purpose:**  
To provide vendor-level and brand-level performance metrics for decision-making in the alcohol wholesale/retail industry.

**Key Columns:**
- `VendorNumber` – Unique identifier for each vendor
- `VendorName` – Name of the vendor
- `Brand` – Brand ID linked to the alcohol product
- `Description` – Product description
- `TotalPurchaseDollars` – Total spend on purchases from the vendor
- `TotalSalesDollars` – Total revenue from sales of the vendor’s products
- `GrossProfit` – Revenue minus costs, excluding overhead
- `ProfitMargin` – Gross profit as a percentage of sales
- `StockTurnover` – Inventory turnover ratio
- `SalesToPurchaseRatio` – Ratio of sales to purchases, indicating efficiency
- `UnsoldInventoryValue` – Dollar value of unsold stock

**Example Preview:**

| VendorNumber | VendorName               | Brand | Description              | TotalSalesDollars | GrossProfit | ProfitMargin | StockTurnover |
|--------------|--------------------------|-------|--------------------------|-------------------|-------------|--------------|---------------|
| 1128         | BROWN-FORMAN CORP         | 1233  | Jack Daniels No 7 Black  | 6,728,193.10       | 1,290,667.91| 25.30%       | 0.98          |
| 4425         | MARTIGNETTI COMPANIES     | 3405  | Tito's Handmade Vodka    | 5,615,123.70       | 1,015,032.27| 21.06%       | 0.97          |
| 17035        | PERNOD RICARD USA         | 8068  | Absolut 80 Proof         | 4,611,401.50       | 1,119,816.92| 24.68%       | 1.00          |


## 🎉 Project Status

This project is completed. All stages — data ingestion, exploratory analysis, vendor performance evaluation, and Power BI dashboard development — have been finalized. The repository includes code, logs, and visuals that showcase the full workflow from raw data to interactive insights.
