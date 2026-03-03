# ETL Lesson 3, Practice 1: Summary Report

## Task 1: Data Profiling

- **Total records / Features:** 1050 rows and 7 columns.
- **Duplicates Found:** 50 duplicate transactions.
- **Missing Values:** `TransactionAmount` (58 missing), `LoyaltyScore` (53 missing).
- **Transaction Amount Distribution:** The mean amount was heavily skewed by outliers, with an average of ~$419.51. Extremely low (negative) and extremely high values (>$47k) were detected.

## Task 2: Data Cleaning

- **Duplicates Removed:** Identified and removed 50 exact duplicated transaction rows.
- **Missing Value Strategy:**
  - `TransactionAmount`: Missing values were replaced by the calculated mean of the respective column.
  - `LoyaltyScore`: Missing values were filled with a default score of 50.
- **Formatting Fixes:** Discovered 26 negative transaction amounts (fixed using absolute values) and 4 extreme outliers (capped at a maximum value of $1000). The dataset's completeness was fully restored, bringing the row count to a verified 1000 unique, clean records.

## Task 3: Data Standardization

- **Date Standardization:** Inconsistent formats like `%d-%b-%y` were unified into standard `YYYY-MM-DD` formats properly.
- **Country Names:** Multiple representations (e.g., "usa", "us") were normalized and title-cased into standardized structures under 'United States', 'UK', etc.
- **Product Categories:** Text cases were unified into title case (e.g. "Electronics").
- **Customer IDs:** Lower-case variants handled correctly to an upper-case formatting.

## Task 4: Business Metrics & Analysis

### Q1. Which country generates the most revenue?

Based on the cleaned data, **Canada** generates the most revenue ($54,081.07), edging out the United States.

### Q2. Who are the top 5 highest-spending customers?

1. CUST0141 ($3,724.76)
2. CUST0024 ($3,700.86)
3. CUST0167 ($3,290.36)
4. CUST0148 ($3,065.09)
5. CUST0068 ($3,033.74)

### Q3. Which product category has the highest average transaction amount?

On average, the **Books** category returned the highest average transaction amount of $284.69. The highest total grossing category overall was Electronics ($57,010.53).

## Deliverables Generated

- `Practice1.ipynb`: An interactive Jupyter notebook containing the pipeline's execution logic and dashboard reporting.
- `transactions_raw.csv`: Generated synthetic dataset showing targeted errors mapping to the objectives.
- `transactions_clean.csv`: Output cleaned CSV file ready for Looker Studio, Power BI, or relevant ingestion dashboards.
