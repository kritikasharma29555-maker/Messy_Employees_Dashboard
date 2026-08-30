# Messy Employee Data Cleaning & Analytics Dashboard

## Executive Summary
This project presents an end-to-end data analytics solution developed using **Excel**, **Python (Pandas & SQLAlchemy)**, **MySQL Workbench**, and **Power BI**. The workflow transforms raw, messy employee data into clean, structured database records and interactive visualizations for data-driven workforce decision-making.

---

## Tech Stack & Project Architecture
* **Excel:** Initial raw data collection (`Messy_Employee_dataset.xlsx`)[cite: 1, 2].
* **Python (Pandas, SQLAlchemy):** Automated data cleaning, median imputation for missing values, string parsing, and database streaming (`Messy Employee Dataset.ipynb`)[cite: 2].
* **MySQL Workbench:** Relational schema creation (`employee_db`), table loading (`clean_employees`), and analytical querying (`Messy_employees.sql`)[cite: 2].
* **Power BI:** Interactive dashboarding (`Messy_Employeess.pbix`) tracking key metrics, hiring velocity, department compensation, and workforce distribution.

---

## Power BI Dashboard Overview

### Key Metrics (KPIs)
* **Total Employees:** 1,020 Total Staff Records[cite: 2]
* **Average Salary:** $85.16K USD[cite: 2]
* **Average Age:** 32 Years[cite: 2]
* **Remote Work Ratio:** 50% Remote Workforce[cite: 2]

---

## Key Dashboard Insights & Visualizations

1. **Hiring Trends Over Time (Line Chart):**
   * Detailed tracking of employee onboarding counts from **2020 to 2024**:
     * **2020:** 203 hires
     * **2021:** 189 hires
     * **2022:** 183 hires
     * **2023:** Peak hiring year with 228 hires
     * **2024:** 217 hires

2. **Workforce Status Overview (Donut Chart):**
   * **Pending:** 35%[cite: 2]
   * **Active:** 35%[cite: 2]
   * **Inactive:** 31%[cite: 2]

3. **Compensation & Department Analytics (Treemap & Scatter Plot):**
   * **Treemap:** Evaluates headcount distribution across core departments (Sales, DevOps, HR, Admin, Finance, Cloud Tech)[cite: 2].
   * **Performance vs. Salary Correlation Scatter Plot:** Analyzes compensation trends against employee performance evaluations (`Poor`, `Average`, `Good`, `Excellent`) spanning $80K to $90K salary bands across departments[cite: 2].

4. **Interactive Filters & Slicers:**
   * Filterable by **Region**, **Department**, and **Join Date Range** (01-01-2020 to 29-12-2024)[cite: 2].

---

## Data Cleaning & Transformation Pipeline

### 1. Data Cleaning & Feature Engineering (Python)
* **Date Standardizing:** Converted raw text date strings in `Join_Date` into proper `datetime64[ns]` objects[cite: 2].
* **Feature Splitting:** Extracted combined values from `Department_Region` into distinct `Department` and `Region` attributes[cite: 2].
* **Missing Value Imputation:** Imputed missing values in `Age` (211 records) and `Salary` (24 records) using median imputation[cite: 2].
* **Data Cleansing:** Converted negative phone values into clean positive string representations[cite: 2].
* **Name Concatenation:** Created a `Full_Name` column by merging `First_Name` and `Last_Name`[cite: 2].

### 2. Relational Database Integration (MySQL)
* Uploaded 1,020 cleaned records into the `clean_employees` table inside `employee_db`[cite: 2].

```sql
-- Database Verification Query
CREATE DATABASE IF NOT EXISTS employee_db;
USE employee_db;
SELECT * FROM clean_employees LIMIT 10;
