# E-commerce Funnel & Cohort Analysis

This project analyzes raw event logs from an e-commerce website to generate key business metrics. It includes a conversion funnel and a cohort-based retention analysis built entirely in Google Sheets using pivot tables and formulas.

## Overview

**Goal:** Turn raw user activity logs into actionable insights for business decision-making  
**Tools Used:** Google Sheets

---

## Contents

- **Conversion Funnel:** Analyze how many users moved from product views → cart opens → purchases.
- **Cohort Analysis:** Group users by first purchase month and track retention.
- **Retention Rates:** Calculate month-by-month retention for each cohort.

---

## 1. Conversion Funnel

- Tracked 3 user events: `product view`, `cart open`, and `purchase`
- Counted **unique users** at each stage
- Calculated:
  - **total_cr** = (stage users ÷ total views)
  - **next_step_cr** = (stage users ÷ previous stage users)

---

## 2. Purchase Data Preparation

- Filtered raw logs to isolate only `purchase` events
- Calculated each user's **first purchase date** using a pivot table
- Added helper columns:
  - `event_month` (formatted with `TEXT(date, "YYYY-MM")`)
  - `first_purchase_month`
  - `cohort_age` using `DATEDIF(first_purchase_date, event_date, "M")`

---

## 3. Cohort Analysis

- Grouped users by the month of their first purchase
- Counted unique users across 5 months of activity

---

### 4. Final Formatting & Summary
- Added an **Executive Summary** to explain insights and assumptions
- Organized sheets: Table of Contents
  - Executive Summary → Cohort Analysis → Retention Rates → First Purchase → Conversion Funnel → Raw User Activity → Purchase Activity
- Applied formatting for readability: headers, date formats, borders, frozen rows

---

## Key Takeaways

- Conversion from product view to cart: **29%**
- Conversion from cart to purchase: **36%**
- Retention drops steeply after the first month — common in e-commerce
- Only a small percentage of users continue purchasing beyond Month 2

---

## Guidance

1. Open the [Google Spreadsheet](https://docs.google.com/spreadsheets/d/1dzaM5xabaM0hrSSav6KB-hl04Wct0YbIPDj0bEcPSyM/edit?usp=sharing).
2. Follow the pivot table configurations and formulas outlined in each sheet.
3. Use the Table of Contents for easy navigation between sections.
