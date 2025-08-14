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
- **`get_vendor_summary.py`** – Queries and generates summarized vendor performance tables for analysis.

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

## 🚧 Current Stage  
This project is currently in the **Power BI development phase**, where interactive dashboards and visualizations are being built to present the analysis findings more effectively.

## 📈 Next Steps
- Finalize Power BI dashboards.
- Publish summary metrics and key charts in the repository’s `/visuals` folder.
- Add documentation for running the scripts and reproducing results.
