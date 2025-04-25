# Data Set Specifications
_Last Updated: 2025-04-25_

The purpose of this file is to provide details of the data collection process for this project. All log files are saved in CSV format.

---

## Data Sources
At this moment, data is captured from four different sources:
- **Weight Tracker**: Tracks progress in weight and body composition over time.
- **Food Log**: Tracks nutritional information for each meal, including macros (protein, carbs, fat) as well as sodium and cholesterol intake.
- **Workout Journal**: Records details for each exercise performed during a workout session.
- **HR Monitor Log**: Heart rate readings for each workout or physical activity.

---

## Weight Tracker
Each row represents a dated measurement, recording key anthropometric metrics and calculating derived values using the U.S. Navy Body Fat formula, which adjusts based on gender.

![Weight Tracker Example](https://github.com/user-attachments/assets/98f0745a-3b39-411e-8bbf-811ace79d842)

#### Data Specifications

| Column Name             | Description |
|--------------------------|-------------|
| `Date`                   | Date of measurement. |
| `Weight (lb)`            | Total body weight in pounds. |
| `Waist (in)`             | Waist circumference in inches. |
| `Hip (in)`               | Hip circumference in inches. |
| `Neck (in)`              | Neck circumference in inches. |
| `BF%`                    | Estimated body fat percentage. |
| `Fat Mass (lb)`          | Fat mass in pounds, calculated as `(Weight × BF%) / 100`. |
| `Lean Mass (lb)`         | Lean body mass in pounds, calculated as `Weight - Fat Mass`. |
| `Fat Mass Change (lb)`   | Change in fat mass since the previous entry. |
| `Lean Mass Change (lb)`  | Change in lean mass since the previous entry. |

---

## Food Log
Each entry in the log represents an individual food item like "_Market Basket - Fat Free Cottage Cheese, 200 gram(s)_". This data is recorded on the MyFitnessPal application.

![Food Log Example](https://github.com/user-attachments/assets/e3983d8f-9995-4e7b-84ff-31707b67f280)

#### Data Specifications

| Column Name        | Description |
|--------------------|-------------|
| `Food_ID`          | Unique identifier for each food entry. |
| `DATE`             | Date the food item was logged. |
| `MEAL`             | Meal number or type (e.g., Meal 1, Meal 2, Breakfast, Lunch, etc.). |
| `FOODS`            | Raw food name as provided by MyFitnessPal, including brand and size details. |
| `Food_Item`        | Cleaned food name with simplified description (brand/details removed). |
| `Quantity`         | Unit of measurement used (e.g., 1 slice, 200g, 1 pack). |
| `Calories`         | Estimated number of calories in the portion consumed. |
| `Protein (g)`      | Amount of protein in grams. |
| `Carbs (g)`        | Amount of carbohydrates in grams. |
| `Fat (g)`          | Amount of fat in grams. |
| `Cholest (mg)`     | Cholesterol content in milligrams. |
| `Sodium (mg)`      | Sodium content in milligrams. |
| `Sugar (g)`        | Sugar content in grams. |
| `Fiber (g)`        | Dietary fiber content in grams. |

---

## Workout Journal
Each entry represents the number of repetitions (or minutes, where applicable) performed for a specific movement in each round of a workout session. This structure allows tracking of individual movement volume and progress over time.

![Workout Journal Example](https://github.com/user-attachments/assets/9912aaef-62bb-45a9-97dd-f5407b277374)

#### Data Specifications

| Column Name           | Description |
|------------------------|-------------|
| `Movement_Log_ID`      | Unique identifier for each movement entry. |
| `Date`                 | Date the workout session took place. |
| `Workout_Session_Type` | The type or focus of the workout (e.g., Full Body, Upper Body, etc.). |
| `Exercise_Type`        | The movement category (e.g., Push, Pull, Core, Cardio). |
| `Movement_Name`        | The specific movement or exercise performed (e.g., Push-Ups, Plank). |
| `Round_1` to `Round_5` | Number of repetitions (or minutes) completed in each round. |
| `Total_Reps`           | Sum of repetitions or minutes across all rounds for the movement. |
| `Notes`                | Additional details, such as duration units ("Minutes") or modifications. |

---

## HR Monitor Readings
Each entry corresponds to an individual exercise activity recorded using a Garmin Forerunner 235 device. The dataset captures heart rate metrics, movement data, and performance-related statistics for various sessions.

![HR Monitor Example](https://github.com/user-attachments/assets/1b763c2a-e25a-4aa5-9a77-116909b4af44)

#### Data Specifications

| Column Name               | Description |
|----------------------------|-------------|
| `Activity_ID`              | Unique identifier for each activity session. |
| `Activity Type`            | Type of activity (e.g., Other, Running, Cycling). |
| `Date`                     | Date the activity was performed. |
| `Favorite`                 | Boolean indicating if the activity is marked as a favorite. |
| `Title`                    | Title or description of the activity. |
| `Distance`                 | Distance covered during the activity. |
| `Calories`                 | Estimated calories burned. |
| `Time`                     | Duration of the activity (HH:MM:SS). |
| `Avg HR`                   | Average heart rate during the activity. |
| `Max HR`                   | Maximum heart rate recorded. |
| `Aerobic TE`               | Aerobic Training Effect score. |
| `Avg Bike Cadence`          | Average cycling cadence (RPM). |
| `Max Bike Cadence`          | Maximum cycling cadence. |
| `Avg Speed`                | Average speed. |
| `Max Speed`                | Maximum speed. |
| `Total Ascent`             | Total elevation gained. |
| `Total Descent`            | Total elevation lost. |
| `Avg Stride Length`        | Average stride length. |
| `Training Stress Score®`   | Proprietary metric for training load. |
| `Steps`                    | Total steps counted. |
| `Decompression`            | Post-activity decompression status. |
| `Best Lap Time`            | Fastest lap recorded. |
| `Number of Laps`           | Total laps completed. |
| `Moving Time`              | Time spent moving. |
| `Elapsed Time`             | Total activity time. |
| `Min Elevation`            | Minimum elevation reached. |
| `Max Elevation`            | Maximum elevation reached. |

---

## Final Notes
This documentation provides the structural details for all datasets collected so far.  
As new data sources are added or formats are updated, this file should be revised to maintain accuracy and clarity.

For any questions, updates, or future expansions of this project, please refer to this document as the baseline reference.

---

## Version History
- 2025-04-25: Initial creation of documentation.
