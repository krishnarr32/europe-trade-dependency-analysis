# Europe Trade Dependency Analysis (2020)

> **Python-based data analysis project** integrating GDP and international trade datasets to identify Europe's most trade-dependent countries and analyse their import/export structures across product categories.

---

## Business Problem

International trade is central to Europe's economic performance. This project answers four key questions for European trade policymakers:

- **Q1:** Which region is most trade-dependent? Which European countries are most trade-dependent?
- **Q2:** What is the import/export structure of the top 3 trade-dependent European countries?
- **Q3:** How does trade dependency relate to GDP per capita?
- **Q4:** How has COVID-19 impacted trading activity among top trade-dependent countries?

---

## Datasets

| Dataset | Source | Description |
|---|---|---|
| GDP Among Countries | Kaggle | 184 countries, GDP and GDP per capita (2020) |
| International Trade | World Bank (WITS) | Merchandise imports & exports by country (2020) |
| Product Category Trade | WITS — manual extraction | Import/export by Raw Materials, Intermediate, Consumer, Capital Goods for top 3 countries |
| Time-Series GDP (Web Scraped) | World Bank API | GDP 2005–2023 for Slovenia, Slovakia, Hungary |

**Final merged dataset:** GDP + trade data for European countries, 2020

---

## Key Findings

### Q1 — Most Trade-Dependent Region & Countries
- **Europe** is the most trade-dependent region globally by Trade-to-GDP ratio
- **Top 3 most trade-dependent European countries:**
  1. 🥇 **Slovenia**
  2. 🥈 **Slovakia**
  3. 🥉 **Hungary**

### Q2 — Import/Export Structure
- All three countries are heavily reliant on **Intermediate Goods** for both imports and exports — reflecting their role in European manufacturing supply chains
- **Capital Goods** form a significant export share for Slovenia and Slovakia

### Q3 — Trade Dependency vs GDP Per Capita
- Higher trade dependency does not consistently correlate with higher GDP per capita — institutional and structural factors play a larger role

### Q4 — COVID-19 Impact
- 2020 data alone is insufficient to assess COVID-19 impact — a time-series approach using World Bank API was proposed and implemented for Slovenia, Slovakia, and Hungary (2005–2023)

---

## Methodology

### Data Wrangling
- Removed irrelevant columns; standardised GDP units to USD millions
- Converted wide-format income data to long format
- Created ISO3A country code mapping for merging datasets
- Derived `Trade_to_GDP` ratio: `(Imports + Exports) / GDP`

### Analysis
- Grouped by region → ranked by average Trade-to-GDP ratio
- Filtered European countries → identified top 3
- Merged product-category trade data for deep-dive analysis
- Web scraped World Bank API for time-series GDP data

### Visualisations
- Bar charts: Trade-to-GDP ratio by region and country
- Pie charts: Import/export structure by product category per country
- Line charts: GDP time-series (2005–2023) via World Bank API

---

## Tools & Libraries

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557c?style=flat)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white)

- **Language:** Python
- **Libraries:** `pandas`, `numpy`, `matplotlib`, `requests`, `json`
- **Data Access:** World Bank API (`NY.GDP.MKTP.CD`)
- **Environment:** Jupyter Notebook

---

## Repository Structure

```
.
├── GROUP_3_PROJECT_FINAL.ipynb    # Full Python analysis notebook
├── Group_3_Presentation.pptx     # Project presentation slides
└── README.md
```

---

## How To Run

1. Open `GROUP_3_PROJECT_FINAL.ipynb` in **Jupyter Notebook** or **VS Code**
2. Place `GDP.csv` and trade CSV files in the same directory
3. Run all cells in order
4. The World Bank API section runs automatically — no API key required

---

## Academic Context

- **Course:** BUSINFO 701 — Data Wrangling and Analysis, University of Auckland
- **Role:** Data wrangling, EDA, trade dependency analysis, visualisation, and web scraping implementation

---

*Project by Sai Krishna Sudarsan | Master of Business Analytics, University of Auckland*
