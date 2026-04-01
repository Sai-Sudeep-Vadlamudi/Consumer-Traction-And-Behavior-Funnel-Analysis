# Consumer-Traction-And-Behavior-Funnel-Analysis
# Consumer Traction & Behavior Funnel Analysis

## Executive Summary

This project is an end-to-end **customer analytics and business intelligence solution** designed to transform raw consumer transaction data into **decision-ready insights** for commercial, product, and operations stakeholders. It combines **Python-based ETL**, **SQL-driven analytical querying**, and **Power BI dashboarding** to surface patterns in purchasing behavior, customer segmentation, monetization, discount usage, shipping preferences, subscription behavior, and product-level performance.

Positioned as a practical analytics portfolio project, the repository demonstrates the ability to build a lightweight but complete **data-to-dashboard pipeline**: ingesting raw data, standardizing and enriching fields, loading curated data into a relational database, writing business-facing SQL, and enabling downstream executive reporting through BI.

---

## Business Problem

This consumer-facing businesses need more than static sales totals. They need to understand:

- **Who their targetted consumer demographics are**
- **How different segments behave**
- **Which products and categories drive traction**
- **How does discounts influence spend**
- **How shipping choices correlate with purchasing behavior**
- **Which customers show stronger retention and subscription signals**

**Basically they want to figure out how can the company leverage consumer shopping data to identify trends, improve customer engagement, and optimize marketing and product strategies?**

This project addresses that need by creating a structured analytical workflow for exploring **consumer traction, behavioral patterns, and revenue dynamics** using a curated retail-style customer dataset.

---
<img width="620" height="449" alt="{72288F44-C01C-4BF0-BCA6-7110133E5E5A}" src="https://github.com/user-attachments/assets/4fe33237-963d-40c7-b6b6-ce59a03b4b8d" />

---
## Solution Overview

The repository implements a compact analytics stack with three tightly connected layers:

### 1. Data Engineering / ETL Layer
A Jupyter Notebook performs data ingestion, profiling, data quality checks, missing-value treatment, schema standardization, and feature engineering.

### 2. Analytics / SQL Layer
A dedicated SQL script answers business-relevant questions focused on revenue, ratings, shipping, discount adoption, customer segmentation, repeat purchase behavior, and demographic contribution.

### 3. Reporting / BI Layer
A Power BI dashboard file is included to support visual storytelling, KPI tracking, and stakeholder-facing reporting.

Together, these layers simulate a real-world **analytics workflow used by data analysts, BI analysts, product analysts, and commercial strategy teams**.


<img width="632" height="354" alt="{70355E8C-3EBC-4817-9F67-BDB2C667365D}" src="https://github.com/user-attachments/assets/1fc743da-6deb-4cf3-a53e-ca455cba31b1" />

---

## Key Capabilities Demonstrated

- **End-to-end analytics workflow** from raw CSV to BI-ready dataset
- **Exploratory data analysis (EDA)** and schema profiling
- **Data quality remediation** through targeted null handling
- **Feature engineering** for segmentation and behavioral analysis
- **Relational data loading** from Python into MySQL using SQLAlchemy
- **Business-oriented SQL analysis** for executive and operational questions
- **Power BI enablement** for dashboard-driven insight delivery
- **Consumer behavior segmentation** using purchase history and demographic bins
- **Monetization analysis** across gender, subscription, age group, and product category
- **Retention proxy analysis** using previous purchases and subscription behavior

---

## Dataset Scope

The analytical dataset contains customer-level retail shopping behavior fields such as:

- Customer demographics
- Product and category attributes
- Purchase amount
- Location
- Seasonality indicators
- Review ratings
- Subscription status
- Shipping type
- Discount usage
- Previous purchase counts
- Payment method
- Purchase frequency

This structure makes the project suitable for demonstrating **customer intelligence**, **behavioral segmentation**, **commercial analytics**, and **retail performance analysis**.

---

## Data Preparation & Feature Engineering

The ETL workflow includes the following transformations:

### Data Profiling
- Loads the raw dataset into pandas
- Inspects schema, data types, non-null counts, and descriptive statistics
- Reviews missing values across all columns

### Data Quality Handling
- Fills missing `Review Rating` values using the **median rating within each product category**
- Standardizes column names into analytics-friendly snake_case
- Renames `purchase_amount_(usd)` to `purchase_amount` for cleaner downstream querying

### Feature Engineering
- Creates `age_group` using quartile-based bucketing with labels:
  - Young Adult
  - Adult
  - Middle-aged
  - Senior
- Maps `frequency_of_purchases` into a numeric behavioral feature: `purchase_frequency_days`
- Validates that `discount_applied` and `promo_code_used` are equivalent in the source data
- Drops the redundant `promo_code_used` field after validation

### Data Loading
- Connects Python to **MySQL** via `SQLAlchemy` and `PyMySQL`
- Writes the curated dataset into the `customer_behavior` database
- Persists the final table as `customer`

This is a solid example of **analytical data preparation for downstream BI and SQL consumption**.

---

## Business Questions Answered in SQL

The SQL layer is built around practical stakeholder questions, including:

1. Revenue generated by **male vs. female customers**
2. Customers who used a **discount** but still spent above the **average purchase amount**
3. Top 5 products with the **highest average review rating**
4. Comparison of average purchase amount between **Standard** and **Express** shipping
5. Whether **subscribed customers** spend more, including average spend and total revenue
6. Products with the **highest discount adoption rate**
7. Customer segmentation into **New, Returning, and Loyal** cohorts
8. Top purchased products within each category using **window functions**
9. Whether **repeat buyers** are also more likely to subscribe
10. Revenue contribution by **age group**

These queries align well with common analytics use cases in **customer lifecycle analysis, promotion effectiveness, retention, merchandising, and revenue optimization**.

---

## Power BI Layer

The repository also includes a Power BI dashboard artifact, enabling the project to extend beyond notebook analysis into a more stakeholder-friendly BI experience.

This supports a portfolio narrative around:

- **Dashboard development**
- **KPI monitoring**
- **Executive reporting**
- **Interactive business storytelling**
- **Self-service analytics enablement**






---

## Tech Stack

- **Python**
- **Pandas**
- **Jupyter Notebook**
- **MySQL**
- **SQLAlchemy**
- **PyMySQL**
- **SQL**
- **Power BI**

---

## Repository Structure

```text
Consumer-Traction-And-Behavior-Funnel-Analysis/
├── Consumer Traction & Behaviour Analysis Dashbord.pbix   # Power BI dashboard artifact
├── ETL.ipynb                                              # Data cleaning, profiling, feature engineering, DB load
├── SQL Queries.sql                                        # Business-facing analytical SQL queries
├── customer_behavior.csv                                  # Raw source dataset
├── README.md                                              # Project documentation
└── LICENSE                                                # MIT license
