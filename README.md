# Data Analytics Projects:

This repository showcases some of my analytics projects.

I'm a versatile individual with experience collecting, transforming and organizing data for analysis to help make informed decisions and possess excellent proficiency of platforms for effective data analysis including SQL, Python, R, Spreadsheets and Tableau.



## Project 1 - Bellabeat Case Study

**For this project, we followed a six step analysis process**

**Tools** - SQL (BigQuery), Spreadsheets and Tableau

### Step 1 - ASK 
* In this step, we will define the Business Task and identify stakeholders.
* **Business Task** - Analyze smart device user data in order to gain insights into how customers use non-Bellabeat smart devices. Then apply these insights to Bellabeat Leaf.
* **Stakeholders** - CEO, Co-founders and Marketing Analytics Team

### Step 2 - PREPARE
* In this step, we will identify data sources.
* **Data Source** - Kaggle <https://www.kaggle.com/datasets/arashnic/fitbit>
* Data is well organized, with the option of both wide and long data.
* The data is reliable and is anonymized.

### Step 3 - PROCESS
* In this step, we will perform data cleaning/manipulation.
* The data cleaning process included removing duplicates, fixing incorrect formats and handling missing data.
* We will verify data integrity via conditional formatting and data validation.

### Step 4 - ANALYZE
* The data contains metrics such as calories, steps, intensity, etc. which can be used to provide basic goals/targets in the app/watch interface.
* Lightly active distance represents a large amount of total active distance.
* Sedentary minutes represents more than 50%  of the total active minutes.
* On an average, 15.8% of the time, the device was inactive (charging or device not worn)
* We deduced metrics such as Max BPM - 200+, Min BPM - 37, Average Max BPM - 171.28 , Average Min BPM - 46.57. These can be used to set up alerts for Upper and lower limit of BPM, as per critical medical conditions.
* Individuals are most active from 5-7 PM, on an average.
* Individuals have highest METs (Metabolic Equivalents) between 9-11 AM and 6-7 PM. Metabolic Equivalents (METs) are a great way to assess the general fitness of an individual.
* Average sleep record was 1.1 in a day.
* Most of the individuals are sleeping less than 8 hours a day. 
* According to the sleep value ID, most individuals are in the ASLEEP ZONE when they are in bed, with a few individuals alternating between ASLEEP and RESTLESS ZONES.
* Most people prefer automatic report generation, accounting for more than 50% of the reports generated.

### Step 5 - SHARE
* We will now create data visualizations using Tableau.
* Then, we will draft an effective presentation for our meeting with the stakeholders.

![Daily Active Distance](https://github.com/kunalbarthwal/portfolio/blob/main/1.%20Bellabeat%20Case%20Study/Tableau%20Visualizations/Daily%20Active%20Distance.png "Daily Active Distance")

![Average Sleep Value](https://github.com/kunalbarthwal/portfolio/blob/main/1.%20Bellabeat%20Case%20Study/Tableau%20Visualizations/Sleep%20Value.png
 "Average Sleep Value")

### Step 6 - ACT
* Based on our analysis, there are plenty of parameters that can be utilized effectively to create new features and increase device/app interaction.
* We can apply these insights by creating new features, alerts such as vibrations/app notifications for critical health features/personal targets and health scores to attract customers.
* Stakeholders can collaborate with R&D and marketing team to develop and test new features.

![Conclusion](https://github.com/kunalbarthwal/portfolio/blob/main/1.%20Bellabeat%20Case%20Study/Tableau%20Visualizations/Conclusion.png "Conclusion")

**Case Study Link** - <https://github.com/kunalbarthwal/portfolio/tree/main/1.%20Bellabeat%20Case%20Study>
