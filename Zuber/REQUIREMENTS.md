# Zuber Ride-Share Data Analysis Project

## Overview

Zuber is a new ride-sharing company preparing to launch in Chicago. As part of the analytics team, your goal is to uncover patterns in taxi ride data to help Zuber understand passenger preferences and external factors affecting ride behavior—particularly the influence of weather.

You will work with a structured database containing ride, vehicle, neighborhood, and weather data. The analysis is split into two parts: exploratory data analysis (Tasks 1–4) and a weather-impact investigation on travel durations (Tasks 5–7).

---

## Data Description

The project uses the following database tables:

### `neighborhoods`  
Contains data on Chicago neighborhoods.
- `name`: Name of the neighborhood  
- `neighborhood_id`: Unique identifier for the neighborhood  

### `cabs`  
Information on taxi vehicles.
- `cab_id`: Vehicle code  
- `vehicle_id`: Technical ID of the vehicle  
- `company_name`: Company that owns the cab  

### `trips`  
Details of taxi rides.
- `trip_id`: Unique identifier for each ride  
- `cab_id`: Foreign key referencing the cab  
- `start_ts`: Start timestamp (rounded to the hour)  
- `end_ts`: End timestamp (rounded to the hour)  
- `duration_seconds`: Ride duration in seconds  
- `distance_miles`: Ride distance in miles  
- `pickup_location_id`: Pickup neighborhood ID  
- `dropoff_location_id`: Dropoff neighborhood ID  

### `weather_records`  
Hourly weather data.
- `record_id`: Unique identifier for weather record  
- `ts`: Timestamp of weather record (rounded to the hour)  
- `temperature`: Recorded temperature  
- `description`: Weather conditions (e.g. "light rain", "clear sky")  

Note: There is no direct link between `trips` and `weather_records`, but they can be joined using timestamps (`start_ts` = `ts`).

---

## Tasks

### Tasks 1–4: Exploratory Data Analysis

**Task 1**  
Print the `company_name` field. Find and count the number of taxi rides for each company from **November 15 to 16, 2017**.  
- Name the resulting count field: `trips_amount`  
- Sort results by `trips_amount` in descending order  

**Task 2**  
Count the number of rides for taxi companies whose names include **"Yellow"** or **"Blue"** from **November 1 to 7, 2017**.  
- Name the count field: `trips_amount`  
- Group results by `company_name`  

**Task 3**  
For the same week (**November 1 to 7, 2017**), calculate the number of rides for the most popular companies: **Flash Cab** and **Taxi Affiliation Services**.  
- Combine rides from all other companies under the group "Other"  
- Group by company name using the field `company`  
- Name the ride count field: `trips_amount`  
- Sort results in descending order by `trips_amount`  

**Task 4**  
Retrieve the neighborhood identifiers for:
- **The Loop**
- **O'Hare International Airport**  
Use the `neighborhoods` table.

---

### Tasks 5–7: Weather Impact on Ride Duration

**Task 5**  
From the `weather_records` table, retrieve weather data for each hour.  
- Create a new field `weather_conditions` using a `CASE` statement:
  - Set to `"Bad"` if `description` contains "rain" or "storm"  
  - Otherwise, set to `"Good"`  
- Final output must include:
  - `ts` (date and hour)
  - `weather_conditions`  

**Task 6**  
From the `trips` table, retrieve all rides that:
- Start in **The Loop** (`pickup_location_id = 50`)  
- End at **O'Hare** (`dropoff_location_id = 63`)  
- Occur on a **Saturday**  

For these rides:
- Join with the `weather_records` data using `start_ts = ts`  
- Add the `weather_conditions` field (from Task 5)  
- Include ride duration (`duration_seconds`)  
- Exclude records where weather data is unavailable  

**Final table columns:**
1. `start_ts`
2. `weather_conditions`
3. `duration_seconds`

Sort the output by `trip_id`.
