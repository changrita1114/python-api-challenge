## Weather Project 
### Background
Whether financial, political, or social -- data's true power lies in its ability to answer questions definitively. So let's take what you've learned about Python requests, APIs, and JSON traversals to answer a fundamental question: "What's the weather like as we approach the equator?"

Now, we know what you may be thinking: "Duh. It gets hotter..."

But, if pressed, how would you prove it?
### Methods
There were two parts of this project.
#### Part I - WeatherPy
A Python script was created to visualize the weather of over 500 cities across the world of varying distance from the equator. To accomplish this, a simple Python library([citipy](https://pypi.org/project/citipy/)) and the OpenWeatherMap API were used.

First was to create a series of scatter plots to showcase the following relationships:
* Temperature (F) vs. Latitude
* Humidity (%) vs. Latitude
* Cloudiness (%) vs. Latitude
* Wind Speed (mph) vs. Latitud

Second was to run linear regression on each relationship. Data was separated into Northern Hemisphere (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude):
* Northern Hemisphere - Temperature (F) vs. Latitude
* Southern Hemisphere - Temperature (F) vs. Latitude
* Northern Hemisphere - Humidity (%) vs. Latitude
* Southern Hemisphere - Humidity (%) vs. Latitude
* Northern Hemisphere - Cloudiness (%) vs. Latitude
* Southern Hemisphere - Cloudiness (%) vs. Latitude
* Northern Hemisphere - Wind Speed (mph) vs. Latitude
* Southern Hemisphere - Wind Speed (mph) vs. Latitude

Final Jupyter notebook:
* Randomly select at least 500 unique (non-repeat) cities based on latitude and longitude.
* Perform a weather check on each of the cities using a series of successive API calls.
* Include a print log of each city as it's being processed with the city number and city name.
* Save a CSV of all retrieved data and a PNG image for each scatter plot.

#### Results
As expected, the weather becomes siginigicantly warmer as one approaches the equator. Humidity, cloudiness and wind speed are not related to latitude changes.
Please find out more information in the [visualization website](https://changrita1114.github.io/Web-Design-Challenge/).
#### Part II - VacationPy 
Jupyter-gmaps and the Google Places API were used for working with weather data to plan future vacations.

* A heat map was created that displays the humidity for every city from part I of the project.
![alt heatmap](https://github.com/changrita1114/python-api-challenge/blob/master/WeatherPy/13_heatmap_01.png)
* The DataFrame was narrowed down to find my ideal weather condition. For example:
    * A max temperature lower than 80 degrees but higher than 75.
    * Wind speed less than 10 mph.
    * Zero cloudiness.
    * Drop any rows that don't contain all three conditions.
* Google Places API was used to find the first hotel for each city located within 5000 meters of the selected coordinates.
* The hotels on top of the humidity heatmap with each pin containing the Hotel Name, City, and Country were plotted.
![alt heatmap](https://github.com/changrita1114/python-api-challenge/blob/master/WeatherPy/14_heatmap_02.png)

### Disclaimer
The resources of this master branch are only for educational purposes. All reserved rights belong to UCSD Data Science and Visualization Boot Camp.
