# 📊 Sales Operations Analytics - Data Assessment

![Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![Data Analysis](https://img.shields.io/badge/Data_Analysis-005571?style=for-the-badge)

## 📝 Project Overview
This project is an interview-grade data analytics assessment designed by **The Unlox Academy**. The scenario places the analyst in a fast-growing tech hardware distributor with the objective of analyzing 5 raw, messy datasets to answer critical business questions, diagnose data quality issues, and evaluate sales team performance. 

A strict requirement of this project was to **preserve the integrity of the raw data**—all data cleaning, lookups, and aggregations had to be performed dynamically via formulas and PivotTables without permanently altering the source files.

## 🗂️ Data Structure
The analysis spans 5 relational tables (approx. 2,000 orders):
* **Orders:** The central fact table containing order details, discounts, and final amounts.
* **Customers:** Demographics, city, and corporate/retail segment data.
* **Products:** Categories, unit costs, pricing, and active/discontinued status.
* **Sales_Reps:** Rep regions, hire dates, and team hierarchy.
* **Targets:** Monthly revenue targets for each sales representative.

## 🎯 Key Tasks & Methodologies

### 1. Advanced Lookups & Relational Mapping
* **Multi-hop Lookups:** Chained lookups across 3 different sheets to map Order IDs to Product Categories.
* **Self-Joins:** Mapped sales representatives to their respective Team Leads using nested lookups.
* **Approximate Matches:** Categorized orders into dynamic discount slabs using lower-bound range lookups.
* **Functions Used:** `INDEX`, `MATCH`, `VLOOKUP`, `XLOOKUP`.

### 2. Data Cleaning & Quality Diagnostics
* Diagnosed the database for **broken foreign keys** (orders referencing missing customers).
* Identified anomalous string formatting (leading/trailing whitespaces, inconsistent casing) and calculated true distinct counts.
* Flagged suspicious patterns, such as cancelled orders retaining high promotional discounts.
* **Functions Used:** `LEN`, `TRIM`, `UPPER`, `ISNA`, Array-based `SUMPRODUCT`.

### 3. Complex Conditional Aggregations
* Calculated multi-condition metrics (e.g., Average revenue for *Electronics* in the *Corporate* segment) dynamically **without the use of helper columns** by utilizing array logic in memory.
* Compared dynamic date ranges (e.g., Q3 vs. specific months) against varying regional targets.
* **Functions Used:** `SUMIFS`, `COUNTIFS`, `AVERAGEIFS`, `LARGE`, `SUMPRODUCT`.

### 4. Pivot Table Analysis
* Built 2D cross-tabulations analyzing product performance by geographic region.
* Grouped time-series data by Quarters and Months.
* Created **Calculated Fields** directly within the PivotTable data model to accurately compute true Profit Margins (`(price - cost) / price`).

### 5. Advanced Ranking & Array Logic
* Generated dynamic top-N lists (e.g., concatenating the names of the top 5 sales reps).
* Calculated cumulative revenue trajectories over dynamic time periods.
* Extracted specific records using multi-conditional `MAX(IF())` arrays.
* **Functions Used:** `RANK.EQ`, `TEXTJOIN`, `MAXIFS`, `Ctrl+Shift+Enter` (CSE) Arrays.

## 🚀 How to View the Project
1. Download the `13548653-Excel_Minor_Project.xlsx` file from this repository.
2. Open the file in Microsoft Excel (Excel 2019 or Microsoft 365 recommended).
3. Navigate through the yellow-highlighted question tabs (`Q1_Lookups`, `Q2_Cleaning`, etc.) to view the formulas and logic used for the analysis.
4. Check the `Pivot Workspace` sheet to interact with the PivotTables and Calculated Fields.

---
*This project was completed as part of the DA/DS Track at The Unlox Academy.*
