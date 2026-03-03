# ETL Lesson 3, Practice 3: Summary Report

## Task 1: Generation of Synthetic Data with Errors

- **Total records generated:** 500 original + 20 duplicates = 520 rows.
- **Attributes Setup:** Included ProductID, ProductName, ProductCategory, ProductPrice, CustomerEmail, AmountSpent, LoyaltyScore, PurchaseDate, PaymentMethod, and ShippingCountry.
- **Errors Introduced:**
  - `NA` strings generated manually inside the `ProductPrice` column.
  - `invalid-email` tags simulated inside `CustomerEmail`.
  - Specific Missing Values mapped randomly inside `PurchaseDate`, `AmountSpent`, `LoyaltyScore`, and `ShippingCountry`.
  - Synthetically introduced bounding box outliers into numeric limits.

## Task 2: Data Profiling Before Cleaning

- Summarized constraints mapping total descriptive limits (`df.describe()`, `df.info()`).
- Measured heatmaps exposing visible null gaps and count metrics tracking missing value gaps globally.
- Isolated standard deviation scales searching for Z-score metric breaches (>3).
- Detected all exact duplication row counts directly.

## Task 3: Data Cleaning and Transformation

- **Duplicate Control:** Trimmed identified exact duplicates explicitly.
- **Imputation Strategy:**
  - `AmountSpent`: Replaced nulls matching mean value averages.
  - `LoyaltyScore`: Replaced nulls using the numeric column median metrics.
  - `PurchaseDate`: Populated missing data values manually binding defaults matching `2025-01-01`.
  - `ShippingCountry`: Masked unknowns mapped matching the explicit `Unknown` strings.
  - `ProductPrice`: Sanitized text string errors parsing to core numeric values substituting default mean thresholds.
- **Outlier Elimination:** Handled removal tracking the measured Z>3 bounds isolating variables in bounds.
- **Dataset Standardization:** Adjusted `ProductCategory` and `PaymentMethod` strings handling casing normalization, adjusting dates mapped via consistent format mappings.

## Task 4: Profiling Post-Cleaning

- Ran secondary verification checks returning 0 empty parameters and strictly validated type casts fully configured globally across the clean tables.

## Task 5: Final Visualizations

- Produced comparative charts contrasting "Before vs After" metric mapping. Included structured visualizations scaling Histograms matching target metrics bounding tight ranges, isolating exact standard Z-score limits correctly mapped out below thresholds reliably in dual scatterplots and boxplots.

## Deliverables Generated

- `Practice3.ipynb`: Fully parameterized interactive notebook executing synthetic errors, profiling pipelines, transformation logic algorithms effectively.
- Dynamically rendered raw `practice3_raw_data.csv` and cleansed `practice3_clean_data.csv` available directly after running the target execution scripts logic.
