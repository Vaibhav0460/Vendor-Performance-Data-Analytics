# Vendor Performance Data Analytics

<div align="center">
  
![Vendor Performance Dashboard](image.jpg)

**A complete end-to-end data analytics solution for vendor performance analysis and optimization**

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/)
[![SQL](https://img.shields.io/badge/SQL-SQLite3-green)](https://www.sqlite.org/)
[![PowerBI](https://img.shields.io/badge/PowerBI-Dashboard-yellow)](https://powerbi.microsoft.com/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-red)](https://pandas.pydata.org/)

</div>

---

## 📋 Table of Contents

- [Overview](#overview)
- [Business Problem](#business-problem)
- [Project Objectives](#project-objectives)
- [Tech Stack](#tech-stack)
- [Project Architecture](#project-architecture)
- [Key Features](#key-features)
- [Installation & Setup](#installation--setup)
- [Project Structure](#project-structure)
- [Data Pipeline](#data-pipeline)
- [Analysis & Insights](#analysis--insights)
- [Dashboard Overview](#dashboard-overview)
- [Key Findings](#key-findings)
- [Future Enhancements](#future-enhancements)
- [Contributing](#contributing)
- [Contact](#contact)
- [License](#license)

---

## 🎯 Overview

This is a **company-standard, real-world data analytics project** that demonstrates a complete end-to-end workflow for vendor performance analysis in the retail and wholesale industry. Unlike typical beginner projects, this solution integrates multiple tools (SQL, Python, Power BI) to solve actual business problems, making it ideal for aspiring data analysts building a professional portfolio.

The project analyzes over **12 million+ sales records** and **2 million+ purchase transactions** across 126 vendors to identify:
- Top-performing vendors and brands
- Underperforming products requiring promotional adjustments
- Inventory turnover inefficiencies
- Pricing optimization opportunities
- Profitability variance analysis

---

## 💼 Business Problem

Effective inventory and sales management are critical for optimizing profitability in the retail and wholesale industry. Companies need to ensure they are not incurring losses due to:

1. **Inefficient Pricing** - Products selling at suboptimal price points
2. **Poor Inventory Turnover** - Stock remaining unsold, increasing holding costs
3. **Vendor Dependency** - Overreliance on specific vendors without performance evaluation

This project provides actionable insights to address these challenges through data-driven decision-making.

---

## 🎯 Project Objectives

### Primary Goals:
1. **Identify underperforming brands** that require promotional and pricing adjustments
2. **Determine top vendors** contributing to sales and gross profit
3. **Analyze the impact of bulk purchasing** on unit cost
4. **Assess inventory turnover** to reduce holding costs and improve efficiency
5. **Investigate profitability variance** between high-performing and low-performing vendors

### Deliverables:
- Automated ETL pipeline for data ingestion
- Cleaned and aggregated vendor summary dataset
- Comprehensive exploratory data analysis (EDA)
- Interactive Power BI dashboard
- Executive summary report with actionable recommendations

---

## 🛠️ Tech Stack

| Category | Technologies |
|----------|-------------|
| **Database** | SQLite3, SQL Alchemy |
| **Data Processing** | Python 3.8+, Pandas, NumPy |
| **Data Analysis** | Scipy, Statistics |
| **Visualization** | Matplotlib, Seaborn, Power BI |
| **ETL/Automation** | Python Scripts, Logging |
| **Version Control** | Git, GitHub |

---

## 🏗️ Project Architecture

```
┌─────────────────┐
│   Raw CSV Data  │
│  (2GB+ files)   │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  ETL Pipeline   │
│  (ingestion_db) │
│  - Validation   │
│  - Loading      │
│  - Logging      │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ SQLite Database │
│  (inventory.db) │
│  - 6 tables     │
│  - 2GB storage  │
└────────┬────────┘
         │
         ▼
┌──────────────────┐
│  SQL Transforms  │
│  (get_vendor_    │
│   summary.py)    │
│  - Joins         │
│  - Aggregations  │
│  - Feature Eng   │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│ Vendor Summary   │
│ Table (10K rows) │
└────────┬─────────┘
         │
         ├─────────────────────┐
         │                     │
         ▼                     ▼
┌─────────────────┐   ┌──────────────┐
│  Python EDA     │   │   Power BI   │
│  - Analysis     │   │  Dashboard   │
│  - Insights     │   │  - KPIs      │
│  - Stats Tests  │   │  - Charts    │
└─────────────────┘   └──────────────┘
```

---

## ✨ Key Features

### 1. **Production-Ready ETL Pipeline**
- Automated data ingestion from CSV to SQLite database
- Comprehensive logging system for monitoring and debugging
- Error handling and data validation
- Optimized query performance for large datasets (2GB+)

### 2. **Advanced Data Transformation**
- Complex SQL joins across 6+ tables
- CTEs (Common Table Expressions) for readable query structure
- Feature engineering (Gross Profit, Profit Margin, Stock Turnover, Sales-to-Purchase Ratio)
- Data cleaning and quality checks

### 3. **In-Depth Exploratory Data Analysis**
- Distribution analysis of 18+ numerical variables
- Correlation heatmaps to identify relationships
- Outlier detection and treatment
- Statistical hypothesis testing

### 4. **Interactive Power BI Dashboard**
- Real-time KPI tracking (Total Sales: $441M, Gross Profit: $134M, Profit Margin: 38.7%)
- Vendor and brand performance comparison
- Purchase contribution breakdown
- Low-performing vendor/brand identification
- Drill-down capabilities for detailed analysis

### 5. **Business Insights & Recommendations**
- Data-driven vendor selection criteria
- Pricing strategy optimization
- Inventory management improvements
- Profitability enhancement opportunities

---

## 🚀 Installation & Setup

### Prerequisites
- Python 3.8 or higher
- Power BI Desktop (for dashboard)
- Git

### Step 1: Clone the Repository
```bash
git clone https://github.com/Vaibhav0460/Vendor-Performance-Data-Analytics.git
cd Vendor-Performance-Data-Analytics
```

### Step 2: Create Virtual Environment (Recommended)
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### Step 3: Install Dependencies
```bash
pip install pandas numpy matplotlib seaborn scipy sqlalchemy sqlite3
```

### Step 4: Prepare Data
- Place your CSV files in the `data/` folder
- Update the file path in `ingestion_db.py` if needed

### Step 5: Run ETL Pipeline
```bash
python ingestion_db.py
```

### Step 6: Create Vendor Summary Table
```bash
python get_vendor_summary.py
```

### Step 7: Exploratory Analysis
Open and run the Jupyter notebooks:
- `Exploratory Data Analysis.ipynb` - Initial data exploration
- `Vendor Performance Analysis.ipynb` - Detailed vendor analysis

### Step 8: View Dashboard
- Open the Power BI file (`.pbix`) in Power BI Desktop
- Refresh data connections to load latest data

---

## 📁 Project Structure

```
Vendor-Performance-Data-Analytics/
│
├── data/                          # Raw CSV files (gitignored)
│   ├── begin_inventory.csv
│   ├── end_inventory.csv
│   ├── purchases.csv
│   ├── purchase_prices.csv
│   ├── sales.csv
│   └── vendor_invoice.csv
│
├── logs/                          # Execution logs
│   ├── ingestions_db.log
│   └── get_vendor_summary.log
│
├── .ipynb_checkpoints/            # Jupyter checkpoint files
│
├── __pycache__/                   # Python cache files
│
├── ingestion_db.py               # ETL script for raw data ingestion
├── get_vendor_summary.py         # Script to create aggregated summary table
│
├── Exploratory Data Analysis.ipynb     # Initial EDA notebook
├── Vendor Performance Analysis.ipynb   # Detailed analysis notebook
│
├── inventory.db                  # SQLite database (gitignored)
│
├── .gitignore                    # Git ignore file
├── README.md                     # Project documentation
│
└── image.jpg                     # Dashboard screenshot
```

---

## 🔄 Data Pipeline

### Phase 1: Data Ingestion (ingestion_db.py)

**Purpose**: Load raw CSV files into SQLite database

**Process**:
1. Scans `data/` folder for CSV files
2. Reads each CSV using Pandas
3. Creates SQLite tables with automatic schema detection
4. Implements logging for monitoring
5. Handles large files (2GB+) efficiently

**Tables Created**:
- `begin_inventory` (206K+ records)
- `end_inventory` (224K+ records)
- `purchases` (2.3M+ records)
- `purchase_prices` (12K+ records)
- `sales` (12.8M+ records)
- `vendor_invoice` (5.5K+ records)

### Phase 2: Data Transformation (get_vendor_summary.py)

**Purpose**: Create aggregated vendor summary table

**Process**:
1. **Freight Summary CTE**: Aggregates freight costs by vendor
2. **Purchase Summary CTE**: Joins purchases with purchase prices
3. **Sales Summary CTE**: Aggregates sales data by vendor and brand
4. **Final Join**: Combines all CTEs into master summary
5. **Feature Engineering**: Calculates derived metrics
6. **Data Cleaning**: Handles missing values, strips whitespace, converts data types

**Output**: `vendor_sales_summary` table (10,692 records)

### Phase 3: Analysis & Visualization

**Python Analysis**:
- Distribution plots for numerical variables
- Boxplots for outlier detection
- Correlation heatmaps
- Statistical hypothesis testing
- Count plots for categorical variables

**Power BI Dashboard**:
- KPI cards (Sales, Purchases, Profit, Margin, Unsold Capital)
- Donut chart (Purchase Contribution %)
- Horizontal bar charts (Top Vendors & Brands by Sales)
- Bar charts (Low Performing Vendors)
- Scatter plot (Low Performing Brands)

---

## 📊 Analysis & Insights

### Data Quality Findings

**Negative & Zero Values**:
- **Gross Profit**: Minimum value of -$52,002.78 indicates some products are sold at a loss
- **Profit Margin**: Contains -inf values where revenue is zero or negative
- **Total Sales Quantity**: 178 products purchased but never sold (dead stock)

**Outliers**:
- **Purchase Prices**: Range from $0.36 to $5,681.81 (premium products)
- **Freight Costs**: Huge variation ($0.09 to $257,032) suggests logistics inefficiencies
- **Stock Turnover**: Ranges from 0 to 274.5, indicating extreme variation in product velocity

### Correlation Insights

- **Purchase Price** has weak correlation with Total Sales (-0.012) and Gross Profit (-0.016)
- **Strong correlation** (0.999) between purchase quantity and sales quantity confirms efficient turnover
- **Negative correlation** (-0.179) between profit margin and sales price suggests competitive pricing pressure
- **Stock Turnover** weakly correlated with profitability (-0.038), indicating fast turnover ≠ high profit

### Vendor Performance

**Top 5 Vendors by Sales**:
1. **DIAGEO NORTH AMERICA INC** - $68M
2. **MARTIGNETTI COMPANIES** - $39M
3. **PERNOD RICARD USA** - $32M
4. **JIM BEAM BRANDS COMPANY** - $31M
5. **BACARDI USA INC** - $25M

**Top 5 Brands by Sales**:
1. **Jack Daniels No 7 Black** - $8.0M
2. **Tito's Handmade Vodka** - $7.2M
3. **Grey Goose Vodka** - $7.2M
4. **Capt Morgan Spiced Rum** - $6.4M
5. **Absolut 80 Proof** - $6.2M

**Low Performing Vendors** (by Stock Turnover):
1. Dunn Wine Brokers - 0.766
2. Circa Wines - 0.756
3. PARK STREET IMPORTS LLC - 0.751
4. HIGHLAND WINE MERCHANTS LLC - 0.708
5. ALISA CARR BEVERAGES - 0.615

---

## 📈 Dashboard Overview

### KPIs at a Glance
- **Total Sales**: $441.41M
- **Total Purchases**: $307.34M
- **Gross Profit**: $134.07M
- **Profit Margin**: 38.7%
- **Unsold Capital**: $2.71M

### Purchase Contribution Analysis
- Top 10 vendors contribute **65.7%** of total purchases
- **DIAGEO NORTH AMERICA INC** leads with 16.3% contribution
- Diversified vendor base reduces dependency risk

### Brand Performance
- Scatter plot identifies 100+ low-performing brands requiring intervention
- Clear separation between profitable (blue) and unprofitable (red) brands
- Average profit margin threshold at ~50% helps categorize performance

---

## 🔍 Key Findings

1. **Inventory Optimization Opportunity**: $2.71M tied up in unsold inventory
2. **Vendor Concentration Risk**: Top 10 vendors account for 65.7% of purchases
3. **Pricing Strategy**: 178 products with zero sales despite purchases need repricing
4. **Profit Margin Leaders**: Products with 38.7% average margin, but high variance
5. **Stock Turnover**: Near-perfect correlation (0.999) between purchase and sales quantity
6. **Freight Inefficiency**: Extreme variance in freight costs suggests optimization potential
7. **Loss-Making Products**: Some items sold at loss (negative gross profit)

---

## 🚀 Future Enhancements

### Short-term
- [ ] Implement real-time data refresh using APIs
- [ ] Add time-series forecasting for sales prediction
- [ ] Create automated email reports for stakeholders
- [ ] Develop vendor scorecard system

### Medium-term
- [ ] Build recommendation engine for vendor selection
- [ ] Integrate machine learning for demand forecasting
- [ ] Add geographical analysis using store location data
- [ ] Create mobile-friendly dashboard version

### Long-term
- [ ] Migrate to cloud infrastructure (AWS/Azure)
- [ ] Implement data warehouse (Snowflake/BigQuery)
- [ ] Build real-time streaming analytics
- [ ] Develop prescriptive analytics for automated decision-making

---

## 🤝 Contributing

Contributions are welcome! If you'd like to improve this project:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📧 Contact

**Vaibhav Mishra**

- Email: [vaibhav0460@gmail.com](mailto:vaibhav0460@gmail.com)
- LinkedIn: [Connect with me](https://www.linkedin.com/in/vaibhav-mishra)
- GitHub: [@Vaibhav0460](https://github.com/Vaibhav0460)

---

## 🙏 Acknowledgments

- **Dataset**: Mock data generated for educational purposes
- **Inspiration**: Real-world vendor management challenges in retail industry
- **Tools**: Thanks to the open-source community for Python, Pandas, and visualization libraries

---

<div align="center">

**⭐ If you find this project helpful, please consider giving it a star! ⭐**

Made with ❤️ by Vaibhav Mishra

</div>
