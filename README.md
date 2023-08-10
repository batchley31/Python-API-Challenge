# Python-API-Challenge

  # Part 1: WeatherPy
# Create Plots to Showcase the Relationship Between Weather Variables and Latitude.

  Before I started creating my plot charts I had to create and empty list so after I pulled all the informaition from the API reference I can add it in and name it certian variables that I am looking for.  I did that by using ".append" to create a dictionary off all my variables that I wanted and added them to the empty "city_data" list.  I then created my own DataFrame with the new information that I created in my new list so I can transform it into a csv to read.
  To create the charts I used a scatter plot to measure the cities latitude(x-axis) compared to it's max temperature(y_axis).  I set my labels for the x-axis, y-axis and title, and then created a grid in the graph by setting up my linestyle and the color for it. I did the same exact thing for my charts for humidity, cloudiness, and wind speed.  I kept latitude as the x-axis and juse switched out my y-axis for the variable I was looking for on each one.  Out of all the comparisons Latitude vs Max Temp seemed to be the only one to have some sort of correlation with each other.  It showed I nice pattern that the closer to 0 Latitude the city was the higher the max temp they recorded, and as the latitude grew to a bigger numeber the max temp recordings went down. For the other three graphs the dots were scatter all around and did not show a pattern between the cities.

# Compute Linear Regression for Each Relationship.
  To start with my linear regression I created my variables to calculate and then made the equation for the regression values and the line equation so it would all show on the scatter plot along with the dots. 
  To seperate my data into Northern and Southern Hemisphere's I created new DataFrames that had the Latitude equal greater than or equal to 0 so it would reperesnt anything north of the equator.  For the southern hemisphere I did the exact same thing except had the Latitude equal anything less than 0 so all negative numbers would show up since they are below the equator.
  I then used each northern and southern hemisphere Dataframe to instert into each regression plot again keeping latitude as my a cordinate and changing my code to search for Max Temp, Humidity, Cloudiness, and Wind Speed and them into the y cordinate for their respective charts.  The ploted linear regression line and equation helps show that latitude vs max temp are the only ones thats actually show some sort of patern.  To split between norhtern and southern, the graphs actually show a better correlation in the northern hemisphere than the souther as the dots are closer together and not as many skew away from the line, or go as far.

  # Part 2: VacationPy
# Create a map that displays a point for every city.
  To create my map I used hvplot.points to plot my cities by their latitude and longitude, then set the frame width and height, and picked a random color for each city once it was ploted on the Geo map

# Narrow down the DataFrame to find your ideal weather condition.
  To find the ideal locations I would like to live, I looked into my orignial dataframe located all the cities that had a max temp of 27 degrees celsius or less but greater than 21 degrees celsius.  I then narrowed my new ideal data frame and looked even further to only cities that have wind speeds less than 4.5 and cloudiness equal to 0. I then used a dropna function to drop any of the rows that didnt have values.

# Create a new DataFrame called hotel_df to store the city, country, coordinates, and humidity.
  For my new data frame I took my ideal wheather data frame and only had it list the City, Country, Latitude, Longitude, and Humidity.  After that I created a new column named "Hotel Name" and left it empty so I could import data into it later.

# For each city, find the first hotel located within 10,000 meters of your coordinates.
  To search for hotels around my ideal cities I set my radius to 10,000 meters, and the parameters equaling categories that searched for hotels, apikey to use the geoapify, and set the limit to 20. Then i am looking through all the rows by latitude and longitude and setting my parameter filters to circle the point by the 10000 meter radius and search inside of it only. I then have create my API request and convert it into JSON format to start my search for the closest hotel to each city.
  In order to do that I looked into my hotel dataframe and searched hotels that fit my index that I set.  If it found something it will print the name of the city and the name of the hotel closest to that city on the same line.  If it does not find anything within those perameters it will still print the city name but instead of putting in the name of the hotel it will print "no hotel found" becuase it coufl not find a locaiton.

# Add the hotel name and the country as additional information in the hover message
  To create my new map I set all the same variables as the last one, the only thing I added was the hover_cols which repersents want I want added into my message that pops up when I hover over a city.  The two variables I added were Hotel Name and Country. 

  
