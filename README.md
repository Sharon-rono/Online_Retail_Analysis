# Online Retail Data Analysis

This project analyzes retail transaction data to extract actionable business insights. The goal is to clean and transform raw retail data, compute key performance metrics, and identify high-performing products, customers, and markets.

## Key objectives include:

-Data cleaning and validation for quantity, unit price, and missing values

-Computing revenue, quantity sold, and monthly performance trends

-Ranking customers and countries based on revenue and demand

-Identifying high-opportunity markets for strategic growth

## Dataset
**Source:** `online_retail_data.xlsx`


## Project Structure

### 1. Data Cleaning Process

**Steps Performed:**
- Converted `InvoiceDate` to datetime format (normalized to date only)
- Removed transactions with `Quantity < 1` (returns/cancellations)
- Removed transactions with `UnitPrice < 0` (invalid prices)
- Dropped rows with missing `CustomerID` values
- Removed duplicate records
- Changed `CustomerID` data type to object

**Data Quality:**
- Initial records: 541,909
- Final cleaned records: 392,731
- Records removed: 149,178 (27.5%)

### 2. Feature Engineering
Created additional columns:
- `Revenue`: Calculated as `Quantity × UnitPrice`
- `Year`: Extracted from `InvoiceDate`
- `Month`: Extracted from `InvoiceDate`
- `Day`: Extracted from `InvoiceDate`

## Analysis Performed

### 1. Time Series Analysis (2011 Revenue Trends)
**Objective:** Track monthly revenue patterns throughout 2011

**Key Findings:**
- Filtered data for Year 2011 (367,058 transactions)
- Computed monthly revenue totals
- Calculated month-over-month percentage changes
- Identified seasonal patterns and growth trends

### 2. Country Performance Analysis (Excluding UK)
**Objective:** Identify top international markets by revenue and quantity

**Top 5 Countries by Revenue:**
1. Netherlands: £285,446.34
2. EIRE (Ireland): £265,262.46
3. Germany: £228,678.40
4. France: £208,934.31
5. Australia: £138,453.81

**Analysis Includes:**
- Total revenue per country
- Total quantity sold per country
- Ranked list of all 36 international markets

### 3. Top Customer Analysis
**Objective:** Identify highest-value customers

**Methodology:**
- Grouped transactions by `CustomerID`
- Calculated total revenue per customer
- Ranked all 4,339 customers by spending
- Identified top 10 highest-spending customers

**Top Customer:** CustomerID 12346 with £77,183.60 in total revenue

### 4. Global Product Demand
**Objective:** Rank countries by product demand (quantity purchased)

**Top 5 Markets by Quantity:**
1. Netherlands: 200,937 units
2. EIRE: 140,383 units
3. Germany: 119,156 units
4. France: 111,429 units
5. Australia: 84,199 units


## Key Insights

1. **Seasonal Trends:** Revenue patterns show significant month-to-month variation in 2011, useful for inventory planning

2. **International Opportunities:** Netherlands, EIRE, and Germany represent the strongest non-UK markets both by revenue and volume

3. **Customer Concentration:** Top customers drive significant revenue, suggesting opportunity for targeted retention strategies

4. **Market Penetration:** 36 international markets served, with clear concentration in European countries


