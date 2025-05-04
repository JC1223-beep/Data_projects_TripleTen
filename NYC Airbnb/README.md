# Airbnb Data Analysis Project

**Report Date:** January 31, 2025  
**Prepared By:** Cassey Cam

---

## Overview

This project focuses on analyzing Airbnb listing and calendar data to extract insights related to pricing, property size, revenue generation, and neighborhood popularity. The objective is to create meaningful data transformations and visual summaries that help identify trends and support data-driven decisions in short-term rental management.

---

## Table of Contents

- Change Log  
  A history log showing what was changed and updated in the spreadsheet, including new columns and calculated values.

- Data Dictionary  
  A description of the data sources (`listings` and `calendar` sheets), and what each one contains.

- Listings Overview  
  An explanation of the Airbnb listing data, including location, property type, bedroom information, and review scores.

- Calendar Overview  
  A breakdown of nightly pricing, minimum/maximum stay rules, and how revenue is calculated.

- Top 10 Neighborhoods  
  A summary of the top 10 neighborhoods to stay in, based on average review ratings from the listings spreadsheet.

- Neighborhoods by Bedroom Popularity  
  A pivot table analysis showing which bedroom size is most popular in each neighborhood.

- Popular Property Size  
  A general analysis (also using a pivot table) to identify the most common property size across all listings.

- Top Revenue Listing  
  An identification of the single Airbnb listing that earned the most revenue during the year, based on calendar data.

---

## Change Log

| Date       | Change Description                                                                 |
|------------|--------------------------------------------------------------------------------------|
| 1/31/2025  | Added column `bedroom_clean` in `listings` to fill blank values in column AK with 0 |
| 1/31/2025  | Added column `neighborhood_clean` in `listings` for a cleaned-up version of column AB |
| 1/31/2025  | Added column `top_listing` in `listings` to flag top-performing listings (1 = yes, 0 = no) |
| 1/31/2025  | Added column `revenue_earned` in `calendar`, calculated only when column C = "f"     |
| 1/31/2025  | Edited `adjusted_price` in column E (`calendar`) to reflect monthly total (×12)      |
| 1/31/2025  | Created this README with Table of Contents and structured documentation              |

---

## Data Dictionary

### listings  
Contains Airbnb property-level data including:
- Property details such as type, location, and bedroom count
- Review scores and total number of reviews
- Listing URLs and availability
- Cleaned fields: `bedroom_clean`, `neighborhood_clean`, and `top_listing`

### calendar  
Provides daily pricing and availability information:
- Minimum and maximum night stays
- Adjusted price per night
- Calculated field: `revenue_earned`, calculated only when availability column equals "f"
- Modified `adjusted_price` to reflect monthly totals (multiplied by 12)

---

## Listings Overview

This dataset holds the core information about each Airbnb listing, such as its location, the number of bedrooms, review score, and links to the listing itself. Columns were added and cleaned to allow for more accurate filtering and analysis:
- `bedroom_clean`: replaces blanks with 0 for analysis consistency
- `neighborhood_clean`: formatted for clarity
- `top_listing`: indicates listings with the highest revenue

---

## Calendar Overview

The calendar file offers insight into Airbnb availability and pricing strategies. It was enhanced to include:
- `revenue_earned`: only calculated when the listing is active (`C` = "f")
- Monthly pricing estimates using adjusted price multiplied by 12
This dataset helps visualize pricing models, booking availability, and estimated income.

---

## Top 10 Neighborhoods

**Summary:**  
The most popular neighborhood based on review ratings is the **Lower East Side**. This was determined by analyzing review scores in the `listings` dataset and ranking neighborhoods accordingly.

---

## Neighborhoods by Bedroom Popularity

**Summary:**  
This analysis shows that **1-bedroom** properties are the most common across most neighborhoods.  
Specifically, the **Lower East Side** has the highest concentration and popularity for 1-bedroom listings, based on review data.

---

## Popular Property Size

**Summary:**  
Across all listings, **Bedroom 1** is the most frequent property size.  
This was determined using a pivot table summarizing the number of reviews per bedroom count.

---

## Top Revenue Listing

**Summary:**  
Airbnb **Listing ID 3662827** generated the most revenue over the past year, according to the calendar dataset.  
This result was calculated using the `revenue_earned` field which multiplies adjusted price by availability for each date.

---

## Recommendations and Next Steps

- Analyze pricing strategies in top neighborhoods like Lower East Side
- Explore what makes Listing ID 3662827 successful (e.g., location, pricing, reviews)
- Study seasonal revenue patterns to optimize calendar-based pricing
- Expand the analysis to include other features like amenities, host type, and guest satisfaction
- Consider building dashboards or visualizations for real-time insight
