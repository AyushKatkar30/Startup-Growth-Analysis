# Startup Funding Analysis – Power BI & Python Project

**Author:** Ayush Katkar  
**Email:** ayushkatkar3002@gmail.com  
**Tools Used:** Power BI, Python (Pandas, Matplotlib), Jupyter Notebook  
**Operating System:** Windows  

---

## 1. Project Overview

This project analyzes Indian startup funding data to uncover patterns in investment distribution across cities, sectors, and investors. The dataset contains real startup funding records with details such as amount raised, investor information, sector type, and date of funding.  

The objective is to clean and transform the raw dataset using Python, and then build interactive dashboards using Power BI to extract meaningful insights that explain growth trends in the Indian startup ecosystem.

---

## 2. Project Objectives

1. Clean and standardize real-world startup funding data.
2. Identify the top startup hubs in India based on funding received.
3. Analyze funding distribution across industries and investment types.
4. Track funding growth over time using time-series analysis.
5. Build interactive dashboards for strategic understanding.
6. Present key insights that support business and investor decisions.

---

## 3. Dataset Details

- Dataset: Indian Startup Funding
- Total Features Used:
  - Startup Name
  - Investors Name
  - Industry Vertical
  - Sub-Vertical
  - City / Location
  - Investment Type
  - Funding Amount
  - Date of Funding

The data was sourced from publicly available startup funding records.

---

## 4. Data Cleaning Using Python

### Key Data Processing Steps
- Removal of missing and irrelevant values.
- Standardization of city and industry names.
- Conversion of Amount column into numeric data.
- Currency transformation into millions for clarity.
- Date formatting into Year and Month for trend analysis.

### Python Code Used

```python
import pandas as pd
import matplotlib.pyplot as plt

# Load dataset
df = pd.read_csv("startup_funding.csv")

# Remove missing values in key fields
df.dropna(subset=["Amount", "City", "Industry Vertical"], inplace=True)

# Convert funding amount into numeric
df["Amount"] = df["Amount"].replace({',': ''}, regex=True).astype(float)

# Convert to millions for better readability
df["Funding_Million"] = df["Amount"] / 1000000

# Handle date format conversion
df["Date"] = pd.to_datetime(df["Date"], errors="coerce")
df["Year"] = df["Date"].dt.year
df["Month"] = df["Date"].dt.month

print(df.head())
```
## 5. Power BI Dashboard Development

### Dashboard Pages Created

---

### Page 1: Executive Overview

- Total Funding (KPI)
- Number of Unique Startups (KPI)
- Number of Funding Deals (KPI)
- Industry-wise funding distribution (Bar Chart)
- City-wise funding chart
- Monthly funding trend line
- Filters for industry, city, and year

---

### Page 2: Funding Insights

- Highest Funded Sectors in India
- Investment Type vs Funding Amount
- Top 5 Most Funded Startups
- Table view of all startup funding details

---

### Page 3: Startup Market Analysis

- Funding based on sub-verticals (Treemap)
- Investor participation patterns
- Insight summary text box

---

## 6. Key Insights Discovered

1. Bengaluru is the top city for startup funding in India.
2. FinTech, E-Commerce, and Technology sectors dominate total investment share.
3. Most funding rounds are concentrated in a few major metros.
4. Funding growth increased significantly in later years of the dataset.
5. Investors focus heavily on scalable and tech-driven businesses.

---

## 7. Project Summary

This project demonstrates how business intelligence and programming techniques transform raw financial data into actionable insights. Using Python, the dataset went through detailed cleaning and preprocessing. Power BI visualization enabled deeper exploration of funding patterns to reveal leading locations, industries, and investor behavior in India’s startup landscape.

The final output provides a data-backed understanding of where startup investments are concentrated and what factors contribute to fast-growing startup ecosystems.

---

## 8. Conclusion

- India’s startup ecosystem is expanding rapidly with technology-driven industries leading the market.
- Funding remains highly centralized in major cities such as Bengaluru and Mumbai.
- Data analytics enables better investment strategy and opportunity identification.
- Interactive dashboards provide clear decision-making support for stakeholders.



