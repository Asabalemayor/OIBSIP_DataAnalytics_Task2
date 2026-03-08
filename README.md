# OIBSIP_DataAnalytics_Task2

# Data Cleaning Project

## Project Overview

Data cleaning is a crucial step in the data analysis process. Poor-quality data can lead to incorrect analysis and unreliable conclusions. The goal of this project is to clean and prepare an Airbnb dataset so it can be used for accurate analysis and decision-making.

In this project, an Airbnb dataset containing listings in New York City was cleaned by handling missing values, detecting inconsistencies, removing outliers, and creating additional useful features.

---

## Dataset

**Source:**  
https://www.kaggle.com/datasets/dgomonov/new-york-city-airbnb-open-data

**Original Dataset Shape:**  
48,895 rows × 16 columns

## Tools Used

| Tool | Purpose |
|-----|-----|
| Python | Data cleaning |
| Pandas | Data manipulation |
| Jupyter Notebook | Analysis environment |
| GitHub | Project documentation and submission |
| Matplotlib & Seaborn | for visualization |
| Numpy | Numerical calculations |
---

## Data Cleaning Steps

## 1. Handling Missing Values

The dataset contained missing values in the following columns:

| Column | Missing Values |
|------|------|
| name | 16 |
| host_name | 21 |
| last_review | 10052 |
| reviews_per_month | 10052 |

Cleaning actions taken:

- Missing `name` and `host_name` values were replaced with `"Unknown"`
- Missing `reviews_per_month` values were replaced with `0`
- `last_review` column was converted to datetime format, leaving missing values as `NaT`

---

## 2. Handle Outliers

- Removed listings with minimum_nights > 365 — unrealistic for most Airbnb stays.

- Checked for extreme price values (very high or zero) and removed if necessary.

## 3. Feature Engineering

Added is_duplicate_host → boolean flag to mark hosts with multiple listings.

Calculated the number of listings per host in calculated_host_listings_count.

## 4. Reset Index

After removing outliers, reset the row index for a clean, consecutive index from 0 to n-1.

# Data Quality Checks

- Checked for rows with 0 reviews but non-zero reviews_per_month, which could indicate inconsistent data.

- Identified hosts with multiple listings:

# Example of top hosts with multiple listings:

| host_id	| listing_count |
|------|------|
| 2787 |	6 |
| 2845 |	2 |
| 7351	| 3 |
| 7549 |	4 |

 These new features help understand multi-listing hosts and potential bias in the dataset.

 Cleaned Dataset

 Final shape: 48,867 rows × 17 columns

- Very few rows were removed (28 rows), mainly due to extreme outliers.

- New columns added: calculated_host_listings_count, is_duplicate_host

The dataset is now ready for exploratory data analysis, visualisation, or machine learning.

## Key Insights from Cleaning

- Airbnb listings can contain inconsistent or missing values — proper handling ensures reliable results.

- Outliers in minimum_nights and price could skew the analysis if not removed.

- Hosts with multiple listings could dominate review counts or pricing, so identifying them helps fairly analyse the data.

- Filling missing values thoughtfully (0 for numeric, "Unknown" for strings) makes the dataset consistent.

## Recommendation

- Please always look over and clean datasets before you begin your analysis.

- Create derived features (like is_duplicate_host) to capture hidden patterns.
.
