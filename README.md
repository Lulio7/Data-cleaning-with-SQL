# World Layoffs Data Cleaning - SQL Project

## 🧾 Project Overview

This project focuses on the **cleaning and preprocessing of layoff data** collected from companies worldwide. Layoff data often comes in inconsistent, duplicate, or incomplete formats, making it crucial to prepare the dataset before performing any meaningful analysis. 

Using **SQL**, we developed a systematic approach to clean, standardize, and optimize the data for further analytical use cases such as:
- Identifying trends in workforce reduction by industry and country
- Analyzing economic impact on specific sectors
- Building visual dashboards for decision-makers
- Feeding reliable inputs to predictive models

## 🛠️ Tools Used

- SQL (MySQL syntax)
- Relational Database Management System
- Dataset: Layoffs from companies worldwide (`world_layoff.layoffs`)

---

## 🔍 SQL Workflow Summary

### 1. Create a Working Copy
- A backup table `layoffs2` is created from the original dataset `layoffs`.
- This allows us to keep the original data intact while working on cleaning.

### 2. Remove Duplicates
- A `row_num` column is created using `ROW_NUMBER()` window function to identify duplicates.
- Duplicated entries (same company, industry, total layoffs, etc.) are filtered and removed.

### 3. Standardize the Data
- **Company names** are trimmed to remove extra spaces.
- **Industries** are standardized (e.g., "Crypto Currency", "CryptoCurrency" → "Crypto").
- **Countries** are corrected (e.g., "United States." → "United States").
- **Date format** is converted using `STR_TO_DATE()` and altered to use the DATE data type.

### 4. Handle Null or Blank Values
- Null and blank values in `industry`, `total_laid_off`, and `percentage_laid_off` are addressed.
- Industries are inferred and updated by joining the dataset with itself based on company name.
- Remaining rows with irrecoverable nulls are deleted.

### 5. Remove Unnecessary Columns
- The temporary `row_num` column used for identifying duplicates is dropped after cleaning.

---

## 💼 Commercial Applications

By cleaning and preparing this dataset, it becomes valuable for several real-world applications:

- **Market Trend Analysis**: Determine which industries or countries are experiencing the most layoffs.
- **Investment Insight**: Investors can assess sectors with increased layoffs, indicating financial stress or downturn.
- **Policy-Making**: Governments or NGOs can use this data to develop targeted relief or retraining programs.
- **Internal HR Strategy**: Companies can benchmark their layoff patterns against competitors or industry norms.

---

## ✅ Final Output

The final cleaned dataset `layoffs_staging2` is ready for analytical queries, dashboard development in tools like Power BI or Tableau, or integration into machine learning pipelines.

---

## 👋 Acknowledgment

Thanks for following along this data cleaning journey!
