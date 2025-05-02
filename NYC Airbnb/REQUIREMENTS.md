#  Manhattan Airbnb Market Analysis

You've been hired to help a client analyze the Manhattan vacation rental market. The goal is to provide guidance on **which property types and neighborhoods to invest in** using Airbnb data.

Your task involves answering the following two key questions:

---

##  1. Which Neighborhoods and Property Sizes Are Most Attractive for Vacation Rentals?

We’ll use the `number_of_reviews_ltm` column as a proxy for how attractive or frequently rented a property is (since reviews only appear after a stay). Follow these steps:

###  Data Cleaning
- **Neighborhoods**: 
  - Clean the `neighborhood` column by removing inconsistent capitalization and trailing spaces.
  - Store cleaned values in a new column called `neighborhood_clean`.

- **Bedrooms**: 
  - Treat empty cells in the `bedrooms` column as 0 (studio apartments).
  - Create a cleaned version of this column called `bedrooms_clean` using an `IF` function.

### Analysis

- **Top 10 Neighborhoods**:
  - Create a pivot table using `neighborhood_clean` and `number_of_reviews_ltm`.
  - Identify the **10 neighborhoods** with the highest total number of reviews.
  - Add a **bar chart** showing review totals for these neighborhoods.

- **Most Popular Property Sizes**:
  - Build a pivot table to determine which `bedrooms_clean` values are most common.
  - Check if different neighborhoods have preferences for different bedroom counts.

---

## 2. How Much Money Did the Most Attractive Listings Generate?

We’ve identified the most popular property size per top neighborhood:
- **1-bedroom** listings are most common in the top neighborhoods, **except Midtown**, which favors **studio apartments**.

### Create a Flag Column
- In the `listings` sheet, add a new column: `top_listing`.
  - Set to **1** if the listing is in a top-10 neighborhood **and** has the most popular size (1-bedroom or studio for Midtown).
  - Otherwise, set to **0**.

### Estimate Revenue
- In the `calendar` sheet:
  - Create a new column: `revenue_earned`.
    - If `available = "f"` (booked), set `revenue_earned = adjusted_price`.
    - Else, set to `$0`.

- In the `listings` sheet:
  - Add a new column also called `revenue_earned`.
  - Use `SUMIF()` to bring in total `revenue_earned` from the 30-day `calendar` data.
  - Estimate **annual revenue** by multiplying the 30-day total by 12.

### Final Output
- Build a pivot table showing total revenue for listings where `top_listing = 1`.
- Order the listings by revenue to identify the top performers.
