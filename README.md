# Data Analytics Projects:

This repository showcases some of my analytics projects.



## Project 1 - Divvy Bikeshare Analysis Case Study

**We followed a six step analysis process**

**Tools** - Python, Pandas , NumPy, Matplotlib


### Step 1 - ASK 
* In this step, we will define the Business Task and identify stakeholders.
* **Business Task** - Devise a new marketing strategy to convert casual riders to annual members, by understanding how they use bikes differently.
* **Stakeholders** - Director of Marketing, Executive Team and Marketing Analytics Team.

### Step 2 - PREPARE
* In this step, we will identify data sources.
* **Data Source** - <https://divvy-tripdata.s3.amazonaws.com/index.html>
* Data is well organized, and was publicly available in an Amazon S3 storage.
* The data is reliable and is anonymized.

### Step 3 - PROCESS
* In this step, we will perform data cleaning/manipulation.
* The data cleaning process included removing duplicates for *ride_id*, changing datatypes of some columns, creating new columns for *trip_duration* and *day* & renaming columns for ease of use.
* We will verify data integrity via summary statistics functions like *head*, *describe* & *info* in Python.

### Step 4 - ANALYZE
* People tend to use electric bikes the most (52.82%), followed by classic bikes (45.44%).
* Casual customers prefer electric bikes over classic bikes, by a margin of 15%.
* Annual members don't use docked bikes.
* Casual customers use bikes mostly on weekends (Saturday-Sunday), and Annual members use bikes mostly on weekdays (Monday-Friday).
* Bikes are most in-demand around 4-6 PM (5 PM Peak) and least in-demand around 3-4 PM.
* There is a sudden surge in demand for Annual members around 7-9 AM (8 AM Peak), usually when people commute to work.
* Most popular stations for Casual customers are *Streeter Dr & Grand Ave*, *Dusable Lake Shore Dr & Monroe St* and *Michigan Ave & Oak St*. These areas have museums, parks and tourist streets which confirms that casual members use bikes mostly for social engagements on weekends.
* Most popular stations for Annual members are *Kingsbury St & Kinzie St*, *Clark St & Elm St* and *Clinton St & Washington Blvd*. These areas have apartments, businesses, corporate offices and services like shipping, ecommerce, etc. which confirms that annual members use bikes mostly for commuting to work on weekdays.
* According to statistical data, average ride duration of casual customers (19:48) is almost twice as annual members (10:50).

### Step 5 - SHARE
* We will now create data visualizations using Matplotlib and Shapely libraries in Python.
* Then, we will draft an effective presentation.

<img src="2. Divvy Bikeshare Case Study/Data Visualization/Bikes used per Day - Casual Customers.png" class="img-responsive" alt="">

<img src="2. Divvy Bikeshare Case Study/Data Visualization/Top 10 Start Stations - Casual Customers.png" class="img-responsive" alt="">


### Step 6 - ACT
* Based on our analysis, there are some actions for devising an effective marketing strategy.
* Since casual customers use electric bikes the most, we can structure the pricing plan in such a way that it costs less for using an electric bike when you are an annual member.
* They mostly use bikes on weekends. We can provide plans or discounts on weekends for those who have purchased annual subscriptions.
* They have almost twice the ride duration of annual members. We can decrease pricing (per minute) for annual members so that casual customers would consider switching to annual memberships.
* Marketing team can collaborate with the pricing team to make necessary changes and devise an new marketing strategy to convert casual riders to annual members

<img src="2. Divvy Bikeshare Case Study/Data Visualization/Conclusion.png" class="img-responsive" alt="">


**Presentation** - 

**Documentation** - <https://github.com/kunalbarthwal/portfolio/tree/main/2.%20Divvy%20Bikeshare%20Case%20Study>



## Project 2 - Bellabeat Data Analysis Case Study

**We followed a six step analysis process**

**Tools** - SQL (BigQuery), Spreadsheets and Tableau


### Step 1 - ASK 
* In this step, we will define the Business Task and identify stakeholders.
* **Business Task** - Analyze smart device user data in order to gain insights into how customers use non-Bellabeat smart devices. Then apply these insights to Bellabeat Leaf.
* **Stakeholders** - CEO, Co-founders and Marketing Analytics Team

### Step 2 - PREPARE
* In this step, we will identify data sources.
* **Data Source** - <https://www.kaggle.com/datasets/arashnic/fitbit>
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

<img src="1. Bellabeat Case Study/Tableau Visualizations/Daily Active Distance.png" class="img-responsive" alt="">

<img src="1. Bellabeat Case Study/Tableau Visualizations/Sleep Value.png" class="img-responsive" alt="">


### Step 6 - ACT
* Based on our analysis, there are plenty of parameters that can be utilized effectively to create new features and increase device/app interaction.
* We can apply these insights by creating new features, alerts such as vibrations/app notifications for critical health features/personal targets and health scores to attract customers.
* Stakeholders can collaborate with R&D and marketing team to develop and test new features.

<img src="1. Bellabeat Case Study/Tableau Visualizations/Conclusion.png" class="img-responsive" alt="">


**Presentation** - 

**Documentation** - <https://github.com/kunalbarthwal/portfolio/tree/main/1.%20Bellabeat%20Case%20Study>
