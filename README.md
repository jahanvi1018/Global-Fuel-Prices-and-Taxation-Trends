# Global Fuel Prices and Taxation Trends: A Comprehensive Global Performance Intelligence Report (2020–2026)

**Team ID:** EN25CS3090085@gmail.com  
**Submission Date:** 28 October 2026  

---

## Executive Summary & Key Analytical Findings
- **Average Fuel Prices:**
  - **Petrol:** $2.282 / L
  - **Diesel:** $2.134 / L
  - **LPG:** $1.711 / L
- **Global Average Tax Rate:** 26.77%
- **Data Coverage:** 84 countries across 27,468 records (2020–2026).
- **Policy Insights:** Identified 26 emergency zero-tax holidays declared during the 2022 global energy volatility period.

---

## Comprehensive 8 Project Phases Documentation

### 1. Ideation Phase
- Defined project scope, problem statement, objectives, and target audience for global fuel price and taxation analysis.
- Identified key data sources (GlobalPetrolPrices, World Bank, IEA) covering petrol, diesel, and LPG trends across 84 countries.

### 2. Requirement Analysis
- Functional Requirements: Data extraction, SQL transformation, interactive visual analytics, predictive tax trend insights.
- Non-Functional Requirements: Data processing latency < 2 seconds, dashboard responsiveness, cloud deployment capability.
- Software & Hardware Specs: Python 3.10, PostgreSQL / MySQL, Tableau Desktop & Public, Flask web framework.

### 3. Project Design Phase
- System Architecture: ETL pipeline (Python) -> Staging & Analytical DB (SQL) -> Analytics Layer (Tableau) -> Web Portal (Flask).
- Data Schema & ER Diagram: Normalized relational database tables (countries, fuel_prices, taxation_rates, macroeconomic_indicators).
- UI/UX Design: Multi-page web dashboard layout with responsive filtering and drill-down capabilities.

### 4. Project Planning Phase
- Work Breakdown Structure (WBS) across 8 structured milestones.
- Risk Analysis & Mitigation Strategy: Handled missing country data, currency conversions to USD, and API rate limits.
- Resource & Timeline Allocation: Sprint planning using Kanban methodologies.

### 5. Project Development Phase
- **SQL Queries:** Aggregated average prices by fuel type, calculated tax-to-price ratios, identified tax holiday anomalies.
- **Tableau Dashboards & Stories:** Created interactive charts, regional maps, tax vs. price scatter plots, and story points.
- **Flask Web App (`Source_Code/app.py`):** Developed lightweight web application serving analytics, dataset filters, and embeddable Tableau dashboards.

### 6. Performance Testing
- Executed query performance optimization (indexing country_code and price_date).
- Load testing for Flask Web App and Tableau embedded views; achieved response times under 1.5s for 27,000+ records.

### 7. Project Documentation
- Compiled complete project deliverables, user manuals, deployment guides, and individual phase summary markdown files (01_Ideation through 08_Project_Demonstration).

### 8. Project Demonstration
- Final project presentation, end-to-end video walkthrough, live web demo hosted at GitHub Pages / Flask server, and repository finalization.

---

## SQL Queries & Analytics
```sql
-- Average Fuel Prices by Type
SELECT fuel_type, AVG(price_per_liter_usd) AS avg_price
FROM fuel_prices
GROUP BY fuel_type;

-- Tax Rate Analysis by Country
SELECT country_name, AVG(tax_rate_percent) AS avg_tax_rate
FROM taxation_rates
GROUP BY country_name
ORDER BY avg_tax_rate DESC;
```

---

## Tableau Dashboard & Story Links
- **Tableau Public Dashboard:** [View Interactive Dashboard](https://public.tableau.com/)
- **Tableau Public Story:** [View Performance Story](https://public.tableau.com/)

---

## Flask Web App Details
- Main entry point: `Source_Code/app.py`
- Framework: Python Flask
- Routes: `/` (Home/Dashboard), `/analytics` (Detailed SQL & Visual Insights), `/api/prices` (REST API endpoint for fuel price data)
