# Pyber-analysis

# Analysis of a Ride-Share App Using Python

### Goal of the Project

The overall task we are working on in this report is to visualize if there are differences in service between different city types that a rideshare comapany serves.

### Data Analysis

##### Data

The data we recieved for this project are two csv files. One contains the cities the rideshare company operates in, the number of drivers registered for each city, and the type of city each city is. There are three types of city, "Urban", "Suburban", and "Rural". The second csv contains individual ride data. For each ride, the city in which the ride took place is recorded, the date and time the ride took place, the fare paid for the ride, and a unique ID to identify the transaction. After checking the data for anomalous entries such as null values, we merge the two dataframes on the city name column they both share. This gives us the starting dataframe for our analysis.

##### Analysis

Using the merged dataframe from the two csvs, we start to obtain data on each city type. Grouping by type, we can look for the number of drivers in each city type, the number of rides in each city type, and the overall fares collected in each city type. From this we also obtain the average fare paid by each passenger and the average fair per driver in each city type. This gives us some basic information to possibly use for business decisions later. Next, to look for trends in Pyber use per week in each city type, we look at fares generated over a period of time. Since the dates given to us are both date and time stamps, a plot of this data would give us multiple shifts a day and mean nothing on the scale of months that we have data for. To rectify this, we create a pivot table in pandas with the date as the index so we can resample the data and view it in weeks instead of days or hours. This resample method only works on datetime like indexes which is why it was necessary to create the pivot table with datetime as the index. With this, we can now plot the fares paid over time for each city type.

### Results

![Data for City Type](https://github.com/roeggealissa/Pyber-analysis/blob/aaf897adc1e6eb40b1463aa4fbdd692cf041dc31/delivery1_chart.png)

The first item of note is that in the Urban areas, there are more drivers than there were rides in that given time period. For both drivers per city type and rides per city type, the sum of the Suburban and Rural types is still less than the amount in Urban areas. The sum of fares in Urban cities also far exceeds the sum of fares for the Suburban and Rural cities combines. Despite that, it is interesting to note that on average the fare of a ride in Rural cities is 10 dollars greater than that in the Urban cities, with Suburban falling between them. Since there are more drivers than rides in the Urban cities, the average fare per driver is less than the average fare per ride, whereas the reverse is true for the Suburban and Rural cities.

![Fares per Week](https://github.com/roeggealissa/Pyber-analysis/blob/2e4042de7efbbe54b8b31a1be5c78a20532d45eb/Pyber_fare_summary.png)

The trends within the three city types over time all reflect each other well. As expected based on the total fares, the Urban cities consistantly earn more per week than the Suburban cities, which in turn earn more than the Rural cities. There's a peak in all three cities around mid February. This peak is the highest earning week in the Suburban cities, whereas in the Rural cities the highest earning peak is mid March. The highest peak in Urban cities based on the chart is either the mid February peak or the peak immediately after in the beginning of March. Only by looking at the resampled table can we tell the beginning of March is the true highest peak for that time period.

### Recommendations

Based on the data provided, there are three primary recommendations. The first is to reduce the drivers in Urban areas as the number of drivers vastly outnumber the number of rides taken. The second is to hire a small amount of drivers in Suburban cities for the same reason as above; to balance the number of rides and drivers. The third is not necessary, but hiring in Rural areas for balance could be done but the ratio is much closer between drivers and rides in the Rural cities versus the two other city types. The data we have is not optimal to make these suggestions however. There are two pieces of data necessary to fully endorse these recommendations; the number of active drivers and the average wait time of riders. If the Urban population has a large amount of inactive drivers, the ratio becomes more balanced on it's own and the recommendation shifts to firing inactive drivers. The wait time is more helpful for things like rural areas, where prices are driven up due to distance but large distances can be traveled faster. If the wait time is short, there is no need to hire additional drivers to cover the population. If rural areas are experiencing high wait times, hiring more drivers to cover the area would be the recommended solution.
