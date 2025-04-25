# Data Set Specifications

The purpose of this file is to provide details of the data collection process. All log files are saved in CSV format. 

## DATA SOURCES
At this moment, data is captured from four different sources:
- **_Weight Tracker_**: Tracks progress in weight and body composition over time.
- **_Food Log_**: Logs details for each entry like macros and other components like sodium intake and cholesterol.
- **_Workout Journal_**: Records details for each exercise performed during a workout session.
- **_HR Monitor Log_**: Heart Rate readings for each workout/physical activity.

## WEIGHT TRACKER
Each row represents a dated measurement, recording key anthropometric metrics and calculating derived values using the U.S. Navy Body Fat formula, which adjusts based on gender.

![image](https://github.com/user-attachments/assets/98f0745a-3b39-411e-8bbf-811ace79d842)

### Weight Tracker Column Specifications

| Column Name             | Description |
|-------------------------|-------------|
| `Date`                  | Date of measurement. |
| `Weight (lb)`           | Total body weight in pounds. |
| `Waist (in)`            | Waist circumference in inches. |
| `Hip (in)`              | Hip circumference in inches. |
| `Neck (in)`             | Neck circumference in inches. |
| `BF%`                   | Estimated body fat percentage. |
| `Fat Mass (lb)`         | Fat mass in pounds, calculated as `(Weight × BF%) / 100`. |
| `Lean Mass (lb)`        | Lean body mass in pounds, calculated as `Weight - Fat Mass`. |
| `Fat Mass Change (lb)`  | Change in fat mass since the previous entry. |
| `Lean Mass Change (lb)` | Change in lean mass since the previous entry. |

## FOOD LOG
Each entry in the log represents and individual food item like "_Market Basket - Fat Free Cottage Cheese, 200 gram(s)_". This data is recorded on the MyFitnessPal application. 

![image](https://github.com/user-attachments/assets/e3983d8f-9995-4e7b-84ff-31707b67f280)

### Food Log Column Specifications
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

## WORKOUT JOURNAL
Each entry represents the number of repetitions (or minutes, where applicable) performed for a specific movement in each round of a workout session. This structure allows tracking of individual movement volume and progress over time.

![image](https://github.com/user-attachments/assets/9912aaef-62bb-45a9-97dd-f5407b277374)

### Workout Jorunal Column Specifications
| Column Name           | Description |
|------------------------|-------------|
| `Movement_Log_ID`      | Unique identifier for each movement entry. |
| `Date`                 | Date the workout session took place. |
| `Workout_Session_Type` | The type or focus of the workout (e.g., Full Body, Upper Body, etc.). |
| `Exercise_Type`        | The movement category (e.g., Push, Pull, Core, Cardio). |
| `Movement_Name`        | The specific movement or exercise performed (e.g., Push-Ups, Plank). |
| `Round_1` to `Round_5` | Number of repetitions (or duration in minutes) completed in each round. |
| `Total_Reps`           | Sum of repetitions or minutes across all rounds for the movement. |
| `Notes`                | Additional details, such as duration units ("Minutes") or modifications. |
