# Project
# UBER PICKUPS IN NEW YORK CITY
## Data visualization using R  



## Contributors:
+ Debalina Chakraborty
+ Samantha Lobo


## Introduction
This project is dedicated to create data visualization for uber and other for-hire vehicle pickups in New York City. We used datasets from [Kaggle](https://www.kaggle.com/fivethirtyeight/uber-pickups-in-new-york-city). The goal of this project was to visualize the data in different ways and point out any interesting discoveries.
One thing we sought to discover was the rush hours in NYC & distribution of trips across days, months & time of the day.
# Information about data set

The dataset contains, roughly, TWO groups of files: 
● Uber trip data from 2014 (April - September), separated by month, with detailed location information. 
● Uber trip data from 2015 (January - June), with less fine-grained location information. 
These files are named: 
● uber-raw-data-apr14.csv 
● uber-raw-data-aug14.csv 
● uber-raw-data-jul14.csv 
● uber-raw-data-jun14.csv 
● uber-raw-data-may14.csv 
● uber-raw-data-sep14.csv 

Base Code | Base Name
---|---------
B02512 | Unter
B02598 | Hinter
B02617 | Weiter
B02682 | Schmecken
B02764 | Danach-NY
B02765 | Grun
B02835 | Dreist
B02836 | Drinnen

These are Uber's bases located in New York. Each uber pickup is affiliated with a TLC (Taxi and Limousine Commission) company base. 
# How to Run the Project

In order to run the project just download the data from above mentioned source then run any file.

# Prerequisites
You need to have installed following softwares and packages in your machine before running this project.
Install R studio

## Loading Packages

    library(ggplot2)
    library(plotly) #used along with ggplot2 for data visualization.
    library(ggmap)  #used for geocoding
    library(plyr)   #used along with dplyr to aggregate data
    library(dplyr)
	library(leaflet)
	library(plotly)


## Plot of Total Uber Pickups
First, we read the data taken from Kaggle.com. In order to keep the plot simple, we only used Uber pickup data from April 2014. 
After reading the data, added a column for the day of the week. This will be used later on to plot the data over the course of the month.

    # Remove minutes and seconds from Date.Time and create Day column
    uber_apr14$Date.Time <- as.Date(uber_apr14$Date.Time, "%m/%d/%Y")
    uber_apr14$Day <- format(as.Date(uber_apr14$Date.Time, format = "%m/%d/%Y"), "%d") #adds a Day column

We then got a map of New York City using the leaflet package & plotted Top pickup locations.
Using the map of New York City as the background, we plotted the Uber pickup locations. We can Zoom in & out to get the exact locations

### Using Plotly to See Pickups Over Time  
We used plotly package in R to make the graphs interactive, you can hover over the graphs so see the data labels.

## Conclusion

Given our dataset, we produced points on a map, a histogram, and a line graph. Our original goal was to visualize the data in order to see any interesting observations. By geocoding, we were able to clearly see which areas of New York were more dense in activity. If the maps by base were not enough, the histogram clearly shows which Uber bases complete more pickups. Finally, the line graph allows us to see if there are any trends within the pickup activity. 

