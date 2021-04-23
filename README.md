# PyBer Ride Sharing Analysis

## Overview
The purpose of this project is to create a summary DataFrame of the ride-sharing data, by city, for Pyber.  In addition a multiple-line graph is included to show the total weekly fares for each city type. With this informtion a summary will be provided below that explains how the data differs by city type and how those differences can be used by decision-makers at PyBer. 

## Project Description
### Setup
To begin the project two Pyber files are added to the resources folder, city_data.csv and ride_data.csv.<br>

The city_data.csv once read into a DataFrame shows that we have three columns: __city, driver_count and type__ where driver count is the number of drivers in the city and type is the type of city, urban, suburban and rural.<br>

The ride_data.csv read into a DataFrame shows four columns: __city, date, fare and ride_id__ where fare is the amount of the fare collected for the ride and the ride id is a unique number for each ride.
<br>

The two DataFrames are then combined into one DataFrame, pyber_data_df, using the city column as the common column.  This DataFrame has the required columns for us to create the summary. These columns are __city, date, fare, ride_id, driver_count, type__.<br>

<img src="https://github.com/linb960/PyBer_Analysis/blob/main/Resources/pyber_data_df.png" width="600" height="200" />

### Summary DataFrame Creation
The first goal of this analysis is to summarize the data.  To do this the groupby function is used to get the __Total Rides, Total Drivers and the Total Fares__.  Then two calculations are done to get the  __Average Fare per Ride and Average Fare per Driver__.  

### Pivot Table Creation

Another goal of this analysis is to create the line and the combined data is used to find the total amount in dollars collected for each city type for the first four month of 2019. A pivot table is used to help summaraze the date and fare around the type of city.<br>
The steps are as follows:
1. The data from the pyber_data_df is grouped by date for each type of city and the fares are summed and a new DataFrame, fares_by_date, is created. 
2. The index is then reset so the pivot function can be used.  
3. The pivot table is then created with the 'date' as the index, the columns are the city type, and values='fare' to get the total fares for each type of city by the date. 
<img src="https://github.com/linb960/PyBer_Analysis/blob/main/Resources/fares_pivot_df.png" width="300" height="190" />


## Results
### Summary DataFrame results
The results from the __Summary DataFrame__ are totals and averages described above and are shown below:

<img src="https://github.com/linb960/PyBer_Analysis/blob/main/Resources/pyber_summary_df.png" width="600" height="125" />

The main points are as follows:
- Rural totals for rides, fares and drivers are lower than Suburban and Urban totals with Urban being significantly greater then the other two.
- Urban fares per ride and per driver are less than Suburban and Rural with Rural fares the greatest.

### Line Graph results
To get to the creation of the line graph the pivot table data is narrowed to just the dates between 01-01-2019 and 04-29-1019 using the .loc() function and then resampled using the resample() function by week.<br>
Here is the final DataFrame:<br>
<img src="https://github.com/linb960/PyBer_Analysis/blob/main/Resources/fares_resampled.png" width="200" height="400" /> <br>

This data of this fares_resampled_df is used to create the line graph where the __x-axis is the month__, the __y-axis is the fare in dollars__ and there are __three lines, one for each city type__ as shown here:
<img src="https://github.com/linb960/PyBer_Analysis/blob/main/analysis/Pyber_fare_summary.png"/>
By looking at the graph the conclusions about the fares becomes quite evident.  The amount of money collected in fares in the Urban cities is far greater than the Rural Cities while the Suburban cities remain in between.

## Summary
In summary it is evident the the analysis bears out what most people would probably conclude, people who live in urban areas ride more frequently in Pyber vehicles than they do in rural and suburban areas.  Therefore the amount of money in fares collected in urban areas over all is greater.
### Recommendations to the CEO of Pyber
1. The suburban area needs more drivers.  In the urban areas there are more drivers than rides at approximately 3 drivers for every 2 rides. Yet in the Suburban area there are more rides than drivers at approximately 3 rides for every 2 drivers.
2. Increase the fares in the urban areas.  Although the rides may be shorter the average fare in urban areas is about $6 less than in Suburban areas and $10 less than Rural.
3. Do further analysis on some of the peaks in the line graph for those weeks and consider if peaks come on weekends or holidays and try to increase the number of drivers available at those times to get more business.

