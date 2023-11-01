# Divvy Bikeshare Analysis Case Study

**We followed a six step analysis process**

**Tools** - Python (Pandas , NumPy, Matplotlib and Plotly)


## Step 1 - ASK 
* In this step, we will define the Business Task and identify stakeholders.
* **Business Task** - Devise a new marketing strategy to convert casual riders to annual members, by understanding how they use bikes differently.
* **Stakeholders** - Director of Marketing, Executive Team and Marketing Analytics Team.

## Step 2 - PREPARE
* In this step, we will identify data sources.
* **Data Source** - <https://divvy-tripdata.s3.amazonaws.com/index.html>
* Data is well organized, and was publicly available in an Amazon S3 storage.
* The data is reliable and is anonymized.

## Step 3 - PROCESS
* In this step, we will perform data cleaning/manipulation.
* The data cleaning process included removing duplicates for *ride_id*, changing datatypes of some columns, creating new columns for *trip_duration* and *day* & renaming columns for ease of use.
* We will verify data integrity via summary statistics functions like *head*, *describe* & *info* in Python.

## Step 4 - ANALYZE
* People tend to use electric bikes the most (52.82%), followed by classic bikes (45.44%).
* Casual customers prefer electric bikes over classic bikes, by a margin of 15%.
* Annual members don't use docked bikes.
* Casual customers use bikes mostly on weekends (Saturday-Sunday), and Annual members use bikes mostly on weekdays (Monday-Friday).
* Bikes are most in-demand around 4-6 PM (5 PM Peak) and least in-demand around 3-4 PM.
* There is a sudden surge in demand for Annual members around 7-9 AM (8 AM Peak), usually when people commute to work.
* Most popular stations for Casual customers are *Streeter Dr & Grand Ave*, *Dusable Lake Shore Dr & Monroe St* and *Michigan Ave & Oak St*. These areas have museums, parks and tourist streets which confirms that casual members use bikes mostly for social engagements on weekends.
* Most popular stations for Annual members are *Kingsbury St & Kinzie St*, *Clark St & Elm St* and *Clinton St & Washington Blvd*. These areas have apartments, businesses, corporate offices and services like shipping, ecommerce, etc. which confirms that annual members use bikes mostly for commuting to work on weekdays.
* According to statistical data, average ride duration of casual customers (19:48) is almost twice as annual members (10:50).

## Step 5 - SHARE
* We will now create data visualizations using Matplotlib and Shapely libraries in Python.
* Then, we will draft an effective presentation.

<img src="Data Visualization/Bikes used per Day - Casual Customers.png" class="img-responsive" alt="">

<img src="Data Visualization/Most Popular Start Stations - Casual Customers.png" class="img-responsive" alt="">


## Step 6 - ACT
* Based on our analysis, there are some actions for devising an effective marketing strategy.
* Since casual customers use electric bikes the most, we can structure the pricing plan in such a way that it costs less for using an electric bike when you are an annual member.
* They mostly use bikes on weekends. We can provide plans or discounts on weekends for those who have purchased annual subscriptions.
* They have almost twice the ride duration of annual members. We can decrease pricing (per minute) for annual members so that casual customers would consider switching to annual memberships.
* Bikes peak in demand at 5 PM. We can provide enhanced bike availability for annual members during rush hour, so that casual customers realize that annual membership is worth it.
* Marketing team can collaborate with the pricing team to make necessary changes and devise an new marketing strategy to convert casual riders to annual members

<img src="Data Visualization/Conclusion.png" class="img-responsive" alt="">


**Documentation** - <https://github.com/kunalbarthwal/portfolio/tree/main/2.%20Divvy%20Bikeshare%20Case%20Study>


