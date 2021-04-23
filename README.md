# PyBer Ride Sharing Analysis

## Overview
The purpose of this project is to create a summary DataFrame of the ride-sharing data, by city, for Pyber.  In addition a multiple-line graph is included to show the total weekly fares for each city type. With this informtion a summary will be provided below that explains how the data differs by city type and how those differences can be used by decision-makers at PyBer. 

## Project Description
### Setup
To begin the project two Pyber files are added to the resources folder, city_data.csv and ride_data.csv.<br>

The city_data.csv once read into a DataFrame shows that we have three columns: __city, driver_count and type__ where driver count is the number of drivers in the city and type is the type of city, urban, suburban and rural.<br>

The ride_data.csv read into a DataFrame shows four columns: __city, date, fare and ride_id__ where fare is the amount of the fare collected for the ride and the ride id is a unique number for each ride.
<br>

The two DataFrames are then combined into one DataFrame, pyber_data_df, using the city column as the common column.  This DataFrame has the required columns for us to create the summary. These columns then are __city, date, fare, ride_id, driver_count, type__.<br>

<img src="https://github.com/linb960/PyBer_Analysis/blob/main/Resources/pyber_data_df.png" width="600" height="200" />

### Summary DataFrame Creation
The first goal of this analysis is to summarize the data.  To do this the groupby function is used to get the __Total Rides, Total Drivers and the Total Fares__.  Then two calculations are done to get the  __Average Fare per Ride and Average Fare per Driver__.  These totals and averages are added to a DataFrame and the result are as follows:

<img src="https://github.com/linb960/PyBer_Analysis/blob/main/Resources/pyber_summary_df.png" width="600" height="200" />

### Pivot Table Creation for Analysis

Another goal of this analysis is to create the line and the combined data is used to find the total amount in dollars collected for each city type for the first four month of 2019. A pivot table is used to help summaraze the date and fare around the type of city.<br>
The steps are as follows:
1. The data from the pyber_data_df is grouped by date for each type of city and the fares are summed. 
2. The index is reset to flatten out the table.  
3. 

## Results

There is a description of the differences in ride-sharing data among the different city types. Ride-sharing data include the total rides, total drivers, total fares, average fare per ride and driver, and total fare by city type. 

## Summary

There is a statement summarizing three business recommendations to the CEO for addressing any disparities among the city types. 

