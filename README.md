# python-api-challenge

WeatherPy: Exploring the Relationship Between Weather Variables and Latitude

Project Overview

This project utilizes Python to generate random geographic coordinates and create a list of cities using the Citipy library. It then fetches weather data for these cities from the OpenWeatherMap API and analyzes the relationship between various weather variables and latitude. The project includes the generation of scatter plots and linear regression analyses for temperature, humidity, cloudiness, and wind speed.

Getting Started

To run the project, we will need the following dependencies installed:

Matplotlib
Pandas
NumPy
Requests
SciPy
OpenWeatherMap API key (imported from api_keys.py)
Citipy library

Generating City List

The project generates a list of cities by randomly selecting geographic coordinates and using Citipy to find the nearest city. The resulting list includes 563 unique cities.

Fetching Weather Data

Weather data is retrieved from the OpenWeatherMap API using the cities list. The data includes latitude, longitude, maximum temperature, humidity, cloudiness, wind speed, country, and date. The data is then stored in a Pandas DataFrame.

Exporting Data

The city weather data is exported to a CSV file named "cities.csv" in the "output_data" directory.

Creating Scatter Plots

Scatter plots are generated to showcase the relationship between weather variables and latitude. Four scatter plots are created:

Latitude vs. Temperature
Latitude vs. Humidity
Latitude vs. Cloudiness
Latitude vs. Wind Speed

The plots are saved as PNG files in the "output_data" directory.

Linear Regression Analysis

Linear regression analysis is performed on each relationship to assess the correlation between latitude and weather variables. The analysis is separated into the Northern and Southern Hemispheres. The resulting plots include the regression line equation and the r-value.

Temperature vs. Latitude

Northern Hemisphere: Strong negative correlation (r-value: -0.89)
Southern Hemisphere: Moderate positive correlation (r-value: 0.64)

Humidity vs. Latitude

Northern Hemisphere: Weak positive correlation (r-value: 0.33)
Southern Hemisphere: Weak positive correlation (r-value: 0.31)

Cloudiness vs. Latitude

Northern Hemisphere: Weak positive correlation (r-value: 0.19)
Southern Hemisphere: Weak positive correlation (r-value: 0.34)

Wind Speed vs. Latitude

Northern Hemisphere: Weak negative correlation (r-value: -0.05)
Southern Hemisphere: Weak negative correlation (r-value: -0.37)

Discussion

The analysis provides insights into the relationships between latitude and weather variables. The strong negative correlation between temperature and latitude in the Northern Hemisphere indicates a decrease in temperature as one moves farther north. Conversely, in the Southern Hemisphere, there is a moderate positive correlation, suggesting an increase in temperature toward lower latitudes.

For humidity, cloudiness, and wind speed, the correlations are generally weak, indicating that latitude alone may not be a strong predictor for these variables.

The linear regression analysis and scatter plots offer a visual representation of these relationships, providing valuable insights into how geographical location influences weather patterns.



GeoHotels: Discovering Ideal Destinations with Geoapify API

Project Overview

This project combines geographical data, weather conditions, and hotel information to help users discover ideal travel destinations. It leverages Python and various libraries to create an interactive map showcasing cities, their humidity levels, and nearby hotels. The Geoapify API is utilized to find hotels within 10,000 meters of each city's coordinates.

Getting Started


To run the project, the following dependencies are installed:

hvplot.pandas
pandas
requests
Geoapify API key (imported from api_keys.py)
Loading Data

The project begins by loading weather data from a CSV file created in a previous step. The data includes information such as city, country, coordinates, maximum temperature, humidity, cloudiness, wind speed, and date.

Creating an Interactive Map

Step 1: Displaying Cities and Humidity

A map is generated with points representing cities. The size of each point corresponds to the humidity level of the respective city.

Step 2: Narrowing Down Ideal Conditions

The city data is filtered based on specified weather criteria, including maximum temperature (20-30°C) and cloudiness (0%). The resulting DataFrame, filtered_cities_df, is then displayed.

Step 3: Creating a Hotel DataFrame

A new DataFrame, hotel_df, is created to store city, country, coordinates, humidity, and hotel names. An empty column, "Hotel Name," is added to store hotel information obtained from the Geoapify API.

Step 4: Finding Hotels with Geoapify API

For each city in the hotel_df DataFrame, the Geoapify API is used to find the nearest hotel within 10,000 meters. The hotel information is added to the DataFrame.

Step 5: Adding Hotel Information to the Map

The final map includes an interactive display of cities, their humidity levels, and nearby hotels. Hovering over each point reveals additional information, including the hotel name and country.

Important Note

The hotel search process may take some time as it iterates through each city. Please be patient while the program retrieves hotel information.
