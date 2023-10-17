## This file inlcudes the steps taken for analyzing data using SQL (BigQuery)


### Step 1 - Created new columns for active_distance, active_minutes and total_minutes:

SELECT 
 Id,
 ActivityDate,
 TotalSteps,
 TotalDistance,
 TrackerDistance,
 LoggedActivitiesDistance,
 VeryActiveDistance,
 ModeratelyActiveDistance,
 LightActiveDistance,
 SedentaryActiveDistance,
 VeryActiveMinutes,
 FairlyActiveMinutes AS moderately_active_minutes,
 LightlyActiveMinutes AS lightly_active_minutes,
 SedentaryMinutes,
 Calories, 
 (VeryActiveDistance + ModeratelyActiveDistance + LightActiveDistance) AS active_distance,
 (VeryActiveMinutes + FairlyActiveMinutes + LightlyActiveMinutes) AS active_minutes,
 (VeryActiveMinutes + FairlyActiveMinutes + LightlyActiveMinutes + SedentaryMinutes) AS total_minutes
FROM 
 `my-project-wangs.bellabeat.daily_activity_merged` 
ORDER BY 
 Id, ActivityDate


### Step 2 - Filtered the average values, ordered by date:

SELECT 
 ActivityDate AS activity_date,
 AVG(TotalSteps) AS total_steps, 
 AVG(TotalDistance) AS total_distance, 
 AVG(TrackerDistance) AS tracker_distance, 
 AVG(LoggedActivitiesDistance) AS logged_activities_distance, 
 AVG(VeryActiveDistance) AS very_active_distance, 
 AVG(ModeratelyActiveDistance) AS moderately_active_distance, 
 AVG(LightActiveDistance) AS lightly_active_distance, 
 AVG(SedentaryActiveDistance) AS sedentary_active_distance, 
 AVG(VeryActiveMinutes) AS very_active_minutes, 
 AVG(FairlyActiveMinutes) AS moderately_active_minutes, 
 AVG(LightlyActiveMinutes) AS lightly_active_minutes, 
 AVG(SedentaryMinutes) AS sedentary_minutes, 
 AVG(Calories) AS calories,
 AVG(ActiveDistance) AS active_distance,
 AVG(ActiveMinutes) AS active_minutes,
 AVG(TotalMinutes) AS total_minutes
FROM 
 `my-project-wangs.bellabeat.daily_activity_merged_v2` 
GROUP BY ActivityDate 
ORDER BY ActivityDate


### Step 3 - Merged the hourly calories, intensities and steps data into a single table using JOIN:

SELECT 
 hourly_calories.Id AS id,
 hourly_calories.ActivityDate AS activity_date,
 hourly_calories.ActivityHour AS activity_hour,
 hourly_calories.Calories AS calories,
 hourly_intensities.TotalIntensity AS total_intensity,
 hourly_intensities.AverageIntensity AS average_intensity,
 hourly_steps.StepTotal AS total_steps
FROM 
 `my-project-wangs.bellabeat.hourly_calories` AS hourly_calories
FULL OUTER JOIN
 `my-project-wangs.bellabeat.hourly_intensities` AS hourly_intensities
ON  
 hourly_calories.Id = hourly_intensities.Id AND
 hourly_calories.ActivityDate = hourly_intensities.ActivityDate AND
 hourly_calories.ActivityHour = hourly_intensities.ActivityHour
FULL OUTER JOIN
 `my-project-wangs.bellabeat.hourly_steps` AS hourly_steps
ON
 hourly_intensities.Id = hourly_steps.Id AND
 hourly_intensities.ActivityDate = hourly_steps.ActivityDate AND
 hourly_intensities.ActivityHour = hourly_steps.ActivityHour
ORDER BY 
 hourly_intensities.Id, 
 hourly_intensities.ActivityDate, 
 hourly_intensities.ActivityHour


### Step 4 - Sorted the hourly data by taking average by date and time:

SELECT 
 activity_date,
 activity_hour,
 AVG(calories) AS calories,
 AVG(total_intensity) AS total_intensity,
 AVG(average_intensity) AS average_intensity,
 AVG(total_steps) AS total_steps
FROM 
 `my-project-wangs.bellabeat.hourly_activity_merged`
GROUP BY 
 activity_date,
 activity_hour


### Step 5 - Sorted the hourly data by taking average by time:

SELECT 
 activity_hour,
 AVG(calories) AS calories,
 AVG(total_intensity) AS total_intensity,
 AVG(average_intensity) AS average_intensity,
 AVG(total_steps) AS total_steps
FROM 
 `my-project-wangs.bellabeat.hourly_activity_merged`
GROUP BY 
 activity_hour

You can use the following to aggregate the date and time into a datetime format, if needed:

SELECT *,
cast(concat(activity_date, ' ', activity_hour) as datetime) AS time_stamp
FROM `my-project-wangs.bellabeat.hourly_activity_merged_v2` 
ORDER BY time_stamp


### Step 6 - Used minute METs, calories, intensities and steps data and merged them into minute_activity_merged table via JOIN:

SELECT 
 minute_METs.Id AS id,
 minute_METs.ActivityDate AS activity_date,
 minute_METs.ActivityMINUTE AS activity_minute,
 minute_METs.METs AS metabolic_equivalents,
 minute_calories.Calories AS calories,
 minute_intensities.Intensity AS intensities,
 minute_steps.Steps AS steps
FROM 
 `my-project-wangs.bellabeat.minute_METs` AS minute_METs
FULL OUTER JOIN
 `my-project-wangs.bellabeat.minute_calories` AS minute_calories
ON  
 minute_METs.Id = minute_calories.Id AND
 minute_METs.ActivityDate = minute_calories.ActivityDate AND
 minute_METs.ActivityMinute = minute_calories.ActivityMinute
FULL OUTER JOIN
 `my-project-wangs.bellabeat.minute_intensities` AS minute_intensities
ON
 minute_calories.Id = minute_intensities.Id AND
 minute_calories.ActivityDate = minute_intensities.ActivityDate AND
 minute_calories.ActivityMinute = minute_intensities.ActivityMinute
FULL OUTER JOIN
 `my-project-wangs.bellabeat.minute_steps` AS minute_steps
ON
 minute_intensities.Id = minute_steps.Id AND
 minute_intensities.ActivityDate = minute_steps.ActivityDate AND
 minute_intensities.ActivityMinute = minute_steps.ActivityMinute
ORDER BY 
 minute_METs.Id, 
 minute_METs.ActivityDate, 
 minute_METs.ActivityMinute


### Step 7 - Sorted the minute data by taking average by date and time:

SELECT 
 activity_date,
 activity_minute,
 AVG(metabolic_equivalents) AS metabolic_equivalents,
 AVG(calories) AS calories,
 AVG(intensities) AS intensities,
 AVG(steps) AS steps
FROM 
 `my-project-wangs.bellabeat.minute_activity_merged`
GROUP BY 
 activity_date,
 activity_minute

You can use the following to aggregate the date and time into a datetime format, if needed:

SELECT *,
cast(concat(activity_date, ' ', activity_minute) as datetime) AS time_stamp
FROM `my-project-wangs.bellabeat.minute_activity_merged_v2` 
ORDER BY time_stamp


### Step 8 - Sorted the minute data by taking average by time:

SELECT 
 activity_minute,
 AVG(metabolic_equivalents) AS metabolic_equivalents,
 AVG(calories) AS calories,
 AVG(intensities) AS intensities,
 AVG(steps) AS steps
FROM 
 `my-project-wangs.bellabeat.minute_activity_merged_v2`
GROUP BY 
 activity_minute


### Step 9 - Using minute_sleep_merged data, took average of sleep_value by id, activitydate and logid:

SELECT
Id,
ActivityDate AS activity_date,
AVG(sleepvalue) AS sleep_value,
logId AS log_id
FROM  
 `my-project-wangs.bellabeat.minute_sleep_merged`
GROUP BY
 Id,
 log_id,
 activity_date


### Step 10 - Took average by id:

SELECT
Id,
AVG(sleep_value) AS sleep_value
FROM  
 `my-project-wangs.bellabeat.minute_sleep_merged_v2`
GROUP BY
 Id


### Step 11 - Using sleep_day_merged data, took average of all integer values by ID:

SELECT 
 Id,
 AVG(TotalSleepRecords) AS total_sleep_records,
 AVG(TotalMinutesAsleep) AS total_minutes_asleep,
 AVG(TotalTimeInBed) AS total_time_in_bed
FROM 
`my-project-wangs.bellabeat.sleep_day_merged` 
GROUP BY
Id


### Step 12 - For the weightLoginfo_merged data, we don't need to perform cleaning and processing as the data is short and speaks for itself. We'll just rename the columns:

SELECT 
Id AS id,
Date AS date,
WeightKg AS weight_kg,
WeightPounds AS weight_pounds,
Fat AS fat,
IsManualReport AS report_type,
LogId AS log_id
FROM `my-project-wangs.bellabeat.weight_log_info_merged` 


### Step 13 - Rename columns for heartrate_seconds_merged:

SELECT 
Id AS id,
TimeStamp AS time_stamp,
Date AS date,
Time AS time,
Value AS bpm
FROM `my-project-wangs.bellabeat.heartrate_seconds_merged` 


### Step 14 - Took max and min values of heartrate by id and date:

SELECT 
 id,
 date,
 MAX(bpm),
 MIN(bpm)
FROM 
 `my-project-wangs.bellabeat.heartrate_seconds_merged_v2` 
GROUP BY
id,
date


### Step 15 - Sorted the data via id:

SELECT 
 id,
 MAX(bpm),
 MIN(bpm)
FROM 
 `my-project-wangs.bellabeat.heartrate_seconds_merged_v2` 
GROUP BY
id
