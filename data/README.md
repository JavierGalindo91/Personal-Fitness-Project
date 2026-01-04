# Data Set Specifications
_Last Updated: 2026-01-04_

The purpose of this document is to describe the **data collection process, structure, and intended use** of all datasets included in this project.  
All log files are stored in **CSV format** and serve as inputs for downstream analysis and visualization.

---

## Data Sources
At present, data is collected from four primary sources:

- **Weight Tracker**  
  Tracks changes in body weight and body composition over time.
- **Food Log**  
  Records nutritional information for each food item consumed, including macronutrients and selected micronutrients.
- **Workout Journal**  
  Captures exercise-level details for each workout session, enabling volume and movement analysis.
- **HR Monitor Log**  
  Stores heart rate and intensity metrics for each recorded physical activity.
---

## Weight Tracker
Each row represents a **dated body measurement**, capturing key anthropometric metrics and derived body composition values.  
Body fat percentage is calculated using the **U.S. Navy Body Fat Formula**, adjusted by gender.

![Weight Tracker Example](https://github.com/user-attachments/assets/98f0745a-3b39-411e-8bbf-811ace79d842)

### Data Specifications

| Column Name | Description |
|------------|-------------|
| `Date` | Date of measurement. |
| `Weight (lb)` | Total body weight in pounds. |
| `Waist (in)` | Waist circumference in inches. |
| `Hip (in)` | Hip circumference in inches. |
| `Neck (in)` | Neck circumference in inches. |
| `BF%` | Estimated body fat percentage. |
| `Fat Mass (lb)` | Fat mass in pounds, calculated as `(Weight × BF%) / 100`. |
| `Lean Mass (lb)` | Lean body mass in pounds, calculated as `Weight − Fat Mass`. |
| `Fat Mass Change (lb)` | Change in fat mass since the previous entry. |
| `Lean Mass Change (lb)` | Change in lean mass since the previous entry. |

---

## Food Log
Each entry represents a **single food item** logged through the **MyFitnessPal** application (e.g., _Market Basket – Fat Free Cottage Cheese, 200 gram(s)_).  
This dataset supports nutritional intake analysis at both the **daily** and **meal-level** granularity.

![Food Log Example](https://github.com/user-attachments/assets/e3983d8f-9995-4e7b-84ff-31707b67f280)

### Data Specifications

| Column Name | Description |
|------------|-------------|
| `Food_ID` | Unique identifier for each food entry. |
| `DATE` | Date the food item was logged. |
| `MEAL` | Meal identifier or category (e.g., Breakfast, Lunch, Meal 1). |
| `FOODS` | Raw food name as provided by MyFitnessPal, including brand and portion details. |
| `Quantity` | Serving size and unit (e.g., 1 slice, 200 g, 1 pack). |
| `Calories` | Estimated calories consumed. |
| `Protein (g)` | Protein content in grams. |
| `Carbs (g)` | Carbohydrate content in grams. |
| `Fat (g)` | Fat content in grams. |
| `Cholest (mg)` | Cholesterol content in milligrams. |
| `Sodium (mg)` | Sodium content in milligrams. |
| `Sugar (g)` | Sugar content in grams. |
| `Fiber (g)` | Dietary fiber content in grams. |

---

## Workout Journal
Each row represents a **movement-level entry** within a workout session.  
This structure enables tracking of **exercise volume**, **round-based performance**, and **movement-specific progression** over time.

![Workout Journal Example](https://github.com/user-attachments/assets/9912aaef-62bb-45a9-97dd-f5407b277374)

### Data Specifications

| Column Name | Description |
|------------|-------------|
| `Movement_Log_ID` | Unique identifier for each movement entry. |
| `Date` | Date the workout session occurred. |
| `Workout_Session_Type` | Overall workout classification (e.g., Full Body, Upper Body). |
| `Exercise_Type` | Movement category (e.g., Push, Pull, Core, Cardio). |
| `Movement_Name` | Specific exercise performed (e.g., Push-Ups, Plank). |
| `Warm Up`, `Round_1`–`Round_5` | Repetitions or minutes completed in each round. |
| `Total_Reps` | Total repetitions or minutes across all rounds. |
| `Notes` | Additional context such as unit type or exercise modifications. |

---

## HR Monitor Readings
Each row represents a **single recorded activity session** captured via a **Garmin Forerunner 235** and enriched with **derived duration and heart-rate zone metrics**.

This dataset supports **cardiovascular intensity analysis**, **training load evaluation**, and **longitudinal performance tracking**.

<img width="1670" height="109" alt="HR Monitor Example" src="https://github.com/user-attachments/assets/28957195-4d47-4437-b877-efe800986945" />

### Dataset Purpose
This dataset is used to answer questions such as:
- How much time is spent in each heart-rate zone per workout?
- How does training intensity change over time?
- What relationships exist between duration, calories, heart rate, and Aerobic Training Effect?
- How do different workout types distribute cardiovascular stress?

### Data Specifications

| Column Name | Description |
|------------|-------------|
| `Activity_ID` | Unique identifier for each recorded activity session. |
| `Date` | Calendar date of the activity. |
| `Month` | Month extracted from `Date` (used for aggregation and filtering). |
| `Day` | Day of month extracted from `Date`. |
| `Year` | Year extracted from `Date`. |
| `Title` | User-defined activity label (e.g., KB Circuit, Boxing Circuit). |
| `Calories` | Estimated calories burned during the session. |
| `Time` | Total elapsed duration in `HH:MM:SS` format. |
| `Avg HR` | Average heart rate (beats per minute). |
| `Max HR` | Maximum heart rate recorded. |
| `Aerobic TE` | Aerobic Training Effect score (Garmin metric). |
| `Time in Zone 1` | Time spent in heart-rate Zone 1, `HH:MM:SS`. |
| `Time in Zone 2` | Time spent in heart-rate Zone 2, `HH:MM:SS`. |
| `Time in Zone 3` | Time spent in heart-rate Zone 3, `HH:MM:SS`. |
| `Time in Zone 4` | Time spent in heart-rate Zone 4, `HH:MM:SS`. |
| `Time in Zone 5` | Time spent in heart-rate Zone 5, `HH:MM:SS`. |
| `TZ1_Mins` | Zone 1 time converted to decimal minutes. |
| `TZ2_Mins` | Zone 2 time converted to decimal minutes. |
| `TZ3_Mins` | Zone 3 time converted to decimal minutes. |
| `TZ4_Mins` | Zone 4 time converted to decimal minutes. |
| `TZ5_Mins` | Zone 5 time converted to decimal minutes. |
| `Total_Mins` | Total session duration in decimal minutes. |

---

## Final Notes
This document serves as the **baseline reference** for all datasets currently used in the project.  
As new data sources are added or existing formats evolve, this file should be updated to ensure continued accuracy and consistency.

---

## Version History
- **2025-04-25** — Initial creation of documentation  
- **2026-01-04** — Structure and HR dataset expanded and refined
