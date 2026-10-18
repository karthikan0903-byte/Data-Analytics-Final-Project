# Superstore Sales Data Analysis & Performance Report (2015-2018) Using Python

A comprehensive, data-driven Exploratory Data Analysis (EDA) of retail superstore performance using Python. This project evaluates revenue trends, profitability dynamics, product category efficiency, regional market strength, and the financial impact of promotional discounting from 2015 to 2018.

---

## Project Overview

This project analyzes nationwide retail superstore transactional data using Python to extract strategic commercial intelligence and optimize retail business operations.

The analysis focuses on:
- **Product Category & Sub-Category Performance:** Identifying revenue drivers and diagnosing loss-making lines.
- **Profitability Dynamics:** Uncovering margin dilution caused by aggressive discounting strategies.
- **Geographic Distribution:** Evaluating sales density and profit conversion across macro-regions (West, East, Central, South).
- **Temporal Trends:** Tracking year-over-year revenue expansion and seasonality patterns from 2015 through 2018.
- **Statistical Distributions:** Examining central tendencies, variability, skewness, and kurtosis across core financial metrics.

The project combines Data Cleaning, Feature Engineering, Statistical Analysis, Exploratory Data Analysis (EDA), and Data Visualization to transform raw transactional logs into actionable executive insights.

---

## Objectives

The main objective of this project is to analyze the Superstore sales dataset using Python and deliver data-backed recommendations to maximize net operating margins.

### Key Objectives
1. Identify high-performing product categories and sub-categories driving top-line revenue.
2. Diagnose loss-making sub-categories and determine root causes of profit erosion.
3. Quantify the statistical relationship between promotional discounts and net profit margins.
4. Measure yearly revenue trajectories (2015–2018) and identify peak seasonal demand cycles.
5. Evaluate regional sales and profitability to optimize geographic resource allocation.
6. Provide executive-level business recommendations based on analytical findings.

---

## Problem Statement

Raw transactional datasets do not directly reveal why certain high-volume categories yield low profits, how discount thresholds impact line-item margins, or which geographic territories underperform relative to sales volume.

Therefore, this project applies Python-based analytical workflows to uncover:
- Underlying profitability drivers across product categories.
- Optimal discount boundaries to prevent margin destruction.
- Geographic inefficiencies and regional profit conversion gaps.
- Growth trajectories across temporal dimensions.

---

## Business Understanding

This analysis is designed to answer fundamental commercial questions:

### Revenue & Profitability
- Which product category yields the highest revenue and net profit?
- Why does the Furniture category exhibit severe profit lag despite high sales volume?
- Which specific sub-categories operate at cumulative financial losses?

### Discounting & Pricing Strategy
- What is the precise correlation between discount percentage and net profit margin?
- At what discount threshold do transactions become net-unprofitable?

### Regional Dynamics
- Which geographic region dominates in revenue and profit generation?
- Why does the Central region exhibit significantly lower profit conversion compared to the West?

---

## Dataset Information

| Attribute | Details |
| :--- | :--- |
| **Data Source** | Superstore Retail Public Transactional Dataset |
| **Location** | United States |
| **Domain** | Retail & E-Commerce |
| **Period** | 2015 – 2018 |
| **Records** | 9,994 |
| **Base Attributes** | 18 |
| **Engineered Features** | 3 (`order_year`, `shipping_days`, `profit_margin`) |
| **Total Attributes** | 21 |
| **File Format** | CSV |
| **Environment** | Google Colab |

### Attribute / Data Dictionary

| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| `Order ID` | Object | Unique identifier for each transaction order |
| `Order Date` | Datetime | Timestamp when the order was placed |
| `Ship Date` | Datetime | Timestamp when the product was dispatched |
| `Ship Mode` | Object | Shipping method (*Standard Class*, *Second Class*, *First Class*, *Same Day*) |
| `Customer ID` | Object | Unique identifier for each customer |
| `Segment` | Object | Market segment (*Consumer*, *Corporate*, *Home Office*) |
| `Country` | Object | Country location (*United States*) |
| `City` | Object | Destination city |
| `State` | Object | Destination state |
| `Postal Code` | Numeric | Destination postal code |
| `Region` | Object | Macro-geographic zone (*West*, *East*, *Central*, *South*) |
| `Product ID` | Object | Unique stock-keeping unit (SKU) identifier |
| `Category` | Object | High-level category (*Technology*, *Furniture*, *Office Supplies*) |
| `Sub-Category` | Object | Granular product sub-grouping (e.g., *Phones*, *Chairs*, *Tables*) |
| `Product Name` | Object | Name of the individual product |
| `Sales` | Float | Gross dollar sales value per transaction |
| `Quantity` | Integer | Total units sold per line item |
| `Discount` | Float | Promotional discount rate applied (0.00 to 0.80) |
| `Profit` | Float | Net dollar profit or loss per line item |
| `order_year` | Integer | Engineered Feature: Calendar year extracted from `Order Date` |
| `shipping_days` | Integer | Engineered Feature: Turnaround days computed as (`Ship Date` - `Order Date`) |
| `profit_margin` | Float | Engineered Feature: Line-item margin ratio computed as (`Profit` / `Sales`) |

---

## Tools & Technologies

- **Programming Language:** Python 3.10+
- **Data Manipulation:** Pandas, NumPy
- **Data Visualization:** Matplotlib, Seaborn
- **Environment:** Google Colab / Jupyter Notebook

---

## Project Workflow
Data Ingestion & Inspection
↓
Data Cleaning & Formatting
↓
Feature Engineering
↓
Statistical Analysis (Central Tendency, Skewness, Kurtosis)
↓
Univariate Analysis
↓
Bivariate Analysis
↓
Multivariate Analysis
↓
Business Insights & Strategic Action Plan

---

## Statistical Analysis Summary

Descriptive statistical measures were calculated across numerical metrics to evaluate central tendencies, dispersion, and distribution shapes:

| Variable | Mean | Median | Std Dev | Variance | Skewness | Kurtosis |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| `Sales` | $229.86 | $54.49 | $623.25 | 388,434.45 | 12.97 | 305.31 |
| `Profit` | $28.66 | $8.67 | $234.26 | 54,876.48 | 7.51 | 397.18 |
| `Quantity` | 3.79 | 3.00 | 2.23 | 4.97 | 1.23 | 1.99 |
| `Discount` | 0.156 | 0.200 | 0.206 | 0.042 | 1.68 | 2.45 |
| `profit_margin` | 0.120 | 0.270 | 0.467 | 0.218 | -2.16 | 10.52 |

### Statistical Interpretations
- **Right-Skewed Sales Distribution:** The mean sales value ($229.86) substantially exceeds the median ($54.49), driven by large enterprise technology purchases.
- **Extreme Profit Volatility:** Profit exhibits high variance ($54,876.48) and extreme kurtosis (397.18), indicating heavy tails with significant positive and negative outliers.
- **Negative Margin Skewness:** `profit_margin` shows strong negative skewness (-2.16), reflecting aggressive promotional discounting that causes deep line-item losses.

---

## Key Exploratory Data Analysis & Visualizations

1. **Correlation Matrix (Heatmap):** 
   - Reveals an inverse correlation ($r = -0.864$) between `Discount` and `profit_margin`. Higher discounts directly erode profit margins.
2. **Category Sales Performance:** 
   - **Technology** leads gross revenue at **$836,154**, followed by **Furniture** (**$741,999**) and **Office Supplies** (**$719,047**).
3. **Category Profitability Discrepancy:**
   - **Technology** generates **$145,455** in profit (17.39% margin) and **Office Supplies** yields **$122,491** (17.04% margin).
   - **Furniture** generates only **$18,451** in net profit (<2.5% margin) despite generating over $741K in sales.
4. **Sub-Category Loss Leaders:**
   - *Phones* ($330K) and *Chairs* ($328K) dominate gross revenue.
   - *Tables* (-$17,725) and *Bookcases* (-$3,473) operate at cumulative net financial losses due to excessive discounting.
5. **Yearly Sales Expansion (2015–2018):**
   - Revenue grew from **$484,247** (2015) to **$733,215** (2018), with peak order volume occurring consistently during Q4 holiday surges.
6. **Regional Performance:**
   - **West** region leads both sales (**$725,458**) and profit (**$108,418**) with a 14.94% operating margin.
   - **Central** region lags in profit conversion (7.92% margin) due to heavy commercial discounting.

---

## Key Findings & Business Insights

- **Technology Anchors Growth:** Technology products generate peak sales and profit, driven by high-margin items like Copiers and Accessories.
- **Furniture Margin Dilution:** Deep promotional discounting and heavy freight overhead severely degrade net margins in Furniture lines.
- **Discount Destruction Threshold:** Discounts exceeding **20%** consistently yield negative net margins, averaging **-24.2%** on items discounted by 30% or more.
- **Regional Execution Gap:** Central region produces 21.8% of gross sales but only 13.9% of net profits, pointing to unmonitored contract discounting.

---

## Strategic Recommendations

1. **Implement Discount Governance:** Automated system caps should prevent discounts over **20%** without executive authorization.
2. **Restructure Loss-Making Sub-Categories:** Adjust pricing, renegotiate freight terms, or transition *Tables* and *Bookcases* to direct-ship bundling models.
3. **Focus on High-Margin Technology:** Increase inventory and marketing allocation toward high-margin items like *Copiers*, *Accessories*, and *Phones*.
4. **Central Region Pricing Audit:** Standardize commercial contract terms in the Central Region and tie sales commissions to **net profit** rather than gross sales volume.

---

## How to Run the Project

Follow these step-by-step instructions and code snippets to run the complete analysis notebook in Google Colab or Jupyter Notebook:

### 1. Clone the Repository
```bash
git clone [https://github.com/your-username/Superstore-Sales-Data-Analysis.git](https://github.com/your-username/Superstore-Sales-Data-Analysis.git)
cd Superstore-Sales-Data-Analysis

### 2. Install Required Libraries
pip install pandas numpy matplotlib seaborn

### 3. Complete Python Analysis Script
Run the following code block in your environment to execute the complete pipeline:

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Set visualization style
sns.set_theme(style="whitegrid")
plt.rcParams['figure.figsize'] = (10, 6)

# ---------------------------------------------------------
# Step 1: Data Collection & Pre-processing
# ---------------------------------------------------------
# Load raw dataset from raw GitHub repository link
url = '[https://raw.githubusercontent.com/datasets/superstore/main/superstore.csv](https://raw.githubusercontent.com/datasets/superstore/main/superstore.csv)'
df = pd.read_csv(url, encoding='latin1')

# Data cleaning & type conversion
df['Order Date'] = pd.to_datetime(df['Order Date'])
df['Ship Date'] = pd.to_datetime(df['Ship Date'])

# Handle missing postal codes if any
df['Postal Code'] = df['Postal Code'].fillna(0).astype(int)

# ---------------------------------------------------------
# Step 2: Feature Engineering
# ---------------------------------------------------------
df['order_year'] = df['Order Date'].dt.year
df['shipping_days'] = (df['Ship Date'] - df['Order Date']).dt.days
df['profit_margin'] = df['Profit'] / df['Sales']

# Export cleaned dataset
df.to_csv('cleaned_superstore.csv', index=False)
print("Cleaned dataset saved as 'cleaned_superstore.csv'")

# ---------------------------------------------------------
# Step 3: Statistical Moments Calculation
# ---------------------------------------------------------
num_cols = ['Sales', 'Profit', 'Quantity', 'Discount', 'profit_margin']
stats_df = pd.DataFrame({
    'Mean': df[num_cols].mean(),
    'Median': df[num_cols].median(),
    'Std Dev': df[num_cols].std(),
    'Variance': df[num_cols].var(),
    'Skewness': df[num_cols].skew(),
    'Kurtosis': df[num_cols].kurt()
})
print("\n--- STATISTICAL ANALYSIS SUMMARY ---")
print(stats_df)

# ---------------------------------------------------------
# Step 4: Exploratory Data Analysis & Visualizations
# ---------------------------------------------------------

# 1. Correlation Matrix Heatmap
plt.figure(figsize=(8, 6))
sns.heatmap(df[['Sales', 'Quantity', 'Discount', 'Profit', 'profit_margin']].corr(), 
            annot=True, cmap='coolwarm', fmt='.3f', linewidths=0.5)
plt.title('Correlation Matrix of Superstore Numerical Features', fontsize=14, fontweight='bold')
plt.tight_layout()
plt.savefig('visualizations/correlation_heatmap.png')
plt.show()

# 2. Total Sales by Product Category
category_sales = df.groupby('Category')['Sales'].sum().reset_index().sort_values(by='Sales', ascending=False)
plt.figure(figsize=(8, 5))
sns.barplot(data=category_sales, x='Category', y='Sales', palette='viridis')
plt.title('Total Sales by Product Category', fontsize=14, fontweight='bold')
plt.ylabel('Total Sales ($)')
plt.tight_layout()
plt.savefig('visualizations/category_sales.png')
plt.show()

# 3. Yearly Sales Trend (2015-2018)
yearly_sales = df.groupby('order_year')['Sales'].sum().reset_index()
plt.figure(figsize=(8, 5))
sns.lineplot(data=yearly_sales, x='order_year', y='Sales', marker='o', linewidth=2.5, color='b')
plt.title('Yearly Sales Trend (2015–2018)', fontsize=14, fontweight='bold')
plt.xlabel('Order Year')
plt.ylabel('Total Sales ($)')
plt.xticks([2015, 2016, 2017, 2018])
plt.tight_layout()
plt.savefig('visualizations/yearly_sales_trend.png')
plt.show()

# 4. Top 10 Sub-Categories by Total Sales
top10_subcat = df.groupby('Sub-Category')['Sales'].sum().reset_index().sort_values(by='Sales', ascending=False).head(10)
plt.figure(figsize=(10, 6))
sns.barplot(data=top10_subcat, y='Sub-Category', x='Sales', palette='magma')
plt.title('Top 10 Sub-Categories by Total Sales', fontsize=14, fontweight='bold')
plt.xlabel('Total Sales ($)')
plt.tight_layout()
plt.savefig('visualizations/top10_subcategories.png')
plt.show()

# 5. Total Profit by Product Category
category_profit = df.groupby('Category')['Profit'].sum().reset_index().sort_values(by='Profit', ascending=False)
plt.figure(figsize=(8, 5))
sns.barplot(data=category_profit, x='Category', y='Profit', palette='crest')
plt.title('Total Profit by Product Category', fontsize=14, fontweight='bold')
plt.ylabel('Total Profit ($)')
plt.tight_layout()
plt.savefig('visualizations/category_profit.png')
plt.show()

# 6. Total Sales by Region
region_sales = df.groupby('Region')['Sales'].sum().reset_index().sort_values(by='Sales', ascending=False)
plt.figure(figsize=(8, 5))
sns.barplot(data=region_sales, x='Region', y='Sales', palette='Blues_r')
plt.title('Total Sales by Region', fontsize=14, fontweight='bold')
plt.ylabel('Total Sales ($)')
plt.tight_layout()
plt.savefig('visualizations/region_sales.png')
plt.show()

# 7. Total Profit by Region
region_profit = df.groupby('Region')['Profit'].sum().reset_index().sort_values(by='Profit', ascending=False)
plt.figure(figsize=(8, 5))
sns.barplot(data=region_profit, x='Region', y='Profit', palette='Greens_r')
plt.title('Total Profit by Region', fontsize=14, fontweight='bold')
plt.ylabel('Total Profit ($)')
plt.tight_layout()
plt.savefig('visualizations/region_profit.png')
plt.show()

Conclusion
This project demonstrates how Python can be utilized to transform raw retail transactional data into meaningful business intelligence. By integrating statistical techniques, exploratory visualizations, and category-level diagnostics, the analysis highlights critical levers for improving retail profitability—specifically controlling promotional discount boundaries, restructuring loss-making furniture categories, and leveraging high-margin technology products.
