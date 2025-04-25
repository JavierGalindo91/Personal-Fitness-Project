# Data Set Specifications
_Last Updated: April 25, 2025_

The purpose of this file is to provide details of the data collection process. All log files are saved in CSV format. 

## DATA SOURCES
At this moment, data is captured from four different sources:
- **_Weight Tracker_**: Tracks progress in weight and body composition over time.
- **_Food Log_**: Tracks nutritional information for each meal, including macros (protein, carbs, fat) as well as sodium and cholesterol intake.
- **_Workout Journal_**: Records details for each exercise performed during a workout session.
- **_HR Monitor Log_**: Heart Rate readings for each workout/physical activity.

## WEIGHT TRACKER
Each row represents a dated measurement, recording key anthropometric metrics and calculating derived values using the U.S. Navy Body Fat formula, which adjusts based on gender.

![image](https://github.com/user-attachments/assets/98f0745a-3b39-411e-8bbf-811ace79d842)

### Data Specifications

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

### Data Specifications
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

### Data Specifications
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

## HR MONITOR READNGS
Each entry corresponds to an individual exercise activity recorded using a Garmin Forerunner 235 device. The dataset captures heart rate metrics, movement data, and performance-related statistics for various sessions.

![image](https://github.com/user-attachments/assets/1b763c2a-e25a-4aa5-9a77-116909b4af44)

### Data Specifications
| Column Name               | Description |
|----------------------------|-------------|
| `Activity_ID`              | Unique identifier for each activity session. |
| `Activity Type`            | Type of activity (e.g., Other, Running, Cycling). |
| `Date`                     | Date the activity was performed. |
| `Favorite`                 | Boolean indicating if the activity is marked as a favorite. |
| `Title`                    | Title or description of the activity. |
| `Distance`                 | Distance covered during the activity (miles or kilometers depending on settings). |
| `Calories`                 | Estimated calories burned. |
| `Time`                     | Duration of the activity (HH:MM:SS). |
| `Avg HR`                   | Average heart rate during the activity (beats per minute). |
| `Max HR`                   | Maximum heart rate recorded during the activity. |
| `Aerobic TE`               | Aerobic Training Effect — a score indicating how the activity improves aerobic fitness. |
| `Avg Bike Cadence`          | Average cycling cadence (revolutions per minute); applicable for biking activities. |
| `Max Bike Cadence`          | Maximum cycling cadence recorded. |
| `Avg Speed`                | Average speed during the activity. |
| `Max Speed`                | Maximum speed achieved. |
| `Total Ascent`             | Total elevation gained (typically in feet or meters). |
| `Total Descent`            | Total elevation lost. |
| `Avg Stride Length`        | Average stride length (meters) for running/walking activities. |
| `Training Stress Score®`   | Proprietary metric estimating the training load of the session. |
| `Steps`                    | Total steps counted during the activity. |
| `Decompression`            | Status indicator (e.g., "No" or "Yes") if post-activity decompression advice is provided. |
| `Best Lap Time`            | Fastest lap time recorded (if applicable). |
| `Number of Laps`           | Total number of laps during the activity. |
| `Moving Time`              | Actual time spent moving (may differ from elapsed time if there were pauses). |
| `Elapsed Time`             | Total time from start to end of the activity, including pauses. |
| `Min Elevation`            | Minimum elevation reached during the activity. |
| `Max Elevation`            | Maximum elevation reached during the activity. |

## Final Notes
This documentation provides the structural details for all datasets collected so far. As new data sources are added or existing formats are updated, this file should be revised to maintain accuracy and clarity. 

For questions, updates, or expansion of this project, please refer to this document as the baseline reference.


