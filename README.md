# Pyber-analysis

# Analysis of a Ride-Share App Using Python

### Introduction

Pyber, a python based ride-share app, has found success in hundreds of cities since its inception.  A ride-share app is one in which the company hires individuals on a contract basis to use their own vehicle to transport others with minimal oversight other than basic driver training and a background check. This is different than a taxi company which hires employees to drive company cars which typically has more oversight and individual state or city regulations. The advantage of a ride-share company is the ability to fire a large amount of contrators and replace them with ease, allowing the company to keep up with market demand and internal quotas. The overall task we are working on in this report is to visualize if there are differences in service between different city types that Pyber serves.

### Data Analysis

##### Data

The data we recieved for this project are two csv files. One contains the cities Pyber operates in, the number of drivers registered for each city, and the type of city each city is. There are three types of city, "Urban", "Suburban", and "Rural". The second csv contains individual ride data. For each ride, the city in which the ride took place is recorded, the date and time the ride took place, the fare paid for the ride, and a unique ID to identify the transaction. After checking the data for anomalous entries such as null values, we merge the two dataframes on the city name column they both share. This gives us the starting dataframe for our analysis.

##### Analysis

Using the merged dataframe from the two csvs, we start to obtain data on each city type. Grouping by type, we can look for the number of drivers in each city type, the number of rides in each city type, and the overall fares collected in each city type. From this we also obtain the average fare paid by each passenger and the average fair per driver in each city type. This gives us some basic information to possibly use for business decisions later. Next, to look for trends in Pyber use per week in each city type, we look at fares generated over a period of time. Since the dates given to us are both date and time stamps, a plot of this data would give us multiple shifts a day and mean nothing on the scale of months that we have data for. To rectify this, we create a pivot table in pandas with the date as the index so we can resample the data and view it in weeks instead of days or hours. This resample method only works on datetime like indexes which is why it was necessary to create the pivot table with datetime as the index. With this, we can now plot the fares paid over time for each city type.

### Results

![Data for City Type](https://github.com/roeggealissa/Pyber-analysis/blob/aaf897adc1e6eb40b1463aa4fbdd692cf041dc31/delivery1_chart.png)

The first item of note is that in the Urban areas, there are more drivers than there were rides in that given time period.
