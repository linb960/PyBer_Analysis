# PyBer Ride Sharing Analysis

## Overview
The purpose of this project is to visualize and summarize data from the ride sharing company, Pyber.  Do do this a summary DataFrame will be created using python in a jupyter notebook.  The ride sharing data will be filtered by city type and a line graph will be drawn using matplotlib.  The final output will show the total of the fares the drivers collected, in dollars, by city type, urban, suburban and rural, for the first four months of 2019.

## Project Description
### Setup
To begin the project two files Pyber files are added to the resources folder, city_data.csv and ride_data.csv.<br>

The city_data.csv once read into a DataFrame shows that we have three columns: __city, driver_count and type__ where driver count is the number of drivers in the city and type is the type of city, urban, suburban and rural.<br>

The ride_data.csv read into a DataFrame shows four columns: __city, date, fare and ride_id__ where fare is the amount of the fare collected for the ride and the ride id is a unique number for each ride.
<br>

The two DataFrames are then combined into one DataFrame, pyber_data_df, using the city column as the common column.  This DataFrame has the required columns for us to create the summary. These columns then are __city, date, fare, ride_id, driver_count, type__.<br>

<img src="https://github.com/linb960/PyBer_Analysis/blob/main/Resources/fares_by_date.png" width="600" height="300" />


### Pivot Table Creation for Analysis

Since the ulitmate goal of this analysis will be to find the total amount in dollars made for each city type for the first four month of the year 2019 a pivot table is used to help summaraze the date and fare around the type of city.<br>
First the data from the pyber_data_df is grouped by date for each type of city and the fares are summed. Next the index is reset to flatten out the table.  

## Results

There is a description of the differences in ride-sharing data among the different city types. Ride-sharing data include the total rides, total drivers, total fares, average fare per ride and driver, and total fare by city type. 

## Summary

There is a statement summarizing three business recommendations to the CEO for addressing any disparities among the city types. 

