# Case Study: Converting Casual Riders into Annual Members
This project analyzes bike usage patterns to understand how casual riders and annual members of Cyclistic, a bike-share company in Chicago, use bikes differently. The goal is to provide data-driven insights to help convert casual riders into annual members.

## About the company
In 2016, Cyclistic launched a successful bike-share offering. Since then, the program has grown to a fleet of 5,824 bicycles that are geotracked and locked into a network of 692 stations across Chicago. The bikes can be unlocked from one station and returned to any other station in the system anytime.

## Scenario
The director of marketing at Cyclistic, a bike-share company in Chicago believes that the company’s future success depends on maximizing the number of annual memberships.

## Analytical Goals
Understand how casual riders and annual members use Cyclistic bikes differently. From these insights, design a new marketing strategy to convert casual riders into annual members.

## Steps
The steps of the data analysis process: **Ask**, **Prepare**, **Process**, **Analyze**, **Share**, and **Act**.

### <ins>Ask</ins>
Three questions will guide the future marketing program:
1. How do annual members and casual riders use Cyclistic bikes differently?
2. Why would casual riders buy Cyclistic annual memberships?
3. How can Cyclistic use digital media to influence casual riders to become members?

**Key tasks**
* Identify the business task
* Consider key stakeholders

**Deliverable**
* A clear statement of the business task

### <ins>Prepare</ins>
Use Cyclistic’s historical trip data to analyze and identify trends. [Download the previous 12 months of Cyclistic trip data here](https://divvy-tripdata.s3.amazonaws.com/index.html).

*Jan 2023 to Dec 2023 data have been used in this analysis.*

**Key tasks**
* Download data and store it appropriately.
* Identify how it’s organized.
* Sort and filter the data.
* Determine the credibility of the data.

**Deliverable**
* A description of all data sources used

### <ins>Process</ins>
1. Collect data.
2. Wrangle data and combine into a single file.
3. Clean up and add data to prepare for analysis.
    * Inspect the new table that has been created
    * There are a few problems we will need to fix:
      - The data can only be aggregated at the ride-level, which is too granular. We will want to add some additional columns of data -- such as day, month, year -- that provide additional opportunities to aggregate the data.
      - We will want to add a calculated field for length of ride since the data did not have the column. We will add "ride_duration" to the entire dataframe for consistency.
      - There are some rides where ride_duration shows up as negative, including several hundred rides where Divvy took bikes out of circulation for Quality Control reasons. We will want to delete these rides.
      - In the "member_casual" column, there are two names for members ("member" and "Subscriber") and two names for casual riders ("Customer" and "casual"). We will need to consolidate that from four to two labels. In the "member_casual" column, replace "Subscriber" with "member" and "Customer" with "casual".

**Key tasks**
* Check the data for errors.
* Choose your tools.
* Transform the data so you can work with it effectively.
* Document the cleaning process.

For code, check [R log](https://github.com/04vaishnavi28/Cyclistic-Bike-Share-2023/blob/main/R%20log.txt)

**Deliverable**
* Documentation of any cleaning or manipulation of data

### <ins>Analyze</ins>
1. Descriptive analysis on ride_duration

| Min | Q1  | Median | Mean | Q3  | Max     |
| --- | --- | ------ | ---- | --- | ------- |
| 1   | 325 | 572    | 1091 | 1015| 5909344 |

2. Compare members and casual users

| Member/Casual | Mean     | Median | Max      | Min |
| ------------- | -------- | ------ | -------- | --- |
| Casual        | 1695.2375| 711    | 5,909,344| 1   |
| Member        | 751.6673 | 511    | 93,580   | 1   |

3. See the average ride time by each day for members vs casual users

| Member/Casual | Sunday    | Monday    | Tuesday   | Wednesday | Thursday  | Friday    | Saturday  |
| ------------- | --------- | --------- | --------- | --------- | --------- | --------- | --------- |
| Casual        | 1972.1093 | 1663.2545 | 1505.3791 | 1458.6211 | 1483.8940 | 1636.1457 | 1928.7081 |
| Member        | 839.5533  | 714.2541  | 720.9112  | 716.9467  | 721.2935  | 748.8346  | 836.4458  |

4. Analyze ridership data by type and weekday

| Rideable Type | Member/Casual | Sunday  | Monday  | Tuesday  | Wednesday | Thursday | Friday  | Saturday |
| ------------- | ------------- | ------- | ------- | -------- | --------- | -------- | ------- | -------- |
| Classic Bike  | Casual        | 155,214 | 96,980  | 99,648   | 98,618    | 107,945  | 127,753 | 190,647  |
| Classic Bike  | Member        | 207,596 | 250,854 | 290,229  | 289,138   | 288,459  | 256,942 | 235,808  |
| Docked Bike   | Casual        | 14,933  | 9,140   | 8,695    | 7,870     | 8,913    | 11,450  | 17,286   |
| Electric Bike | Casual        | 165,470 | 128,646 | 137,819  | 142,605   | 153,682  | 172,632 | 202,675  |
| Electric Bike | Member        | 201,169 | 243,627 | 286,400  | 297,227   | 301,027  | 274,561 | 236,950  |

5. Visualize the number of rides by rider type

![no  of rides over weekdays](https://github.com/user-attachments/assets/3c322610-ccca-4452-ab0c-0c2d43157949)

6. Create a visualization for average duration

![avg  duration over weekdays](https://github.com/user-attachments/assets/9745e15f-dd43-4ef5-82a5-ea0fec499b77)

**Key tasks**
* Aggregate your data so it’s useful and accessible.
* Organize and format your data.
* Perform calculations.
* Identify trends and relationships.

For code, check [R log](https://github.com/04vaishnavi28/Cyclistic-Bike-Share-2023/blob/main/R%20log.txt)

**Deliverable**
* A summary of your analysis

### <ins>Share</ins>
Create visualizations to share your findings.

**Key tasks**
* Determine the best way to share your findings.
* Create effective data visualizations.
* Present your findings.
* Ensure your work is accessible.

![Screenshot (228)](https://github.com/user-attachments/assets/b1a21c4e-bedf-447f-b73d-393220547868)

![Screenshot (230)](https://github.com/user-attachments/assets/87a124ff-b191-40c0-be6c-c87afed25fd9)

![Screenshot (232)](https://github.com/user-attachments/assets/4cbbaf64-eac5-48c7-afb6-f344f3d39440)

For visualization, check [Tableau](https://public.tableau.com/app/profile/vaishnavi.hemadri/viz/Cyclistic-BikeShare2023/Dashboard1)

**Deliverable**
* Supporting visualizations and key findings

### <ins>Act</ins>
Now that you have finished creating your visualizations, act on your findings. Prepare the deliverables you created, including the three top recommendations based on your analysis.

**Key tasks**
* Create your portfolio.
* Add your case study.
* Practice presenting your case study to a friend or family member.

**Deliverable**
* Your top three recommendations based on your analysis

For presentation, check [Cyclistic - Bike Share 2023.pptx](https://github.com/user-attachments/files/17266699/Cyclistic.-.Bike.Share.2023.pptx)

.
