# Shopify App Store Data Analysis using Power BI

This project analyzes data scraped from the public Shopify App Store using Power BI. The goal is to understand the key factors that influence the success of Shopify apps based on app attributes, reviews, and developer responses.

## Dataset Overview

The data used is from `shopify.xlsx`, which contains the following tables:

- `apps`: Details of the apps listed on the Shopify app store.
- `apps_categories`: Join table that connects apps with categories.
- `categories`: Categories assigned to apps (many-to-many relationship).
- `reviews`: Each review's rating, helpfulness, and developer reply info.

## Power BI Report Structure

The report is structured into three main sections, each built as a separate sheet in Power BI:

---

### 🔹 Part 1: App Landscape

Focuses on app distribution and engagement:
- **KPI Card**: Count of unique apps.
- **Line Chart**: Sum of reviews over time (by `lastmod` date).
- **Scatterplot**: Relationship between `reviews_count` and `average_rating`.

---

### 🔹 Part 2: Reviews

Focuses on review quality and developer engagement:
- Created a calculated column:  
  `helpful_reviews = rating * (1 + helpful_count)`
- **Card**: Displays the average value of `helpful_reviews`.
- **Developer Answered** column:
  `developer_answered = IF(ISBLANK(developer_reply), 0, 1)`
- **Scatterplot**: Average rating vs whether the developer responded.

---

### 🔹 Part 3: App Reviews

Analyzes developer performance:
- Joined `Reviews` and `Apps` on `app_id` and `id`.
- **Bar Chart**: Developer vs sum of ratings.
- **Bar Chart**: Developer vs average helpful review score.
- **Bar Chart**: Most responsive developers (with `reviews_count > 500`).

---

## 📌 Key Insights

- Developers that respond to reviews generally have higher average ratings.
- Some apps have high review volume but low average ratings.
- Helpful reviews (based on user votes) reveal deeper customer satisfaction.

---

## 📁 File List

| File Name     | Description                                 |
| ------------- | ------------------------------------------- |
| `README.md`   | This project overview and structure.         |
| `REQUIREMENTS.md` | Software and dependencies needed.         |
| `Power BI Dashboard.pdf`    | Dashboard and screenshot of each years      |

---
