# Requirements

This project uses Power BI and requires the following setup:

---

## 🛠 Software

- **Power BI Desktop**
  - Version: October 2023 or later recommended
  - Download: https://powerbi.microsoft.com/desktop/

---

## Data File

- `shopify.xlsx`
  - Includes: apps, apps_categories, categories, reviews

---

## 📊 Power BI Configuration

### 1. Data Modeling
- Create relationship: `Reviews[app_id]` → `Apps[id]` (Many-to-One)

### 2. DAX Columns
- `helpful_reviews = rating * (1 + helpful_count)`
- `developer_answered = IF(ISBLANK(developer_reply), 0, 1)`

---

## Visuals Used

| Visual Type   | Description                                  |
|---------------|----------------------------------------------|
| KPI Card      | Unique apps, average helpful rating          |
| Line Chart    | Total reviews over time                      |
| Scatterplot   | Rating vs helpfulness, rating vs dev reply   |
| Bar Chart     | Developer performance and responsiveness     |

---

## ✅ Notes

- This analysis is based on public data only.
- All visuals are created in Power BI and exported manually as screenshots.

---


