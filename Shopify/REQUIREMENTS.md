# ⚙️ Requirements to Reproduce the Shopify App Marketplace Analysis

This document outlines everything needed to replicate or extend the dashboard used in the final sprint project.

---

## Software

- **Microsoft Power BI Desktop**
  - Recommended Version: October 2023 or later
  - Download: https://powerbi.microsoft.com/desktop/

---

## Dataset

- `shopify.xlsx` (from publicly scraped Shopify App Store data)

**Contains:**
- `apps`: App metadata
- `apps_categories`: App to category link
- `categories`: App categories
- `reviews`: Ratings, comments, developer replies

---

## Data Preparation

### Relationships Created:

- `Reviews[app_id]` ➝ `Apps[id]`  
  (Many-to-One relationship)

### DAX Columns:

1. **Helpful Reviews**
   ```DAX
   helpful_reviews = rating * (1 + helpful_count)
