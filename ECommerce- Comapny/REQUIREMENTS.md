# E-commerce Funnel & Cohort Analysis

This project analyzes raw user activity logs from an e-commerce platform to generate key business metrics. It was completed using spreadsheet tools like pivot tables, VLOOKUP, TEXT, and DATEDIF functions.

## Project Objectives

### 1. Conversion Funnel Analysis
- Built a 3-stage funnel: product views → cart opens → purchases
- Counted unique users at each stage
- Calculated total conversion rates and step-by-step conversion rates

### 2. Cohort Analysis Preparation
- Filtered data to include only purchase events
- Calculated each user's first purchase date
- Created new columns for:
  - `event_month` – the month of the activity
  - `first_purchase_month` – the user's cohort
  - `cohort_age` – months since first purchase

### 3. Retention Rate Calculation
- Created a cohort-based pivot table showing user counts by month since acquisition
- Calculated retention rates (months 1 to 4) based on cohort size

### 4. Spreadsheet Organization
- Wrote a summary of results and methodology in an Executive Summary tab
- Ordered sheets as follows:
  - Table of Contents
  - Executive Summary
  - Results (conversion funnel, retention rates)
  - Calculations (pivot tables and formulas)
  - Raw data
- Applied formatting for readability (headers, number/date formats, borders, frozen rows)

