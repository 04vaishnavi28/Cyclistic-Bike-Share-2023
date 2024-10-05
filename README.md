# Cyclistic-Bike-Share-2023
This project analyzes bike usage patterns to understand how casual riders and annual members of Cyclistic, a bike-share company in Chicago, use bikes differently. The goal is to provide data-driven insights to help convert casual riders into annual members.

## About the company
In 2016, Cyclistic launched a successful bike-share offering. Since then, the program has grown to a fleet of 5,824 bicycles that are geotracked and locked into a network of 692 stations across Chicago. The bikes can be unlocked from one station and returned to any other station in the system anytime.

## Scenario
The director of marketing at Cyclistic, a bike-share company in Chicago believes the company’s future success depends on maximizing the number of annual memberships.

## Analytical Goals
Understand how casual riders and annual members use Cyclistic bikes differently. From these insights, design a new marketing strategy to convert casual riders into annual members.

## Steps
The steps of the data analysis process: **Ask**, **Prepare**, **Process**, **Analyze**, **Share**, and **Act**.

### Ask
Three questions will guide the future marketing program:
1. How do annual members and casual riders use Cyclistic bikes differently?
2. Why would casual riders buy Cyclistic annual memberships?
3. How can Cyclistic use digital media to influence casual riders to become members?
**Key tasks** 
● Identify the business task
● Consider key stakeholders

### Prepare
Use Cyclistic’s historical trip data to analyze and identify trends. [Download the previous 12 months of Cyclistic trip data here](https://divvy-tripdata.s3.amazonaws.com/index.html).
*Jan 2023 to Dec 2023 data have been used in this analysis.*
**Key tasks**
● Download data and store it appropriately.
● Identify how it’s organized.
● Sort and filter the data.
● Determine the credibility of the data.

### Process
1. Collect data.
2. Wrangle data and combine into a single file.
3. Clean up and add data to prepare for analysis.
    Inspect the new table that has been created
    There are a few problems we will need to fix:
      The data can only be aggregated at the ride-level, which is too granular. We will want to add some additional columns of data -- such as day, month, year -- that             provide additional opportunities to aggregate the data.
      We will want to add a calculated field for length of ride since the data did not have the column. We will add "ride_duration" to the entire dataframe for consistency.
      There are some rides where ride_duration shows up as negative, including several hundred rides where Divvy took bikes out of circulation for Quality Control reasons.         We will want to delete these rides.
      In the "member_casual" column, there are two names for members ("member" and "Subscriber") and two names for casual riders ("Customer" and "casual"). We will need to         consolidate that from four to two labels. In the "member_casual" column, replace "Subscriber" with "member" and "Customer" with "casual".
**Key tasks**
● Check the data for errors.
● Choose your tools.
● Transform the data so you can work with it effectively.
● Document the cleaning process.

For code, check [R log](https://github.com/04vaishnavi28/Cyclistic-Bike-Share-2023/blob/main/R%20log.txt)

### Analyze
1. Descriptive analysis on ride_duration
min	q1	median	mean	q3	max
1	325	572	1091	1015	5909344


2. Compare members and casual users
3. See the average ride time by each day for members vs casual users
4. Analyze ridership data by type and weekday
5. Visualize the number of rides by rider type
6. Create a visualization for average duration
**Key tasks**
● Aggregate your data so it’s useful and accessible.
● Organize and format your data.
● Perform calculations.
● Identify trends and relationships.

For code, check [R log](https://github.com/04vaishnavi28/Cyclistic-Bike-Share-2023/blob/main/R%20log.txt)
